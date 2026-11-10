# Relatório de Teste de Usabilidade com Usuário Real — Portal Fala.BR

**Disciplina:** Interação Humano-Computador (IHC) — Semestre 2026.2  
**Professora:** Rejane M. C. Figueiredo  
**Instituição:** Universidade de Brasília (UnB)  
**Grupo:** 03  
**Plataforma Avaliada:** Portal Fala.BR (Controladoria-Geral da União)  
**URLs Avaliadas:**
* Página Inicial: `https://falabr.cgu.gov.br/v2/`
* Fluxo de Registro de Manifestação: `https://falabr.cgu.gov.br/v2/manifestacoes/registrar`

---

## 1. Perfil dos Participantes

Em consonância com as recomendações da **Seção 2.2 da proposta de trabalho**, o grupo selecionou usuários reais que se enquadram no perfil de cidadãos com demandas de acessibilidade e tecnologias assistivas:

* **Participante 1 (P1 — Estudo de Caso Principal):**
  * **Idade:** 48 anos.
  * **Gênero:** Feminino.
  * **Perfil Funcional:** Baixa visão e presbiopia severa; necessita rotineiramente de ampliação tipográfica no navegador e aplicação de zoom na tela.
  * **Uso da Internet:** Diário, para pesquisas e serviços básicos.
  * **Familiaridade com o Fala.BR:** Nunca havia utilizado o sistema.
  * **Vínculo Acadêmico:** Não estuda na UnB, não cursa a disciplina e não possui vínculo com os integrantes do grupo.

* **Participante 2 (P2 — Análise Complementar de Controle):**
  * **Idade:** 21 anos.
  * **Gênero:** Masculino.
  * **Perfil Funcional:** Limitação motora nos membros superiores (Tremor Essencial); utiliza navegação híbrida compensatória com mouse e **uso intensivo da tecla TAB no teclado** para evitar cliques falso-positivos em áreas pequenas.
  * **Uso da Internet:** Diário (pesquisa, entretenimento e estudos).
  * **Familiaridade com o Fala.BR:** Nunca havia utilizado nem ouvido falar da plataforma.

---

## 2. Síntese do Roteiro e Metodologia da Sessão

O teste seguiu o protocolo adaptado de Rubin e Chisnell (2008) e Nielsen (1993), estruturado nas etapas:
1. **Acolhida e assinatura do Termo de Consentimento Livre e Esclarecido (TCLE)** em duas vias (com autorização expressa para gravação de tela e áudio).
2. **Entrevista inicial** de caracterização (idade, frequência de internet e tecnologias assistivas).
3. **Instrução de pensar em voz alta (*think-aloud*)**.
4. **Execução de três tarefas representativas formuladas como cenários** (sem dados pessoais reais e pausadas na tela de revisão).
5. **Aplicação do questionário System Usability Scale (SUS)** imediatamente após as tarefas.
6. **Entrevista final** qualitativa e encerramento.

### 2.1 Ensaio Piloto e Política de Tempo-Limite
O roteiro foi previamente testado em ensaio piloto por um membro do grupo em 05/11/2026 para validação das ferramentas de gravação e cronometragem dos **tempos de referência** (T1: 40s; T2: 55s; T3: 70s). Em conformidade estrita com a **Seção 2.2 da especificação**, por se tratarem de pessoas com deficiência, **o tempo-limite não foi aplicado como critério eliminatório de corte**, sendo o tempo cronometrado em vídeo utilizado apenas como dado descritivo da interação com o sistema.

---

## 3. Resultados por Tarefa e Métricas de Usabilidade

A cronometragem foi realizada a partir das gravações em vídeo de alta precisão das sessões, classificando desfechos e erros conforme as definições normativas da Seção 3 da proposta de trabalho:

### 3.1 Tabela de Resultados por Tarefa e Participante

| Participante | Tarefa | Início | Fim | Tempo na Tarefa | Desfecho Oficial | Nº de Erros | Hesitações e Comportamento Observado |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| **P1 (Baixa Visão)** | **Tarefa 1** | 02:24 | 05:15 | **171 s** (2m51s) | **Sucesso com ajuda** | **1** | Acessou menu incorreto ("Dados Abertos"); orientador interveio para retornar; retornou à Home em 03:30; **o site travou** e exigiu recarregar a página (F5). |
| **P1 (Baixa Visão)** | **Tarefa 2** | 06:40 | 08:20 | **100 s** (1m40s) | **Sucesso sem ajuda** | **1** | Clicou repetidas vezes no campo dropdown sem digitar; demorou a compreender que o seletor exigia digitação prévia para exibir a lista. |
| **P1 (Baixa Visão)** | **Tarefa 3** | 09:26 | 11:30 | **124 s** (2m04s) | **Sucesso sem ajuda** | **0** | Preencheu o relato de teste, indicou Brasília e revisou as informações no Passo 5 com sucesso. |
| **P2 (Tremor Essencial)** | **Tarefa 1** | 02:58 | 04:15 | **77 s** (1m17s) | **Sucesso sem ajuda** | **1** | Verbalizou ausência de informações sobre denúncia anônima na Home; acessou caminho incorreto via Tab, mas retornou sozinho. |
| **P2 (Tremor Essencial)** | **Tarefa 2** | 04:58 | 05:45 | **47 s** (0m47s) | **Sucesso sem ajuda** | **0** | Usou a tecla Tab para focar o campo e digitou "Universidade de Brasília" com agilidade. |
| **P2 (Tremor Essencial)** | **Tarefa 3** | 07:05 | 08:10 | **65 s** (1m05s) | **Sucesso sem ajuda** | **0** | Alternou entre Tab e cliques no mouse; confirmou a tela de revisão no Passo 5 com firmeza. |

### 3.2 Taxa de Sucesso Consolidada (Nielsen & Budiu, 2001)
* **Sucesso sem Ajuda:** $5 / 6 = \mathbf{83,3\%}$ (5 tarefas concluídas de forma autônoma).
* **Sucesso com Ajuda:** $1 / 6 = \mathbf{16,7\%}$ (Tarefa 1 de P1, com intervenção do facilitador aos `03:29`).
* **Taxa de Falha:** $0 / 6 = \mathbf{0,0\%}$ (nenhuma desistência).

### 3.3 Análise Temporal (P1 vs. P2 vs. Tempo de Referência)
* **Tempo Total de Tarefas Ativas:** P1 despendeu **395 segundos (6m35s)** contra **189 segundos (3m09s)** de P2.
* A participante com baixa visão exigiu **mais que o dobro do tempo (+109,0%)** em relação ao participante com limitação motora. Essa disparidade foi impulsionada pela barreira tipográfica (tamanho de fonte insuficiente), pela falta de feedback do seletor suspenso no Passo 2 e pela necessidade de recarregar a página travada na Tarefa 1.

---

## 4. Avaliação Psicométrica: Escore SUS (System Usability Scale)

O questionário padronizado SUS (Lourenço, Carmona & Lopes, 2022) foi aplicado rigorosamente antes da entrevista final, evitando qualquer contaminação das notas:

| Item da System Usability Scale (SUS) | Polaridade | Nota Bruta P1 (1 a 5) | Contribuição P1 (0 a 4) | Nota Bruta P2 (1 a 5) | Contribuição P2 (0 a 4) | Média Ajustada (0 a 4) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| 1. Gostaria de usar frequentemente | Positiva (+) | 2 | 1,0 | 2 | 1,0 | **1,00** |
| 2. Achei o sistema desnecessariamente complexo | Negativa (-) | 2 | 3,0 | 1 | 4,0 | **3,50** |
| 3. Achei o sistema fácil de usar | Positiva (+) | 3 | 2,0 | 3 | 2,0 | **2,00** |
| 4. Precisaria de ajuda de uma pessoa técnica | Negativa (-) | 2 | 3,0 | 1 | 4,0 | **3,50** |
| 5. Funções bem integradas | Positiva (+) | 3 | 2,0 | 2 | 1,0 | **1,50** |
| 6. Apresenta muita inconsistência | Negativa (-) | 1 | 4,0 | 1 | 4,0 | **4,00** |
| 7. A maioria das pessoas aprende a usar rápido | Positiva (+) | 5 | 4,0 | 2 | 1,0 | **2,50** |
| 8. Achei o sistema muito pesado para usar | Negativa (-) | 2 | 3,0 | 3 | 2,0 | **2,50** |
| 9. Me senti muito seguro usando o sistema | Positiva (+) | 4 | 3,0 | 4 | 3,0 | **3,00** |
| 10. Tive que aprender muitas coisas antes | Negativa (-) | 1 | 4,0 | 1 | 4,0 | **4,00** |
| **Soma das Contribuições (Máx: 40)** | — | — | **29,0** | — | **26,0** | **27,50** |
| **Escore SUS Final (Soma $\times$ 2,5)** | — | — | **72,5 pontos** | — | **65,0 pontos** | **68,75 pontos** |

* **Interpretação Normativa dos Resultados:**
  * Conforme as diretrizes de Sauro (2011), os escores do SUS são expressos em **pontos** (escala de 0 a 100) e **não como porcentagem**.
  * O escore médio de **68,75 pontos** enquadra a usabilidade do Fala.BR no **Conceito C (Marginal / Regular)**, alinhando-se exatamente à média global histórica de usabilidade (68,0 pontos).
  * **O Paradoxo da Auto-Culpabilização:** Embora P1 tenha sofrido muito mais fricções práticas e demorado o dobro do tempo, atribuiu um escore maior (**72,5**) que P2 (**65,0**). Isso se deveu à nota máxima (5) no Item 7, uma vez que a usuária atribuiu suas dificuldades à sua própria condição visual (*"é porque eu não enxergo direito"*). Já P2 avaliou o sistema criticamente, pontuando que o cidadão comum se perderia na busca de informações desorganizadas na Home.

---

## 5. Síntese das Entrevistas Inicial e Final

### 5.1 Entrevista Inicial
* **P1 (Baixa Visão):** Utiliza computador e smartphone diariamente, mas depende constantemente de ampliar textos e aplicar zoom. Não conhecia o Fala.BR e nunca havia aberto manifestações em ouvidorias federais.
* **P2 (Tremor Essencial):** Utiliza internet diariamente com facilidade. Para atenuar a instabilidade motora nas mãos, adota rotineiramente a navegação por teclado (tecla Tab) para focar campos de texto e evitar cliques fora do alvo.

### 5.2 Entrevista Final
* **P1 (Baixa Visão):** Declarou que a estrutura visual geral é compreensível, mas apontou com ênfase a tipografia reduzida como o maior obstáculo: *"Eu acho que as letras poderiam ser maiores. Os botões até que estavam claros, mas as letras precisava ser maior. Aumentaria o tamanho das letras"* (repetido 4 vezes na transcrição).
* **P2 (Tremor Essencial):** Elogiou o tamanho físico dos botões e a consistência visual, mas criticou severamente a arquitetura de informação inicial: *"O site em si não é muito atrativo, não tem muitas informações iniciais e nisso você teria que buscar sempre que quiser achar alguma coisa. [...] Primeiro, talvez seja essa de ter que ir atrás de informação e sair clicando nas coisas para achar o que realmente quer"*.

---

## 6. Tabela Oficial de Problemas de Usabilidade e Severidade

A tabela a seguir consolida os problemas empíricos observados durante as sessões, classificados segundo a **Escala de Severidade de Nielsen (1994)** (0 = Não é problema; 1 = Cosmético; 2 = Menor; 3 = Grave; 4 = Catastrófico):

| ID | Descrição do Problema | Local na Interface | Evidência Empírica na Sessão (Minuto e Fala) | Severidade (Nielsen) |
| :-: | :--- | :--- | :--- | :---: |
| **PR-01** | **Instabilidade e travamento de tela exigindo F5, sem rascunho automático** | Transição Home $\rightarrow$ Passo 1 | P1 (03:29): *"Cliquei e não foi. Ixe, acho que tá meio travado. Deixa eu só clicar aqui para atualizar a página... Encontramos uma falha no site"*. | **4 (Catastrófico)** |
| **PR-02** | **Ausência de identificação visível sobre canal de denúncia anônima na Home** | Página Inicial (`/v2/`) | P2 (03:37): *"Aqui eu não vejo nada de forma anônima, né? Primeiramente"*; P1 (02:24): Acessou menu incorreto de Dados Abertos por desorientação. | **3 (Grave)** |
| **PR-03** | **Seletor suspenso de órgãos exige digitação sem instruir o usuário** | Passo 2: Tipo e Assunto | P1 (06:40): *"Federal e não tá indo aqui. Ah, tem digitar nome. Foi, foi errado"*. Clicou seguidas vezes esperando abertura de lista. | **3 (Grave)** |
| **PR-04** | **Sobrecarga de foco via Tab por falta de link de salto (*Skip Link*)** | Cabeçalho e Menus | P2 (02:58 a 04:15): Necessitou teclar Tab dezenas de vezes por elementos repetidos antes de atingir a área central do formulário. | **3 (Grave)** |
| **PR-05** | **Tamanho padrão de fonte reduzido para usuários com baixa visão** | Todas as telas do fluxo | P1 (16:04): *"As letras precisava ser maior... precisava de umas letras maiores mesmo... aumentaria o tamanho das letras"*. | **2 (Menor)** / **3 (Grave)** |
| **PR-06** | **Campo de relato sem rótulo externo fixo (depende apenas de placeholder)** | Passo 1: Relato | P1 (05:13): Teve hesitação prolongada ao ler a caixa de texto antes de digitar, pois a dica interna some no primeiro caractere. | **2 (Menor)** |

---

## 7. Relação entre os Problemas Observados e o Pocket de Acessibilidade

O cruzamento entre as evidências empíricas e o **Guia/Checklist de Acessibilidade do Grupo 03** demonstra que as principais barreiras enfrentadas pelos usuários já haviam sido diagnosticadas pela inspeção técnica:

1. **PR-01 vinculado aos Itens 28, 29 e 123 do Pocket (Não Conformes):** A ausência de persistência de dados em `localStorage`/`sessionStorage` transforma qualquer instabilidade ou erro de rede em perda irreparável de esforço para quem digita com lentidão.
2. **PR-02 vinculado ao Item 121 do Pocket (Não Conforme):** O pocket atesta a inexistência de orientações prévias na Home sobre denúncia anônima, forçando ambos os participantes ao mesmo erro de rota inicial.
3. **PR-03 vinculado ao Item 111 do Pocket (Parcialmente Conforme):** O componente customizado de autocompletar não disponibiliza texto de instrução permanente externo, violando o princípio de previsibilidade.
4. **PR-04 vinculado aos Itens 42, 46 e 49 do Pocket (Não Conformes):** O pocket registrou ausência de Skip Link, barra superior fixa cobrindo campos e ordem de tabulação poluída por nós decorativos.
5. **PR-05 vinculado ao Item 104 do Pocket (Não Conforme):** A reprovação técnica da escala tipográfica padrão confirmou-se plenamente na queixa central da Participante 1.
6. **PR-06 vinculado aos Itens 109 e 110 do Pocket (Não Conformes):** O `<textarea>` do relato não possui tag `<label for>` vinculada, dependendo unicamente de placeholder cinza de baixo contraste.

---

## 8. As Cinco Recomendações Priorizadas

Com base na gravidade do impacto na vida do cidadão e na viabilidade técnica, o grupo estabelece as 5 melhorias prioritárias para o Fala.BR:

1. **Recomendação 1 (Prioridade 1 — Vinculada ao PR-01 e Itens 28, 29, 123):**
   * *Ação:* Implementar mecanismo de salvamento automático (*auto-save*) do texto do relato em armazenamento local do navegador (`sessionStorage`), impedindo a perda de dados em caso de recarregamento (F5), travamento ou queda de conexão.
2. **Recomendação 2 (Prioridade 2 — Vinculada ao PR-02 e Item 121):**
   * *Ação:* Incluir na página inicial um card e atalho de destaque com a inscrição clara: *"Registrar Manifestação Anônima"*, acompanhado de breve explicação das regras de não acompanhamento antes do ingresso no formulário.
3. **Recomendação 3 (Prioridade 3 — Vinculada ao PR-03 e Item 111):**
   * *Ação:* Adicionar rótulo descritivo e dica permanente junto ao campo de seleção de órgãos no Passo 2 (ex: *"Digite as primeiras letras do órgão para buscar"*), evitando que usuários fiquem clicando em vão esperando uma lista estática.
4. **Recomendação 4 (Prioridade 4 — Vinculada ao PR-04 e Itens 42, 46, 49):**
   * *Ação:* Inserir como primeiro elemento interativo do código o link de salto *"Pular para o conteúdo principal"*, ajustar o espaçamento superior (`scroll-margin-top`) para não encobrir o foco atrás da barra fixa e limpar elementos decorativos da ordem de tabulação.
5. **Recomendação 5 (Prioridade 5 — Vinculada ao PR-05 e Item 104):**
   * *Ação:* Aumentar a escala tipográfica padrão do corpo de texto para o equivalente a 16px/18px e incluir botões nativos de redimensionamento de fonte (`A+` e `A-`) visíveis no cabeçalho ao lado do botão de Alto Contraste.

---

## 9. Declaração do Uso de Inteligência Artificial

Em conformidade estrita com a **Seção 6 da proposta de trabalho**, declara-se que foram utilizadas ferramentas de inteligência artificial generativa (Antigravity / Gemini) exclusivamente para apoio na sumarização das transcrições gravadas, formatação de tabelas em Markdown e validação algébrica das equações do questionário SUS. Todos os tempos cronometrados, citações de áudio/vídeo, atribuições de severidade e análises de conformidade com o pocket foram revisados, verificados e validados integralmente pelos estudantes responsáveis com base nas evidências empíricas reais das sessões.

---

## 10. Links e Acesso às Evidências

* **Gravações em Vídeo das Sessões:**
  * Sessão Participante 1 (Baixa Visão): [Gravação em Vídeo — P1 (Google Drive)](https://drive.google.com/file/d/1n98wHccjvb11rqECNBev6Y7TchUeYsHc/view?usp=sharing)
  * Sessão Participante 2 (Tremor Essencial): [Gravação em Vídeo — P2 (Google Drive)](https://drive.google.com/file/d/1g2Wuhr3AbpEhassPUMrLsV2r0oibk5Mq/view?usp=sharing)
* **Termos de Consentimento Assinados (PDF):**
  * [`Termo_Consentimento_Participante_1_assinado.pdf`](./entrevistas/Termo_Consentimento_Participante_1_assinado.pdf)
  * [`Termo_Consentimento_Participante_2_assinado.pdf`](./entrevistas/Termo_Consentimento_Participante_2_assinado.pdf)
* **Roteiro Completo Aplicado (Anexo):**
  * [`roteiro_entrevista.md`](./entrevistas/roteiro_entrevista.md)
* **Transcrições Integrais Cronometradas:**
  * [`transcricao_participante_1.md`](./entrevistas/transcricao_participante_1.md)
  * [`transcricao_participante_2.md`](./entrevistas/transcricao_participante_2.md)
