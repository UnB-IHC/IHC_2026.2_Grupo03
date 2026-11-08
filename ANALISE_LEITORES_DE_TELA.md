# Simulação e Auditoria Técnica: Como os Leitores de Tela Leem o Fala.BR

**Data:** Novembro de 2026  
**Tecnologia Empregada:** Extração da **Árvore de Acessibilidade do Chromium (A11y Tree / Chrome DevTools Protocol)**, exatamente a mesma interface de acessibilidade exposta pelo navegador para as APIs de acessibilidade do sistema operacional (UI Automation e IAccessible2 no Windows, utilizadas pelo **NVDA** e **JAWS**, e Android Accessibility framework, utilizado pelo **TalkBack**).

---

## 1. Como um Leitor de Tela Realmente "Lê" a Página?

Um leitor de tela (NVDA, TalkBack, VoiceOver) **não lê o código HTML bruto e nem enxerga o CSS visual**.  
Ele percorre a **Árvore de Acessibilidade (Accessibility Tree)** calculada em tempo real pelo navegador. Para cada elemento, ele anuncia três informações fundamentais:
1. **Nome Acessível (*Accessible Name*):** O texto que identifica o elemento.
2. **Papel (*Role*):** O tipo de controle (ex.: *botão*, *caixa de texto*, *link*, *cabeçalho*).
3. **Estado / Valor (*State / Value*):** Se está marcado, expandido, desabilitado ou o texto digitado.

---

## 2. Diagnóstico Geral: Os Leitores de Tela Conseguem Ler?

> **RESPOSTA DIRETA:**  
> **Sim, os leitores de tela conseguem ler a maior parte do texto da página, MAS enfrentam barreiras severas que tornam a navegação confusa, repetitiva e, em alguns pontos, praticamente às cegas.**

Abaixo estão as constatações detalhadas nó a nó extraídas da Árvore de Acessibilidade do Fala.BR:

---

## 3. Principais Barreiras Auditivas Detectadas na Árvore de Acessibilidade

### 🔴 Barreira 1: O "Eco de Botões Fantasmas" (`aria-label="Botão"`)
No topo da página e nos menus principais, a árvore de acessibilidade revela que múltiplos botões têm seu nome acessível substituído pela palavra genérica `"Botão"`.
Quando o usuário do NVDA navega por `Tab` no cabeçalho, o sintetizador de voz lê literalmente:
> 🔊 *"Botão"*  
> 🔊 *"Botão"*  
> 🔊 *"Abrir, botão"*  
> 🔊 *"Botão"*  
> 🔊 *"VLibras, botão"*  
> 🔊 *"Cookies, botão"*  
> 🔊 *"Alto Contraste, botão"*  
> 🔊 *"Idioma, botão"*  
> 🔊 *"Botão"*  

**Impacto:** O usuário cego não tem a menor ideia do que esses botões fazem (na interface visual eles são "Início", "Órgãos", "Dados Abertos", mas o leitor só escuta a palavra "Botão"). Além disso, quem usa comando por voz não consegue dizer *"clicar em Órgãos"*, pois para o sistema o elemento só se chama *"Botão"*.

---

### 🟡 Barreira 2: Leitura do Campo de Relato (Passo 1)
Ao chegar no campo principal de texto do formulário (`<textarea id="re_relato">`):
- **Papel (*Role*):** `textbox` (caixa de texto multilinhas)
- **Nome Acessível (*Name*):** `"Digite seu relato"` (gerado a partir do `placeholder` / `title`)
- **Descrição (*Description*):** Nenhuma vinculada (`aria-describedby` ausente)

**O que o leitor de tela anuncia:**
> 🔊 *"Digite seu relato, caixa de texto, edição, multilinha, obrigatório."*

**Veredito:** O leitor de tela **consegue ler** e anunciar o campo porque o navegador utilizou o *placeholder* como fallback. Porém, **não há `<label>` semântico associado**, e o leitor de tela não anuncia os critérios de anexos e orientações adicionais que estão visíveis apenas graficamente na tela.

---

### 🔴 Barreira 3: Botões Mudos e Nomes Excessivamente Longos (Passo 2)
No Passo 2 (*Tipo e Assunto*), a árvore de acessibilidade revelou dois extremos graves:
1. **Botão Mudo (Sem Nome):**  
   - Foi detectado nó interativo com `role: "button"` e `name: ""` (vazio). O leitor de tela simplesmente diz *"botão"* sem nenhuma palavra de identificação.
2. **Botão com Parágrafo Inteiro como Nome:**  
   - Em vez de ler apenas o título do card, o leitor de tela foi forçado a ler um texto corrido de mais de 200 caracteres de instruções acoplado ao nome do botão:
   > 🔊 *"Registre seu relato. É importante que seja claro e objetivo, mas completo com informações que facilitarão a análise. Indique o órgão e o agente responsável, o tema, o serviço relacionado, a data, o local, as condutas praticadas, e tudo mais que possa ajudar a entender o caso, botão."*

---

### 🟡 Barreira 4: Leitura do Assistente de Etapas (*Stepper Wizard*)
Os 6 passos do formulário são expostos na árvore de acessibilidade como elementos do tipo `tab` (aba):
- `[tab] Relato` (selecionado)
- `[tab] Tipo e Assunto`
- `[tab] Local`
- `[tab] Envolvidos`
- `[tab] Revisão`
- `[tab] Conclusão`

**Veredito:** O leitor de tela **consegue ler os nomes das etapas**. No entanto, devido à falha técnica de código identificada anteriormente (`aria-controls="tab0"` com ID inexistente no DOM), o leitor de tela não consegue saltar diretamente da aba para o painel de conteúdo correspondente via atalho de abas.

---

### 🔴 Barreira 5: Falta de Anúncio de Erro ao Falhar Validação
Quando o usuário tenta avançar sem preencher um campo obrigatório:
- O alerta visual surge na tela (`role="alert"`), mas **o foco da árvore de acessibilidade permanece preso no nó raiz `[RootWebArea]` (corpo da página)**.
- **O que acontece no NVDA/TalkBack:** O leitor de tela **permanece em silêncio** ou continua lendo o rodapé, sem levar o usuário cego até o aviso de erro, fazendo parecer que o botão "Avançar" simplesmente quebrou e não fez nada.

---

## 4. Tabela de Verificação da Leitura pelos Leitores de Tela

| Componente / Área | O Leitor de Tela Consegue Ler? | Como é Lido na Prática | Severidade |
| :--- | :---: | :--- | :---: |
| **Cabeçalho e Menus Principais** | ⚠️ Parcialmente | Lê "Botão, botão, botão" em 5 controles por causa de `aria-label="Botão"` genérico. | 🔴 Alta |
| **Banner de Cookies** | 🟢 Sim | Lê o texto do consentimento e os botões "Aceitar" e "Definir". | 🟢 Baixa |
| **Widget do VLibras** | 🟢 Sim | Anunciado como `[button] VLibras`. | 🟢 Baixa |
| **Passos do Formulário (1 a 6)** | 🟢 Sim | Lê como abas ("Relato", "Tipo e Assunto"), mas com atalhos de controle de aba quebrados. | 🟡 Média |
| **Caixa de Texto de Relato (Passo 1)** | 🟢 Sim | Lê "Digite seu relato, caixa de texto multilinha" (via placeholder de contingência). | 🟡 Média |
| **Contador de Caracteres** | ⚠️ Parcialmente | Não possui `aria-live`, portanto não atualiza o leitor de tela conforme a pessoa digita. | 🟡 Média |
| **Cards de Seleção de Tipo (Passo 2)** | ⚠️ Parcialmente | Lê nomes gigantescos ou vazios em determinados cartões customizados. | 🔴 Alta |
| **Alertas de Erro de Validação** | ❌ Não Conduz | O leitor não move o foco para o erro; o usuário cego fica sem saber por que não avançou. | 🔴 Crítica |

---

## 5. Como Resolver sem Precisar de NVDA Manualmente

Para que qualquer leitor de tela leia o portal com 100% de clareza, os desenvolvedores da CGU precisam apenas aplicar 3 regras simples no HTML:
1. **Remover o atributo `aria-label="Botão"`** dos botões que já têm texto visível (ex.: deixar apenas `<button class="br-button">Início</button>`).
2. **Associar `<label for="re_relato">Digite seu relato</label>`** em vez de confiar apenas no texto cinza do *placeholder*.
3. **Mover o foco programático (`input.focus()`)** quando houver erro de validação.
