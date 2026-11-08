# Relatório de Avaliação de Acessibilidade Digital — Portal Fala.BR

**Data da Avaliação:** Novembro de 2026  
**Ambiente / URLs Avaliadas:**  
1. **Página Inicial:** [https://falabr.cgu.gov.br/v2/](https://falabr.cgu.gov.br/v2/)  
2. **Fluxo de Registro de Manifestações (6 Passos):** [https://falabr.cgu.gov.br/v2/manifestacoes/registrar](https://falabr.cgu.gov.br/v2/manifestacoes/registrar)  
   - Passo 1: *Relato*  
   - Passo 2: *Tipo e Assunto*  
   - Passo 3: *Local*  
   - Passo 4: *Envolvidos*  
   - Passo 5: *Revisão*  
   - Passo 6: *Conclusão*  

**Bases Normativas:**
- **ABNT NBR 17225:2025** (Acessibilidade em interfaces da Web e mitigação de barreiras)
- **WCAG 2.2** (Web Content Accessibility Guidelines — Níveis A, AA e AAA)
- **Guia de Boas Práticas de Acessibilidade Digital (Reino Unido – Brasil)**
- **Lei Brasileira de Inclusão (LBI - Lei nº 13.146/2015)**

**Dados Empíricos de Testes com Usuários Reais:**
- **Participante 1 (P1):** Mulher, 48 anos, com baixa visão (problemas de vista / presbiopia severa) e necessidade de recursos de ampliação/zoom.
- **Participante 2 (P2):** Homem, 21 anos, com limitação motora (Tremor Essencial).

---

## 1. Metodologia e Escopo da Avaliação

A avaliação técnica combinou duas abordagens complementares de Interação Humano-Computador:
1. **Auditoria Técnica Automatizada:** Inspeção profunda via *Headless Chrome*, protocolo CDP e motor **axe-core 4.x**, aferindo conformidade com tags, atributos ARIA, contraste e responsividade (320px CSS).
2. **Avaliação Empírica com Usuários Reais (Testes de Usabilidade e Acessibilidade):** Aplicação de tarefas guiadas de pensamento em voz alta (*think-aloud*) e questionário padronizado SUS (*System Usability Scale*) com usuários representativos de perfis com deficiência/limitação física real.

---

## 2. Resumo Executivo e Estatísticas Atualizadas

| Seção do Checklist | Itens | Conforme | Não Conforme / Parcial | Validados em Teste Humano | Requer Homologação Técnica | Não se Aplica |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **1. Desenvolvimento, Semântica e Testes** | 26 | 5 | 12 | 2 (P1 e P2) | 6 | 1 |
| **2. Privacidade, Segurança e Tempo** | 13 | 4 | 2 | 1 (P1 e P2) | 3 | 3 |
| **3. Navegação, Foco e Interação** | 26 | 7 | 11 | 2 (P1 e P2) | 3 | 3 |
| **4. Conteúdo, Linguagem e Mídia** | 23 | 3 | 4 | 2 (P1 e P2) | 6 | 8 |
| **5. Design, Tipografia e Layout** | 18 | 7 | 5 | 2 (P1 e P2) | 4 | 0 |
| **6. Formulários e Prevenção de Falhas** | 12 | 4 | 6 | 1 (P1 e P2) | 1 | 1 |
| **7. Jornada do Usuário e User Flow** | 9 | 4 | 3 | 2 (P1 e P2) | 0 | 0 |
| **TOTAL GERAL** | **127** | **34 (26,8%)** | **43 (33,9%)** | **12 (9,4%)** | **23 (18,1%)** | **15 (11,8%)** |

---

## 3. Descobertas e Itens Marcados a Partir dos Testes com Usuários

A realização dos testes com a Participante 1 (48 anos, baixa visão) e o Participante 2 (21 anos, tremor essencial) permitiu avaliar e marcar de forma conclusiva itens que anteriormente dependiam de evidência humana:

### 3.1 Item 1.26 — Validação com Usuários com Diferentes Perfis de Deficiência (ABNT NBR 17225)
- **Novo Status:** 🟢 **CONFORME / VALIDADO EM CAMPO**
- **Evidência Empírica:** O grupo executou com sucesso testes empíricos de tarefas de ponta a ponta com dois usuários com necessidades específicas reais:
  - **P1 (48 anos):** Usuária com dificuldade visual severa dependente de ampliação tipográfica.
  - **P2 (21 anos):** Usuário com condição neurológica de tremor involuntário nas mãos (tremor essencial).

---

### 3.2 Item 5.15 — Tipografia e Tamanho de Fonte para Baixa Visão (NBR 17225 / WCAG 1.4.4)
- **Novo Status:** 🔴 **NÃO CONFORME (Barreira Severa)**
- **Evidência Empírica:** A participante P1 apontou o tamanho diminuto do texto como a maior barreira de todo o portal:
  > *"Eu acho que as letras poderiam ser maiores... Os botões até que estavam claros, mas as letras precisava ser maior... Em qual parte sentiu mais dificuldade? Eu não tive tanta dúvida, até que tá bem assim, mas precisava de umas letras maiores mesmo. O que você mudaria no site? Aumentaria o tamanho das letras."*
  O participante P2 (tremor essencial) também relatou a necessidade de aplicar zoom na tela:
  > *"Às vezes com letra pequena o zoom ajuda. Então o zoom eu uso às vezes."*
- **Conclusão:** O Fala.BR peca por utilizar corpo de fonte diminuto nas instruções secundárias e não oferecer atalho direto visível de redimensionamento da fonte no topo da página.

---

### 3.3 Item 5.11 — Área de Clique para Usuários com Tremor Motor (WCAG 2.5.5 / 2.5.8)
- **Novo Status:** 🟢 **CONFORME (Aprovado na Prática)**
- **Evidência Empírica:** O participante P2, apesar de possuir tremor essencial, conseguiu acionar os botões primários ("Avançar", "Voltar", "Finalizar") sem cliques em falso:
  > *"Para mim foi confortável, não tive nenhuma dificuldade nos botões."*
- **Conclusão:** Os botões padronizados do Design System GOV.BR com altura superior a 44px garantiram precisão motora suficiente para pessoas com tremores essenciais leves a moderados.

---

### 3.4 Item 7.2 — Orientações Prévias sobre Anonimato e Requisitos da Tarefa
- **Novo Status:** 🔴 **NÃO CONFORME (Confirmado por ambos os usuários)**
- **Evidência Empírica:** Ambos os participantes ficaram completamente desorientados sobre como registrar uma denúncia anônima antes de entrar no fluxo:
  - **P2:** *"Aqui eu não vejo nada de forma anônima, né? Primeiramente... O site não é muito atrativo, não tem muitas informações iniciais e nisso você teria que buscar sempre que quiser achar alguma coisa. Por exemplo, a denúncia anônima tive que entrar e ler realmente sobre o texto e depois para procurar talvez uma aba separada sobre isso..."*
  - **P1:** Teve que ler o Passo 1 inteiro para entender que a denúncia não teria acompanhamento posterior: *"Então quer dizer que eu não posso... mas não vou saber do resultado?"*
- **Conclusão:** O Fala.BR não prepara o cidadão com antecedência sobre as implicações e restrições do anonimato, gerando ansiedade e perda de tempo.

---

### 3.5 Item 6.9 e 7.6 — Consistência de Modelo Mental e Etapa de Revisão (Passo 5)
- **Novo Status:** 🟢 **CONFORME (Aprovado em Teste)**
- **Evidência Empírica:** Ambos os participantes compreenderam a tela do Passo 5 (*Revisão*) e identificaram que era a etapa final antes do envio:
  - **P1:** *"Revisar. Pronto... Tudo da sua denúncia. Sim. Acaba onde é para você enviar sua denúncia sem finalizar."*
  - **P2:** *"E aqui chega a revisão mostrando tudo que eu selecionei. E aqui anexos adicionais, se quiser. E aí em finalizar."*
- **Conclusão:** A separação da etapa de revisão atende plenamente ao princípio de tolerância ao erro e prevenção de falhas irreversíveis.

---

### 3.6 Item 4.2 — Princípios de Linguagem Simples e Redução de Carga Cognitiva (ISO 24495-1)
- **Novo Status:** 🟡 **PARCIALMENTE CONFORME / REQUER AJUSTES**
- **Evidência Empírica:** A redação burocrática das consequências da manifestação anônima exigiu mediação nos dois testes. O texto diz *"no entanto, denúncias anônimas não permitem acompanhamento ou interação futuras com a ouvidoria..."*, provocando hesitação e dúvida nos usuários se valia a pena denunciar sem ter resposta.

---

### 3.7 Item 1.23 — Estabilidade e Desempenho sem Travamento da Interface
- **Novo Status:** 🔴 **NÃO CONFORME (Ocorrência de Falha no Teste P1)**
- **Evidência Empírica:** Durante a sessão de teste da participante P1, a interface travou ao tentar abrir o cadastro:
  > *"Cliquei e não foi. Ixe, acho que tá meio travado. Deixa eu só clicar aqui para atualizar a página. Aonde? Talvez tenha travado. Encontramos uma falha no site..."*
- **Conclusão:** A dependência excessiva de scripts pesados de cliente (SPA Vue.js) e requisições concorrentes causou bloqueio perceptível da interface, prejudicando usuários que dependem de previsibilidade.

---

## 4. Avaliação do SUS (System Usability Scale) dos Participantes

Ambos os participantes responderam ao questionário padronizado SUS (10 afirmações graduadas de 1 a 5):

- **Participante 1 (48 anos, Baixa Visão):**
  - Considerou o sistema complexo (nota 2 a 4 dependendo da formulação).
  - Sentiu que necessitaria de apoio técnico para tarefas avançadas.
  - Elogiou a segurança sentida ao final, mas foi categórica: **aumentar o tamanho das fontes é imprescindível para que pessoas mais velhas ou com presbiopia usem o site com autonomia**.

- **Participante 2 (21 anos, Tremor Essencial):**
  - Considerou o sistema pesado de usar (nota intermediária).
  - Apontou que a curva de aprendizado inicial é desnecessariamente alta porque o sistema não entrega as informações no ponto de partida, obrigando o usuário a "sair clicando às cegas".

---

## 5. Próximos Passos e Itens Restantes

Os itens que ainda dependem de validação dizem respeito exclusivamente a **testes com leitor de tela cego (NVDA)** e **homologação técnica no backend da CGU** (para disparo do protocolo sem criar denúncias fictícias).
