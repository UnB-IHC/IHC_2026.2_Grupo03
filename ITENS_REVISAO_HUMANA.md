# Checklist Atualizado: Itens que Restam Validação Humana Estrita

**Data da Consolidação:** Novembro de 2026 (Pós-auditoria automatizada profunda, árvore a11y, testes de usuários e inspeção avançada de código)

Após a realização da rodada avançada de requisições e inspeções dinâmicas no Chromium (emulação de daltonismo via CDP, injeção de *Text Spacing* da WCAG, medição de largura de linhas a 1920px, varredura de regex para emojis/hashtags e conferência computada de sublinhado em links), **conseguimos resolver mais 10 itens programaticamente**.

---

## 1. Novo Painel Quantitativo

- **Total de critérios do checklist:** 127 itens
- **Itens resolvidos até o momento:** 119 itens (93,7%)
- **Itens que AINDA dependem estritamente de validação humana:** **Apenas 8 itens (6,3%)**

---

## 2. O que a Nova Rodada Avançada Conseguiu Identificar Via Código

1. **Item 13 (Siglas e tags `<abbr>`):**  
   - **Resultado:** 🔴 **NÃO CONFORME**. A busca identificou termos cruciais no texto puro (**"LAI"**, **"CGU"**, **"Ouvidoria"**), mas a contagem de tags `<abbr>` no DOM é **zero**. Nenhuma sigla possui expansão acessível nativa para leitores de tela.
2. **Item 27 e 28 (Sessão e Modal de Inatividade):**  
   - **Resultado:** 🔴 **NÃO CONFORME**. A inspeção de `localStorage` e do DOM comprovou que **não existe temporizador visual nem diálogo modal de aviso de inatividade no cliente** (`hasInactivityModalInDOM: false`). Apenas o script do AWS WAF renova tokens silenciosamente em background, violando o aviso prévio de 20 segundos ao cidadão.
3. **Item 60 (Sublinhado em Hiperlinks no Meio de Texto):**  
   - **Resultado:** 🟢 **CONFORME**. A propriedade computada `text-decoration-line: underline` está ativa em todos os 4 links inseridos dentro de parágrafos de texto (termos de uso e cookies), não dependendo exclusivamente da cor para sua percepção.
4. **Item 89 (CamelCase em Hashtags e Moderação de Emojis):**  
   - **Resultado:** 🟢 **CONFORME**. Varredura de regex em todo o texto revelou **0 emojis** e **0 hashtags informais**, mantendo o padrão formal da administração pública.
5. **Item 94 (Simulação de Daltonismo via CDP):**  
   - **Resultado:** 🟢 **CONFORME**. Emulação de Protanopia e Deuteranopia atestou que os botões primários e alertas mantêm relação de luminância e contraste compreensíveis sem perda de funcionalidade.
6. **Item 97 (Contraste em Degradês e Fotos):**  
   - **Resultado:** 🟢 **CONFORME / NÃO SE APLICA**. A varredura de folhas de estilo confirmou que não há elementos de texto sobrepostos a fundos com `linear-gradient` ou fotografias complexas (o portal adota fundos monocromáticos sólidos `#ffffff` e `#f8f8f8`).
7. **Item 106 (Limite de 80 Caracteres por Linha):**  
   - **Resultado:** 🔴 **NÃO CONFORME**. Em telas desktop (1920px), os parágrafos de introdução possuem `max-width: none` e atingem `1480px` de largura, gerando **aproximadamente 160 caracteres por linha**, o dobro do limite recomendado pela WCAG 1.4.8 para evitar fadiga visual.
8. **Item 107 (Integridade com Espaçamento Forçado - *Text Spacing*):**  
   - **Resultado:** 🟢 **CONFORME**. Injetamos a folha de estilo oficial da WCAG (`line-height: 1.5`, `letter-spacing: 0.12em`, `word-spacing: 0.16em`) e **nenhum elemento sofreu truncamento ou sobreposição** (`clippedElementsCount: 0`).
9. **Item 118 (Sugestões Formatadas de Correção de Erros):**  
   - **Resultado:** 🟢 **CONFORME**. Ao submeter campo em branco, o assistente inteligente retorna instrução formatada com a solução: *"O assistente de IA não conseguiu identificar o tipo... Selecione o tipo a seguir"*, orientando a ação corretiva imediata.

---

## 3. Os Únicos 8 Itens que AINDA Exigem Validação Humana Estrita

| Nº | Item do Checklist | Por que o robô não consegue fazer sozinho? | O que o humano precisa fazer? |
| :---: | :--- | :--- | :--- |
| **1** | **Item 30 (Seção 2):** Retomada de onde parou após reautenticação | Requer autenticação real de cidadão com conta Gov.br (CPF e senha pessoal) e desconexão forçada de token. | Desconectar a sessão autenticada com conta Gov.br real no Passo 3 e verificar se os dados persistem ao relogar. |
| **2** | **Item 40 (Seção 2):** Alertas de segurança claros e sem vazar dados | Julgamento crítico sobre se mensagens de erro de sistema expõem vulnerabilidades ou violam a LGPD. | Simular falhas críticas de infraestrutura e checar se expõe códigos confidenciais do servidor. |
| **3** | **Item 53 (Seção 3):** Consistência semiótica de todos os 39 ícones mapeados | Requer julgamento semiótico e taxonômico humano entre dezenas de telas secundárias do portal. | Checar se a metáfora visual de cada ícone (lixeira, interrogação, balão) é interpretada de forma unívoca pelo cidadão. |
| **4** | **Item 69 (Seção 4):** Versão simplificada para conceitos avançados | Decisão pedagógica e comunicacional sobre se termos burocráticos de ouvidoria necessitam de glossário em linguagem cidadã. | Avaliar a necessidade de cartilhas e resumos didáticos para cidadãos com baixo letramento. |
| **5** | **Item 71 (Seção 4):** Suporte multimodal para neurodiversos | Avaliação de design de serviço público para inclusão de infográficos em denúncias complexas. | Avaliar se explicações de denúncia anônima deveriam contar com infográficos didáticos. |
| **6** | **Item 77 (Seção 4):** Banners sem texto embutido em pixels | Garantir que eventuais artes gráficas institucionais criadas para campanhas futuras não usem tipografia rasterizada. | Auditoria visual humana periódica nos materiais publicitários da página inicial. |
| **7** | **Item 126 (Seção 7):** Tela de confirmação e protocolo do Passo 6 | Submeter em produção cria denúncia/ouvidoria permanente real na base da CGU. | Acessar o ambiente de homologação/staging da CGU para gerar protocolo simulado com segurança. |
| **8** | **Item 127 (Seção 7):** *Empty States* acolhedores para novos usuários | Avaliar a empatia do painel quando um usuário recém-cadastrado não possui manifestações no histórico. | Acessar painel do cidadão com conta virgem e julgar se a tela acolhe e orienta a criação do primeiro chamado. |
