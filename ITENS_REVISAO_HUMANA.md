# Checklist de Itens que Demandam Revisão Humana Obrigatória

Este documento lista **todos os critérios do Checklist de Acessibilidade Digital** que **não podem ser plenamente auditados por ferramentas automatizadas** (como *axe-core*, *Lighthouse* ou analisadores de código estático) e que, por exigência da **ABNT NBR 17225:2025**, das **WCAG 2.2** e das boas práticas de Interação Humano-Computador (IHC), **exigem avaliação manual, cognitiva e empírica realizada por humanos**.

> **Fundamentação Técnica:** Ferramentas automatizadas capturam no máximo 30% a 40% das barreiras reais de acessibilidade. A conformidade plena com a Lei Brasileira de Inclusão (LBI - Lei 13.146/2015) exige a validação do desempenho real de pessoas com diferentes perfis de deficiência e o julgamento crítico de usabilidade.

---

## Sumário dos Itens por Seção

| Seção | Total de Itens que Exigem Revisão Humana |
| :--- | :---: |
| **1. Desenvolvimento, Semântica e Testes** | 6 itens |
| **2. Privacidade, Segurança e Controle de Tempo** | 4 itens |
| **3. Navegação, Foco e Interação** | 2 itens |
| **4. Conteúdo, Linguagem e Mídia** | 5 itens |
| **5. Design, Tipografia e Layout Responsivo** | 4 itens |
| **6. Formulários e Prevenção de Falhas** | 1 item |
| **7. Jornada do Usuário e Fluxos de Navegação** | 3 itens |
| **TOTAL GERAL** | **25 itens principais** |

---

## 1. Desenvolvimento, Semântica e Testes

### 1.1 Marcar textos especiais no código com tags semânticas específicas
- **Critério do Checklist:**  
  *Marcar textos especiais no código (ênfases, citações, abreviações) com as tags semânticas específicas para o propósito deles (ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 - Nível A).*
- **Por que a ferramenta não consegue avaliar:**  
  Um validador automático consegue saber se existem tags `<em>`, `<strong>`, `<q>`, `<blockquote>` ou `<abbr>`, mas **não compreende o significado semântico do texto**. Não consegue discernir se uma palavra destacada é uma citação textual, uma ênfase de entonação vocal ou mera estilização visual de design.
- **Como o humano deve avaliar:**  
  Revisão editorial do conteúdo por avaliador humano para verificar se trechos de leis, citações de manifestantes e termos enfatizados utilizam a semântica correta para que o leitor de tela aplique a entonação ou anúncio adequado.

---

### 1.2 Dar instruções claras de como operar componentes customizados complexos
- **Critério do Checklist:**  
  *Dar instruções claras de como operar componentes customizados que tenham interações muito complexas (ABNT NBR 17225; WCAG 2.2 C.S. 3.3.2 - Nível A).*
- **Por que a ferramenta não consegue avaliar:**  
  A ferramenta verifica apenas a presença de atributos de texto, mas não tem capacidade cognitiva de julgar se a explicação ("Como anexar arquivos", "Como selecionar múltiplos órgãos", "Como buscar tipologia") é pedagógica, clara e compreensível para usuários com deficiência intelectual ou leigos.
- **Como o humano deve avaliar:**  
  Teste de usabilidade com usuários reais ou avaliação heurística por especialista em UX, verificando se as instruções de uso dos componentes de upload e busca dinâmica são fáceis de entender.

---

### 1.3 Manter a ordem do código HTML intuitiva, lógica e correspondente à apresentação visual
- **Critério do Checklist:**  
  *Manter a ordem do código HTML intuitiva, lógica e correspondente à apresentação visual da tela (Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.3.2 - Nível A).*
- **Por que a ferramenta não consegue avaliar:**  
  A ferramenta não sabe qual é a intenção de leitura do usuário em layouts com cards flutuantes, colunas flexíveis (`flexbox`) ou grid CSS. Uma ordem pode ser válida sintaticamente no DOM, mas gerar uma experiência auditiva confusa no leitor de tela se a ordem de leitura divergir da ordem lógica esperada.
- **Como o humano deve avaliar:**  
  Navegar pela página desligando o CSS ou utilizando o modo linear do leitor de tela (navegação por setas no NVDA/VoiceOver), conferindo se a sequência auditiva faz sentido completo e coincide com a lógica visual.

---

### 1.4 Permitir alternar entre mouse, teclado, toque ou voz sem travar a interface
- **Critério do Checklist:**  
  *Permitir que o usuário alterne entre mouse, teclado, toque ou voz na mesma sessão sem que a interface trave (ABNT NBR 17225; WCAG 2.2 C.S. 2.5.6 - Nível AAA).*
- **Por que a ferramenta não consegue avaliar:**  
  Exige múltiplos periféricos e dispositivos de entrada conectados em hardware físico concorrente (tela sensível ao toque, software de reconhecimento de voz e teclado físico atuando simultaneamente).
- **Como o humano deve avaliar:**  
  Operar o sistema em um tablet híbrido ou notebook com tela touch, acionando um campo via toque, prosseguindo com digitação por teclado e usando comandos de voz (*Voice Access* / *Dragon NaturallySpeaking*), observando se a interface responde sem travamento ou perda de foco.

---

### 1.5 Realizar testes manuais rigorosos com leitores de tela desktop e mobile
- **Critério do Checklist:**  
  *Fazer testes manuais rigorosos navegando apenas pelo teclado e usando leitores de tela tanto no desktop (NVDA, Orca, VoiceOver) quanto no mobile (TalkBack, VoiceOver) (Guia do Reino Unido; ABNT NBR 17225).*
- **Por que a ferramenta não consegue avaliar:**  
  Simuladores automatizados não reproduzem a sintetização de voz, as pausas de pontuação, o anúncio de formulários em tempo real, as falhas de dicção e a experiência real de navegação cega.
- **Como o humano deve avaliar:**  
  Sessões de teste operadas exclusivamente via teclado com a tela desligada (ou cortina de tela ativada), navegando com **NVDA** no Windows e **TalkBack** no Android ao longo dos 6 passos do formulário Fala.BR.

---

### 1.6 Validar a usabilidade com pessoas com diferentes perfis de deficiência
- **Critério do Checklist:**  
  *Validar a usabilidade dos fluxos com pessoas com diferentes perfis de deficiência (sem visão, visão limitada, sem audição, restrições motoras e cognitivas) (Guia do Reino Unido; ABNT NBR 17225).*
- **Por que a ferramenta não consegue avaliar:**  
  Trata-se de um requisito empírico, social e metodológico. Não existe robô ou algoritmo capaz de substituir a vivência de uma pessoa surda, cega, autista ou com mobilidade reduzida.
- **Como o humano deve avaliar:**  
  Recrutamento de painel de testes com usuários reais representativos das diversas deficiências, com aplicação de testes de tarefas (ex.: "Registrar um elogio a um órgão federal") e coleta de percepções qualitativas de acessibilidade.

---

## 2. Privacidade, Segurança e Controle de Tempo

### 2.1 Projetar fluxos sem limite de tempo na sessão
- **Critério do Checklist:**  
  *Projetar fluxos que não tenham limite de tempo na sessão, a menos que sejam eventos em tempo real ou mídias sincronizadas (ABNT NBR 17225; WCAG 2.2 C.S. 2.2.1 - Nível A e 2.2.3 - Nível AAA).*
- **Por que a ferramenta não consegue avaliar:**  
  A expiração de sessão em sistemas governamentais é controlada pelo backend e por cookies de autenticação (Gov.br / AWS). Para atestar se o preenchimento de um relato longo expira a sessão, é necessário monitorar a página por minutos ou horas contínuas.
- **Como o humano deve avaliar:**  
  Preencher parte do formulário, pausar a interação por 20, 40 e 60 minutos e checar se o sistema preservou os dados ou encerrou a sessão sem aviso.

---

### 2.2 Oferecer aviso prévio de 20 segundos e opção de prorrogar o limite de tempo em até 10x
- **Critério do Checklist:**  
  *Se a tela tiver limite de tempo, oferecer ao usuário a opção de desativá-lo, ajustá-lo em até 10x ou prorrogá-lo mediante aviso prévio de 20 segundos por meio de uma ação simples (ABNT NBR 17225; WCAG 2.2 C.S. 2.2.1 - Nível A).*
- **Por que a ferramenta não consegue avaliar:**  
  Requer disparar ou aguardar o temporizador interno de inatividade e avaliar a usabilidade do diálogo modal que surge para prorrogação do prazo.
- **Como o humano deve avaliar:**  
  Aguardar a proximidade do encerramento da sessão, verificar se surge aviso audível e visual com pelo menos 20 segundos de antecedência e testar se é possível estender o tempo via teclado com apenas um clique.

---

### 2.3 Garantir que o usuário retome exatamente de onde parou após reautenticação sem perder dados
- **Critério do Checklist:**  
  *Se a sessão de login cair, garantir que o usuário retome exatamente de onde parou após a reautenticação, sem perder os dados já inseridos (ABNT NBR 17225; WCAG 2.2 C.S. 2.2.1 - Nível A e 2.2.5 - Nível AAA).*
- **Por que a ferramenta não consegue avaliar:**  
  Envolve credenciais reais de autenticação de cidadão no portal Gov.br, expiração forçada de token e redirecionamento com integridade de estado na aplicação Vue.
- **Como o humano deve avaliar:**  
  Autenticar com conta Gov.br, digitar um relato no Passo 1, avançar até o Passo 3, forçar a limpeza do cookie de sessão, clicar em autenticar novamente e verificar se o formulário manteve intactos os dados preenchidos anteriormente.

---

### 2.4 Exibir alertas de segurança em linguagem clara sem depender só de cor e sem vazar dados
- **Critério do Checklist:**  
  *Exibir alertas de segurança usando textos claros (não dependendo apenas de cor, som ou ícone) e garantir que as mensagens não exponham dados sensíveis ou códigos do sistema (ABNT NBR 17225; WCAG 2.2 C.S. 1.4.1 - Nível A).*
- **Por que a ferramenta não consegue avaliar:**  
  A ferramenta não sabe avaliar se uma mensagem como "Falha no token de autenticação JWT" é técnica demais ou se expõe vulnerabilidades, nem julga a clareza da linguagem para o cidadão comum.
- **Como o humano deve avaliar:**  
  Simular entradas maliciosas ou timeouts de rede e avaliar se as mensagens de erro retornadas são amigáveis, não exibem stack traces do servidor e informam com precisão como o cidadão deve proceder.

---

## 3. Navegação, Foco e Interação

### 3.1 Identificar ícones e componentes que realizam a mesma ação sempre de forma consistente
- **Critério do Checklist:**  
  *Identificar ícones e componentes que realizam a mesma ação sempre de um jeito padronizado e consistente (ABNT NBR 17225; WCAG 2.2 C.S. 3.2.4 - Nível AA).*
- **Por que a ferramenta não consegue avaliar:**  
  Identificar consistência semântica e semiótica entre dezenas de páginas (ex.: conferir se o ícone de interrogação sempre abre FAQ e o ícone de lixeira sempre exclui) exige juízo de consistência global de design system.
- **Como o humano deve avaliar:**  
  Mapeamento de todos os ícones funcionais em um guia de componentes e checagem cruzada da uniformidade de rótulos visuais e alternativos ao longo das jornadas.

---

### 3.2 Destacar links no meio de textos usando sublinhado e contraste além da cor
- **Critério do Checklist:**  
  *Destacar hiperlinks que ficam no meio de blocos de texto usando sublinhado e contraste, sem depender unicamente da cor azul para diferenciá-los (Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.4.1 - Nível A).*
- **Por que a ferramenta não consegue avaliar:**  
  A ferramenta automática frequentemente confunde links contidos em listas ou botões estilizados com links em parágrafos de texto corrido, e não testa confiavelmente os estados dinâmicos (`:hover`, `:focus`, `:active`).
- **Como o humano deve avaliar:**  
  Inspeção visual direta de textos explicativos de termos e condições, verificando se há sublinhado permanente (`text-decoration: underline`) ou indicador adicional que não dependa exclusivamente de tons azuis.

---

## 4. Conteúdo, Linguagem e Mídia

### 4.1 Escrever adotando princípios de Linguagem Simples (ISO 24495-1)
- **Critério do Checklist:**  
  *Escrever adotando os princípios de Linguagem Simples (ISO 24495-1): frases curtas (15 a 20 palavras), ordem direta, pontuação clara e sem uso de ambiguidades ou figuras de linguagem rebuscadas (Guia do Reino Unido; ABNT NBR 17225).*
- **Por que a ferramenta não consegue avaliar:**  
  Embora existam índices matemáticos de legibilidade (como Flesch), eles não julgam a clareza conceitual, a ambiguidade jurídica de instruções do serviço público e a adequação sociocultural da mensagem.
- **Como o humano deve avaliar:**  
  Revisão textual baseada nas diretrizes da ISO 24495-1 por profissional de comunicação pública ou redação UX, simplificando frases longas e jargões burocráticos.

---

### 4.2 Oferecer versão simplificada caso o conteúdo exija nível de leitura avançado
- **Critério do Checklist:**  
  *Oferecer uma versão simplificada ou material de apoio em texto caso o conteúdo original exija um nível de leitura técnico ou muito avançado (ABNT NBR 17225; WCAG 2.2 C.S. 3.1.5 - Nível AAA).*
- **Por que a ferramenta não consegue avaliar:**  
  Julgar se uma instrução sobre a Lei de Acesso à Informação ou Ouvidoria Pública exige conhecimentos técnicos prévios é uma decisão pedagógica e de experiência do usuário.
- **Como o humano deve avaliar:**  
  Verificar se há glossários, resumos em linguagem cidadã ou cards didáticos explicando passo a passo o significado de termos complexos.

---

### 4.3 Apresentar informações principais em mais de um formato (texto, áudio, gráfico)
- **Critério do Checklist:**  
  *Apresentar as informações principais em mais de um formato (texto, áudio, gráfico) para apoiar o entendimento de pessoas neurodiversas ou com baixo letramento (Guia do Reino Unido; ABNT NBR 17225).*
- **Por que a ferramenta não consegue avaliar:**  
  A ferramenta não tem como discernir se uma explicação exclusivamente textual sobre como denunciar um ato ilícito deveria ser complementada por um infográfico ou áudio instrucional.
- **Como o humano deve avaliar:**  
  Avaliação de design de serviço público para identificar se os pontos mais críticos da jornada oferecem alternativas para cidadãos com dificuldades de leitura.

---

### 4.4 Evitar usar imagens contendo texto (banners com frases coladas em imagem)
- **Critério do Checklist:**  
  *Evitar usar imagens contendo texto (banners com frases coladas). Se forem estritamente essenciais (como logotipos), elas devem conter um alt idêntico ao texto da imagem (Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.4.5 - Nível AA e 1.4.9 - Nível AAA).*
- **Por que a ferramenta não consegue avaliar:**  
  A ferramenta automática não lê o conteúdo pixelizado dentro de arquivos PNG/JPEG/WEBP para comparar se o texto impresso na imagem é idêntico ou se poderia ter sido construído em HTML/CSS real.
- **Como o humano deve avaliar:**  
  Inspeção visual humana dos banners promocionais, logotipos e ilustrações da página inicial, garantindo que frases institucionais sejam texto real em HTML.

---

### 4.5 Aplicar padrão CamelCase em hashtags e moderar o uso de emojis
- **Critério do Checklist:**  
  *Aplicar o padrão CamelCase ao criar hashtags (ex: #AcessibilidadeDigital) para melhorar a dicção dos leitores de tela e moderar o uso de emojis no meio dos textos (Guia do Reino Unido; ABNT NBR 17225).*
- **Por que a ferramenta não consegue avaliar:**  
  Exige conferência contextual da redação de eventuais postagens, avisos e campanhas na interface, avaliando se leitores de tela pronunciam corretamente as palavras compostas.
- **Como o humano deve avaliar:**  
  Ouvir com leitor de tela a leitura de eventuais hashtags e textos decorados com emojis para garantir que a mensagem permaneça inteligível.

---

## 5. Design, Tipografia e Layout Responsivo

### 5.1 Testar paleta de cores em simuladores para diferentes tipos de daltonismo
- **Critério do Checklist:**  
  *Testar a paleta cromática do site em simuladores para validar se as informações permanecem legíveis para diferentes tipos de daltonismo (Guia do Reino Unido; ABNT NBR 17225).*
- **Por que a ferramenta não consegue avaliar:**  
  Ferramentas automáticas calculam razões numéricas de contraste, mas não avaliam a percepção subjetiva e a perda de significado em casos de Protanopia (dificuldade com vermelho), Deuteranopia (verde) e Tritanopia (azul/amarelo).
- **Como o humano deve avaliar:**  
  Utilizar simuladores visuais (como o recurso nativo de emulação de deficiências visuais do Chrome DevTools / *Color Oracle*), inspecionando cada tela para checar se alertas e botões continuam distinguíveis.

---

### 5.2 Checar contraste mínimo em fotos e fundos com degradê
- **Critério do Checklist:**  
  *Checar o contraste mínimo em fotografias e fundos degradê analisando os três pontos da área de texto: tom mais claro, tom médio e tom escuro (Guia do Reino Unido).*
- **Por que a ferramenta não consegue avaliar:**  
  Robôs de acessibilidade frequentemente falham ao avaliar texto sobreposto a imagens de fundo com gradientes CSS (`linear-gradient`) ou fotografias, reportando "impossível determinar contraste".
- **Como o humano deve avaliar:**  
  Utilizar uma ferramenta conta-gotas de contraste (*Colour Contrast Analyser - CCA*) e medir manualmente os pontos mais críticos da imagem em relação à cor da tipografia.

---

### 5.3 Configurar CSS para que linhas de texto tenham no máximo 80 caracteres de largura
- **Critério do Checklist:**  
  *Configurar o CSS para que as linhas de texto tenham no máximo 80 caracteres de largura, poupando o cansaço visual de movimentos de leitura muito longos na tela (Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.4.8 - Nível AAA e 1.4.10 - Nível AA).*
- **Por que a ferramenta não consegue avaliar:**  
  A largura da linha em caracteres depende do tamanho da janela do navegador, do monitor ultrawide do usuário e das propriedades dinâmicas do contêiner.
- **Como o humano deve avaliar:**  
  Inspecionar as folhas de estilo dos parágrafos de ajuda e textos longos em monitores de alta resolução (1080p, 1440p, 4K), verificando se o CSS estabelece largura máxima (`max-width: 70ch` a `80ch`).

---

### 5.4 Garantir texto íntegro com ajustes pesados de entrelinhas (1,5x) e espaçamento entre letras
- **Critério do Checklist:**  
  *Garantir que o texto continue íntegro se o usuário aplicar ajustes pesados nas propriedades da fonte, como: entrelinhas de 1,5x, espaçamento entre parágrafos de 2x, ou distância aumentada entre as letras (ABNT NBR 17225; WCAG 2.2 C.S. 1.4.8 - Nível AAA e 1.4.12 - Nível AA).*
- **Por que a ferramenta não consegue avaliar:**  
  A ferramenta não avalia o comportamento dinâmico quando um usuário com dislexia injeta estilos personalizados no navegador.
- **Como o humano deve avaliar:**  
  Ativar o script de teste de espaçamento de texto da WCAG (Bookmarklet de Text Spacing: `line-height: 1.5`, `letter-spacing: 0.12em`, `word-spacing: 0.16em`) e conferir visualmente se caixas de texto cortam ou sobrepõem palavras no formulário.

---

## 6. Formulários e Prevenção de Falhas

### 6.1 Sugerir caminhos fáceis e formatados de como o usuário resolve o erro
- **Critério do Checklist:**  
  *Além de apontar o erro, o sistema deve sugerir caminhos fáceis e formatados de como o usuário resolve aquele problema (desde que a dica não exponha falhas de segurança) (Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 3.3.3 - Nível AA).*
- **Por que a ferramenta não consegue avaliar:**  
  Validadores automáticos verificam apenas se a mensagem de erro existe no código, mas são incapazes de avaliar se a instrução orienta com empatia como corrigir o problema (ex.: indicar o padrão correto de data ou como resumir um relato prolixo).
- **Como o humano deve avaliar:**  
  Forçar propositalmente erros de preenchimento em todos os campos do fluxo e julgar a eficácia e clareza das mensagens de correção exibidas.

---

## 7. Jornada do Usuário e Fluxos de Navegação

### 7.1 Exibir telas de confirmação claras (Mensagens de Sucesso) após a conclusão do fluxo
- **Critério do Checklist:**  
  *Exibir telas de confirmação claras (Mensagens de Sucesso) após a conclusão do fluxo, resumindo brevemente o que foi feito, o que vai acontecer a seguir (ex: "Você receberá um e-mail em 5 minutos") e oferecendo atalhos lógicos para a próxima ação.*
- **Por que a ferramenta não consegue avaliar:**  
  No portal Fala.BR, submeter o Passo 6 em ambiente de produção gera uma **manifestação oficial registrada na Controladoria-Geral da União**, o que incorreria no disparo de denúncias ou ouvidorias fictícias em banco governamental real. Além disso, avaliar a clareza dos prazos e instruções pós-registro exige leitura humana.
- **Como o humano deve avaliar:**  
  Acesso a ambiente de homologação (*staging*) da CGU por técnicos autorizados, submetendo manifestação simulada e inspecionando a página de comprovante e número de protocolo com leitor de tela.

---

### 7.2 Projetar *Empty States* instrutivos e acolhedores com botão de ação
- **Critério do Checklist:**  
  *Projetar Empty States (telas sem conteúdo, como um carrinho vazio ou uma lista de favoritos sem itens) de forma instrutiva e acolhedora, explicando o que deveria estar ali e exibindo um botão de ação para ajudar o usuário a começar a popular aquela tela.*
- **Por que a ferramenta não consegue avaliar:**  
  A ferramenta não entende o conceito de acolhimento visual e empatia de uma tela sem dados (ex.: um histórico de manifestações vazio para um usuário recém-cadastrado).
- **Como o humano deve avaliar:**  
  Acessar o painel do cidadão com uma conta nova sem manifestações prévias e verificar se a tela orienta educadamente como registrar a primeira manifestação.

---

### 7.3 Minimizar as trocas de contexto (*context switching*)
- **Critério do Checklist:**  
  *Minimizar as trocas de contexto (context switching): evitar obrigar o usuário a sair do aplicativo, ir para o e-mail, copiar um código e voltar para o aplicativo no meio de um fluxo crítico, a menos que seja estritamente necessário para segurança.*
- **Por que a ferramenta não consegue avaliar:**  
  A alternância de contexto depende da jornada completa do usuário envolvendo múltiplos canais (navegador, aplicativo gov.br no celular para duplo fator de autenticação, checagem de código SMS ou e-mail).
- **Como o humano deve avaliar:**  
  Mapeamento de jornada do usuário medindo a carga cognitiva e o número de etapas externas necessárias para autenticar e concluir a manifestação.

---

## 8. Recomendações Metodológicas para a Equipe de IHC

Para cumprir plenamente os requisitos da disciplina de IHC e as diretrizes do Governo Digital:
1. **Ambiente Controlado:** Solicitar acesso ao ambiente de treinamento/homologação do Fala.BR para executar o fluxo até a geração final do protocolo sem impactar o serviço público real.
2. **Protocolo com Usuários:** Aplicar o protocolo de teste com pelo menos um usuário de leitor de tela (NVDA) e um usuário com baixa visão ou restrição motora.
3. **Checklist Imparcial:** Utilizar este documento como roteiro de homologação manual complementar aos relatórios do axe-core e Lighthouse.
