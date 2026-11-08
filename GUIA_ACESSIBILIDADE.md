# Checklist de Acessibilidade Digital

Criar um ambiente digital acessível exige entender de verdade as barreiras tecnológicas, cognitivas e sensoriais que milhões de pessoas enfrentam todos os dias. Este checklist não é voltado para um sistema específico, mas funciona como um guia prático para avaliar sistemas. Ele reúne as exigências legais e de usabilidade para qualquer interface web, garantindo que a acessibilidade e experiência seja tratada como pilar estrutural do projeto.

---

## Nossas Três Referências Fundamentais

Nosso guia foi montado com base em três documentos principais que se complementam, unindo a obrigação legal à excelência na experiência do usuário (UX):

1. **ABNT NBR 17225:2025**: Nossa base técnica e legal no Brasil. Ela define os requisitos para mitigar barreiras, alinhando-se à Lei Brasileira de Inclusão (LBI), com foco no desempenho real das pessoas (navegar sem ver, sem ouvir, ou com limitações motoras e cognitivas).
2. **WCAG 2.2**: O padrão-ouro mundial mantido pelo W3C. Ele garante que nossas recomendações sejam agnósticas a dispositivos (*device-agnostic*), validando os quatro princípios de que a web deve ser: Perceptível, Operável, Compreensível e Robusta.
3. **Guia de Boas Práticas (Reino Unido - Brasil)**: É o documento que traduz as regras técnicas rígidas para o dia a dia ágil de gestão, design e desenvolvimento. Ele traz a abordagem humana, focando na cultura da equipe e na redução da carga cognitiva.

---

## 1. Desenvolvimento, Semântica e Testes

- [ ] Usar um título (`<title>`) único e descritivo em cada página para identificar onde o usuário está no site (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.2 - Nível A*).
- [ ] Declarar o idioma principal na tag raiz (`<html lang="...">`) e identificar programaticamente os trechos do texto que estiverem em idiomas estrangeiros (*ABNT NBR 17225; WCAG 2.2 C.S. 3.1.1 - Nível A e 3.1.2 - Nível AA*).
- [ ] Usar tags HTML nativas para o seu propósito estrutural real (`<button>` para ações, `<a>` para navegação), sem improvisar comportamentos interativos em `<div>` ou `<span>` (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 - Nível A e 4.1.2 - Nível A*).
- [ ] Estruturar o layout com as regiões de referência (`header`, `main`, `footer`, `nav`, `aside`) garantindo que todo o conteúdo da página esteja contido nelas (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 - Nível A e 1.3.6 - Nível AAA*).
- [ ] Manter apenas uma região principal de `header`, `main` e `footer` por página (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 - Nível A e 1.3.6 - Nível AAA*).
- [ ] Atribuir nomes acessíveis exclusivos (via ARIA) quando houver múltiplas regiões do mesmo tipo na tela, como dois menus `<nav>` (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 - Nível A e 4.1.2 - Nível A*).
- [ ] Respeitar a ordem lógica dos cabeçalhos (`h1` a `h6`) sem pular níveis e nunca usá-los apenas para mudar o estilo visual do texto (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 - Nível A e 2.4.6 - Nível AA*).
- [ ] Ter um único `h1` descritivo por página e iniciar todas as seções de conteúdo importantes com cabeçalhos adequados (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 2.4.6 - Nível AA e 2.4.10 - Nível AAA*).
- [ ] Agrupar itens em tela usando listas semânticas coerentes (`<ul>`, `<ol>`, `<dl>`) (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 - Nível A*).
- [ ] Usar tabelas exclusivamente para dados tabulares. Se usar tabela para montar layout, ela deve ter sua semântica removida (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 - Nível A*).
- [ ] Ligar as células de dados (`<td>`) aos seus respectivos cabeçalhos de linha e coluna (`<th>`) diretamente no código (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 - Nível A*).
- [ ] Colocar legendas (`<caption>`) nas tabelas e fornecer um resumo em texto caso a tabela de dados seja muito complexa (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 - Nível A, 2.4.6 - Nível AA e 3.1.5 - Nível AAA*).
- [ ] Marcar textos especiais no código (ênfases, citações, abreviações) com as tags semânticas específicas para o propósito deles (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 - Nível A*).
- [ ] Dar um atributo `title` exclusivo e descritivo para todos os elementos `<frame>` e `<iframe>` (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 - Nível A e 4.1.2 - Nível A*).
- [ ] Garantir que o nome acessível do componente (o que o leitor de tela lê) contenha exatamente o mesmo texto que aparece visível na interface (*ABNT NBR 17225; WCAG 2.2 C.S. 2.5.3 - Nível A*).
- [ ] Determinar via WAI-ARIA a função (`role`), o estado, a propriedade e o valor de componentes customizados, incluindo suas mudanças dinâmicas (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 - Nível A e 4.1.2 - Nível A*).
- [ ] Dar instruções claras de como operar componentes customizados que tenham interações muito complexas (*ABNT NBR 17225; WCAG 2.2 C.S. 3.3.2 - Nível A*).
- [ ] Não colocar conteúdos ou textos essenciais usando pseudoclasses CSS (`::before`, `::after`), pois leitores de tela podem não acessá-los (*Guia do Reino Unido; ABNT NBR 17225*).
- [ ] Ter cuidado ao usar `display: none` e `visibility: hidden`, lembrando sempre que eles escondem os elementos também das tecnologias assistivas (*Guia do Reino Unido; ABNT NBR 17225; WAI-ARIA Practices*).
- [ ] Atualizar dinamicamente o nome de botões que usam apenas ícones conforme a ação mudar (ex: alternar de "expandir" para "retrair") (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 4.1.2 - Nível A*).
- [ ] Avisar sobre mensagens de status ("carregando", "salvo com sucesso", alertas) via código (*live regions*) sem roubar o foco do usuário na tela (*ABNT NBR 17225; WCAG 2.2 C.S. 4.1.3 - Nível AA*).
- [ ] Manter a ordem do código HTML intuitiva, lógica e correspondente à apresentação visual da tela (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.3.2 - Nível A*).
- [ ] Permitir que o usuário alterne entre mouse, teclado, toque ou voz na mesma sessão sem que a interface trave (*ABNT NBR 17225; WCAG 2.2 C.S. 2.5.6 - Nível AAA*).
- [ ] Rodar validadores automáticos no código HTML/WCAG e documentar as correções através de relatórios estruturados (*Guia do Reino Unido*).
- [ ] Fazer testes manuais rigorosos navegando apenas pelo teclado e usando leitores de tela tanto no desktop (NVDA, Orca, VoiceOver) quanto no mobile (TalkBack, VoiceOver) (*Guia do Reino Unido; ABNT NBR 17225*).
- [ ] Validar a usabilidade dos fluxos com pessoas com diferentes perfis de deficiência (sem visão, visão limitada, sem audição, restrições motoras e cognitivas) (*Guia do Reino Unido; ABNT NBR 17225*).

---

## 2. Privacidade, Segurança e Controle de Tempo

- [ ] Projetar fluxos que não tenham limite de tempo na sessão, a menos que sejam eventos em tempo real ou mídias sincronizadas (*ABNT NBR 17225; WCAG 2.2 C.S. 2.2.1 - Nível A e 2.2.3 - Nível AAA*).
- [ ] Se a tela tiver limite de tempo, oferecer ao usuário a opção de desativá-lo, ajustá-lo em até 10x ou prorrogá-lo mediante aviso prévio de 20 segundos por meio de uma ação simples (*ABNT NBR 17225; WCAG 2.2 C.S. 2.2.1 - Nível A*).
- [ ] Avisar o usuário antecipadamente caso a inatividade vá causar a perda dos dados, ou preservar o que foi preenchido por pelo menos 20 horas (*ABNT NBR 17225; WCAG 2.2 C.S. 2.2.1 - Nível A e 2.2.6 - Nível AAA*).
- [ ] Se a sessão de login cair, garantir que o usuário retome exatamente de onde parou após a reautenticação, sem perder os dados já inseridos (*ABNT NBR 17225; WCAG 2.2 C.S. 2.2.1 - Nível A e 2.2.5 - Nível AAA*).
- [ ] Permitir que o usuário pause, oculte ou ajuste a frequência de conteúdos que atualizam sozinhos, como placares e feeds de notícias (*ABNT NBR 17225; WCAG 2.2 C.S. 2.2.2 - Nível A*).
- [ ] Oferecer a opção de adiar ou suprimir alertas e interrupções não emergenciais na interface (*ABNT NBR 17225; WCAG 2.2 C.S. 2.2.4 - Nível AAA*).
- [ ] Não exigir testes de função cognitiva (como resolver quebra-cabeças, transcrever textos distorcidos ou memorizar senhas) como único meio de login (*ABNT NBR 17225; WCAG 2.2 C.S. 3.3.8 - Nível AA e 3.3.9 - Nível AAA*).
- [ ] Permitir o uso livre de gerenciadores de senhas, recursos de preenchimento automático e atalhos de copiar e colar nos campos de segurança (*ABNT NBR 17225; WCAG 2.2 C.S. 3.3.8 - Nível AA*).
- [ ] Fornecer métodos alternativos de autenticação avançada que não dependam de reconhecimento visual de objetos ou conteúdo pessoal (*ABNT NBR 17225; WCAG 2.2 C.S. 3.3.9 - Nível AAA*).
- [ ] Se utilizar biometria ou reconhecimento facial, dar instruções acessíveis de posicionamento da câmera e sempre oferecer um método alternativo (*ABNT NBR 17225; WCAG 2.2 C.S. 1.1.1 - Nível A, 2.5.4 - Nível A e 2.5.6 - Nível AAA*).
- [ ] Deixar claro em texto qual é a tarefa ou o desafio exigido por qualquer CAPTCHA presente na tela (*ABNT NBR 17225; WCAG 2.2 C.S. 1.1.1 - Nível A*).
- [ ] Disponibilizar opções simples e multimodais para os CAPTCHAs, como desafios de áudio (sem ruído excessivo e no idioma correto) ou verificação lógica básica (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.1.1 - Nível A*).
- [ ] Assegurar que todas as telas de validação, segurança e login funcionem 100% via teclado e sejam operáveis por leitores de tela (*ABNT NBR 17225; WCAG 2.2 C.S. 2.1.1 - Nível A*).
- [ ] Exibir alertas de segurança usando textos claros (não dependendo apenas de cor, som ou ícone) e garantir que as mensagens não exponham dados sensíveis ou códigos do sistema (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.1 - Nível A*).

---

## 3. Navegação, Foco e Interação

- [ ] Garantir que 100% das funções interativas do site sejam alcançáveis e operáveis exclusivamente pelo uso do teclado (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 2.1.1 - Nível A e 2.1.3 - Nível AAA*).
- [ ] Fazer com que o foco de navegação (`tabindex`) passe apenas por elementos interativos, respeitando uma ordem sequencial e lógica na interface (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 2.4.3 - Nível A*).
- [ ] Evitar completamente as "armadilhas de teclado" (*keyboard traps*), assegurando que o usuário consiga entrar e sair de qualquer componente facilmente (*ABNT NBR 17225; WCAG 2.2 C.S. 2.1.2 - Nível A*).
- [ ] Destacar claramente qual elemento está recebendo a interação exibindo um indicador de foco evidente (`:focus-visible`) (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 2.4.7 - Nível AA*).
- [ ] Garantir que o contorno do foco tenha contraste mínimo de 3:1 (tanto com o fundo quanto com o estado inativo) e englobe o elemento com uma espessura visível (*retângulo delimitador / minimum bounding box*) (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.11 - Nível AA e 2.4.13 - Nível AA*).
- [ ] Assegurar que o item focado nunca fique escondido atrás de cabeçalhos fixos, barras flutuantes ou rodapés (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.11 - Nível AA e 2.4.12 - Nível AAA*).
- [ ] Não criar atalhos de teclado formados por uma única tecla (sem uso de Ctrl ou Alt), a menos que o usuário possa desligá-los, remapeá-los ou que só funcionem com o componente específico em foco (*ABNT NBR 17225; WCAG 2.2 C.S. 2.1.4 - Nível A*).
- [ ] Não exigir velocidade ou impor limite de tempo para o usuário conseguir acionar sequências de teclas na navegação (*WCAG 2.2 Diretriz 2.1 - Nível AAA; ABNT NBR 17225*).
- [ ] Disponibilizar um link invisível de salto ("Pular para o conteúdo principal") que aparece como primeiro item interativo no topo das páginas (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 2.4.1 - Nível A*).
- [ ] Fornecer mais de uma maneira de encontrar as páginas do site (como campo de pesquisa, mapa do site ou índice de conteúdos) (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 2.4.5 - Nível AA*).
- [ ] Mostrar ao usuário onde ele está localizado dentro da arquitetura do site (utilizando trilhas de navegação / *breadcrumbs*) (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 2.4.8 - Nível AAA*).
- [ ] Manter os menus principais e botões de ajuda (FAQ, contato) repetidos exatamente na mesma ordem relativa em todas as páginas (*ABNT NBR 17225; WCAG 2.2 C.S. 3.2.3 - Nível AA e 3.2.6 - Nível A*).
- [ ] Identificar ícones e componentes que realizam a mesma ação sempre de um jeito padronizado e consistente (*ABNT NBR 17225; WCAG 2.2 C.S. 3.2.4 - Nível AA*).
- [ ] Explicar a função ou o destino do link no próprio texto clicável, evitando expressões vazias isoladas como "clique aqui", "saiba mais" ou "baixe agora" (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 2.4.4 - Nível A e 2.4.9 - Nível AAA*).
- [ ] Escrever os textos de links de forma contínua, evitando cortes com reticências ("...") que prejudicam a compreensão pelo leitor de tela (*Guia do Reino Unido; ABNT NBR 17225*).
- [ ] Não usar textos de links idênticos se eles levam para destinos diferentes, e evitar links repetidos adjacentes apontando para o mesmo lugar (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.4 - Nível A e 3.2.4 - Nível AA*).
- [ ] Evitar colocar um texto de apoio (`title` ou ARIA) que faça apenas a repetição exata do texto que já está visível no link (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.4 - Nível A*).
- [ ] Avisar de forma clara (no texto ou visualmente) quando o link for abrir em uma nova aba ou levar para um site de terceiros (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.4 - Nível A e 3.2.5 - Nível AAA*).
- [ ] Indicar o formato e o peso do arquivo nos links de download (ex: "Relatório (PDF, 2 MB)") e certificar-se de que o documento baixado também é acessível (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.4 - Nível A*).
- [ ] Destacar hiperlinks que ficam no meio de blocos de texto usando sublinhado e contraste, sem depender unicamente da cor azul para diferenciá-los (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.4.1 - Nível A*).
- [ ] Garantir que tooltips ou submenus que aparecem ao passar o mouse continuem abertos quando o cursor se move para cima deles, e que o usuário consiga fechá-los com a tecla ESC (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.13 - Nível AA*).
- [ ] Não disparar mudanças bruscas na interface (como abrir modais, enviar dados ou roubar o foco) apenas porque um elemento recebeu foco do teclado ou o input foi alterado sem aviso prévio (*ABNT NBR 17225; WCAG 2.2 C.S. 3.2.1 - Nível A e 3.2.2 - Nível A*).
- [ ] Confirmar cliques e toques somente quando o usuário solta o botão (*up-event*), permitindo que a ação seja cancelada se ele arrastar o ponteiro para fora da área (*ABNT NBR 17225; WCAG 2.2 C.S. 2.5.2 - Nível A*).
- [ ] Oferecer um botão simples (operação de um clique/toque) como alternativa para qualquer ação que exija gestos complexos como arrastar-e-soltar, pinça (*zoom*) ou deslizar na tela (*ABNT NBR 17225; WCAG 2.2 C.S. 2.5.1 - Nível A e 2.5.7 - Nível AA*).
- [ ] Disponibilizar botões convencionais para substituir interações baseadas em movimento físico do aparelho (sacudir, inclinar) e dar a opção de desativar esses sensores (*ABNT NBR 17225; WCAG 2.2 C.S. 2.5.4 - Nível A*).
- [ ] Evitar janelas modais sobrepostas. Quando forem indispensáveis, elas precisam ser fáceis de fechar, suportar a tecla ESC, segurar o foco do teclado de forma segura, não abrir sozinhas e nunca empilhar uma modal sobre a outra (*Guia do Reino Unido; ABNT NBR 17225*).

---

## 4. Conteúdo, Linguagem e Mídia

- [ ] Tratar o público com a terminologia correta: use "Pessoa com deficiência (PcD)" ou especifique a condição (pessoa cega, surda, autista, cadeirante), abolindo completamente o uso da palavra "portador" (*Guia do Reino Unido; LBI*).
- [ ] Escrever adotando os princípios de Linguagem Simples (ISO 24495-1): frases curtas (15 a 20 palavras), ordem direta, pontuação clara e sem uso de ambiguidades ou figuras de linguagem rebuscadas (*Guia do Reino Unido; ABNT NBR 17225*).
- [ ] Oferecer uma versão simplificada ou material de apoio em texto caso o conteúdo original exija um nível de leitura técnico ou muito avançado (*ABNT NBR 17225; WCAG 2.2 C.S. 3.1.5 - Nível AAA*).
- [ ] Criar mecanismos acessíveis para expandir siglas, explicar jargões da área e orientar a pronúncia de termos muito complexos (*ABNT NBR 17225; WCAG 2.2 C.S. 3.1.3 - Nível AAA, 3.1.4 - Nível AAA e 3.1.6 - Nível AAA*).
- [ ] Apresentar as informações principais em mais de um formato (texto, áudio, gráfico) para apoiar o entendimento de pessoas neurodiversas ou com baixo letramento (*Guia do Reino Unido; ABNT NBR 17225*).
- [ ] Descrever imagens informativas no atributo `alt` de forma estruturada: tipo + o quê/quem + onde + ação (no presente) + contexto, evitando escrever o óbvio como "foto de" (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.1.1 - Nível A*).
- [ ] Descrever a ação ou o destino final no atributo `alt` de botões com ícones funcionais, como usar "Buscar pedidos" em vez de descrever o visual da "Lupa" (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.1.1 - Nível A e 2.4.4 - Nível A*).
- [ ] Aplicar o atributo vazio (`alt=""`) ou carregar via CSS as imagens que são puramente decorativas, garantindo que o leitor de tela simplesmente as ignore (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.1.1 - Nível A*).
- [ ] Fornecer uma breve identificação no `alt` e um bloco de texto detalhado e visível na própria página para explicar imagens complexas como gráficos, organogramas ou mapas (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.1.1 - Nível A*).
- [ ] Inserir o texto alternativo correspondente em cada área clicável individual (`<area>`) dentro de mapas de imagem (*ABNT NBR 17225; WCAG 2.2 C.S. 1.1.1 - Nível A*).
- [ ] Evitar usar imagens contendo texto (banners com frases coladas). Se forem estritamente essenciais (como logotipos), elas devem conter um `alt` idêntico ao texto da imagem (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.4.5 - Nível AA e 1.4.9 - Nível AAA*).
- [ ] Disponibilizar uma transcrição integral em texto para áudios e podcasts, identificando adequadamente os locutores e efeitos sonoros relevantes (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.2.1 - Nível A*).
- [ ] Fornecer legendas descritivas e sincronizadas (Open ou Closed Caption) para vídeos pré-gravados, transcrevendo falas e contextualizando sons de ambiente com bom contraste (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.2.2 - Nível A*).
- [ ] Integrar audiodescrição em vídeos pré-gravados, de preferência planejando os espaços já na etapa de roteiro ou criando uma versão estendida (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.2.3 - Nível A, 1.2.5 - Nível AA e 1.2.7 - Nível AAA*).
- [ ] Oferecer um roteiro ou transcrição completa que descreva simultaneamente o conteúdo visual e o sonoro para arquivos de vídeo pré-gravados (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.2.3 - Nível A e 1.2.8 - Nível AAA*).
- [ ] Incluir uma janela de interpretação em Libras nas mídias de vídeo, preferencialmente à direita da tela e com alto contraste no fundo (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.2.6 - Nível AAA*).
- [ ] Disponibilizar legendas sincronizadas em tempo real para vídeos ao vivo, bem como texto ao vivo equivalente para transmissões focadas apenas em áudio (*ABNT NBR 17225; WCAG 2.2 C.S. 1.2.4 - Nível AA e 1.2.9 - Nível AAA*).
- [ ] Barrar mídias de áudio que toquem automaticamente por mais de 3 segundos; se tocarem, fornecer logo no topo da tela um botão acessível para pausar ou baixar o volume de forma independente (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.2 - Nível A*).
- [ ] Produzir áudios de fala onde eventuais ruídos de fundo (trilhas musicais) fiquem pelo menos 20 dB mais baixos que a voz principal, evitando sons muito estridentes (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.4.7 - Nível AAA*).
- [ ] Exibir botões claros e fáceis de operar pelo teclado para pausar carrosséis e banners automáticos que permaneçam em movimento por mais de 5 segundos (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 2.2.2 - Nível A*).
- [ ] Evitar excessos como animações de tela inteira ou rolagem com efeito parallax, e dar ao usuário o poder de desligar as animações disparadas por interação (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 2.3.3 - Nível AAA*).
- [ ] Proteger o usuário de crises convulsivas garantindo que absolutamente nenhum conteúdo pisque ou brilhe mais de 3 vezes por segundo na tela (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 2.3.1 - Nível A e 2.3.2 - Nível AAA*).
- [ ] Aplicar o padrão CamelCase ao criar hashtags (ex: `#AcessibilidadeDigital`) para melhorar a dicção dos leitores de tela e moderar o uso de emojis no meio dos textos (*Guia do Reino Unido; ABNT NBR 17225*).

---

## 5. Design, Tipografia e Layout Responsivo

- [ ] Assegurar a responsividade do layout em larguras bem pequenas (como 320px CSS) sem cortar conteúdos e sem forçar o usuário a rolar a página vertical e horizontalmente ao mesmo tempo (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.10 - Nível AA*).
- [ ] Não bloquear a tela do celular em uma única orientação; o design deve fluir livremente caso o usuário gire o aparelho para modo retrato ou paisagem (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.3.4 - Nível AA*).
- [ ] Permitir que a interface receba até 200% de zoom pelo navegador sem truncar blocos de texto (evite alturas fixas no CSS) e sem quebrar o layout (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.4.4 - Nível AA e 1.4.10 - Nível AA*).
- [ ] Jamais utilizar apenas a cor visual para indicar uma ação ou um campo com erro; combine cores com descrições em texto, texturas ou ícones óbvios (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.4.1 - Nível A*).
- [ ] Testar a paleta cromática do site em simuladores para validar se as informações permanecem legíveis para diferentes tipos de daltonismo (*Guia do Reino Unido; ABNT NBR 17225*).
- [ ] Garantir o contraste de cor mínimo de 4,5:1 entre a fonte normal e seu fundo. Textos maiores (18pt normal ou 14pt negrito) podem ter um limite mais flexível de 3:1 (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.3 - Nível AA*).
- [ ] Para projetos de excelência (nível AAA), buscar um contraste avançado de pelo menos 7:1 para os textos de leitura comum (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.6 - Nível AAA*).
- [ ] Checar o contraste mínimo em fotografias e fundos degradê analisando os três pontos da área de texto: tom mais claro, tom médio e tom escuro (*Guia do Reino Unido*).
- [ ] Garantir que o contraste não se limite às fontes: as bordas de formulários e os gráficos funcionais também exigem a relação de 3:1 com o fundo da tela (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.11 - Nível AA*).
- [ ] Oferecer a opção nativa de alto contraste (*dark mode*) e desenhar uma estrutura de CSS que não quebre caso o usuário injete seu próprio esquema de cores no navegador (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.4.8 - Nível AAA*).
- [ ] Desenhar botões e links com área de clique mínima de 24x24 pixels CSS, sendo altamente recomendado mirar nos 44x44px ou 48x48px, mesmo que o desenho do ícone no centro seja menor (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 2.5.5 - Nível AAA e 2.5.8 - Nível AA*).
- [ ] Inserir respiros visuais generosos (espaçamento em branco) entre campos ou opções de clique próximas para não poluir a interface e evitar ações acidentais (*Guia do Reino Unido; ABNT NBR 17225*).
- [ ] Sempre que possível, unir texto e ícone nos botões, pois a combinação visual acelera drasticamente a compreensão para pessoas neurodivergentes e surdas (*Guia do Reino Unido; ABNT NBR 17225*).
- [ ] Não basear as orientações da interface apenas em aspectos visuais ou acústicos da tela (ex: em vez de dizer "preencha o quadro redondo vermelho", diga "preencha o campo de endereço") (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.3 - Nível A*).
- [ ] Selecionar fontes tipográficas legíveis e redondas (recomendado tamanho de 18pt normal ou 14pt negrito), descartando letras cursivas finas e blocos densos totalmente em caixa alta (*Guia do Reino Unido; ABNT NBR 17225*).
- [ ] Alinhar blocos contínuos de texto sempre à esquerda para idiomas ocidentais. Textos justificados ou centralizados geram perdas de linha e leitura para quem possui dislexia (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.4.8 - Nível AAA*).
- [ ] Configurar o CSS para que as linhas de texto tenham no máximo 80 caracteres de largura, poupando o cansaço visual de movimentos de leitura muito longos na tela (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 1.4.8 - Nível AAA e 1.4.10 - Nível AA*).
- [ ] Garantir que o texto continue íntegro se o usuário aplicar ajustes pesados nas propriedades da fonte, como: entrelinhas de 1,5x, espaçamento entre parágrafos de 2x, ou distância aumentada entre as letras (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.8 - Nível AAA e 1.4.12 - Nível AA*).

---

## 6. Formulários e Prevenção de Falhas

- [ ] Planejar formulários curtos e objetivos que sempre tenham um botão explícito para enviar os dados, evitando disparos automáticos ou mudanças inesperadas ao digitar (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 3.2.2 - Nível A*).
- [ ] Conectar tecnicamente os campos de preenchimento (`<input>`) aos seus textos de identificação (`<label>`) e posicioná-los lado a lado no layout (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 - Nível A, 3.3.2 - Nível A e 4.1.2 - Nível A*).
- [ ] O rótulo deve ser autoexplicativo e externo à caixa do campo. Nunca use o placeholder (a dica cinza dentro da caixa) no lugar de um `<label>`, pois ele some ao primeiro toque (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.6 - Nível AA e 3.3.2 - Nível A*).
- [ ] Colocar dicas de formato de forma permanente na tela (ex: exibir DD/MM/AAAA por fora do campo), e manter eventuais ícones de ajuda contextual fáceis de achar (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 3.3.2 - Nível A e 3.3.5 - Nível AAA*).
- [ ] Usar as tags de agrupamento HTML (`<fieldset>` e `<legend>`) para juntar opções de resposta que pertençam a uma mesma pergunta lógica, como blocos de radio buttons ou checkboxes (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 - Nível A*).
- [ ] Indicar visualmente, textualmente e via código (ex: `aria-required`) quais os campos da tela são de preenchimento obrigatório (*ABNT NBR 17225; WCAG 2.2 C.S. 3.3.2 - Nível A*).
- [ ] Configurar os tipos dos campos (`type`, `autocomplete`) adequadamente quando coletarem dados pessoais, facilitando o uso do preenchimento automático integrado no navegador (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.5 - Nível AA*).
- [ ] Cortar entradas repetitivas do fluxo: se o usuário já forneceu um dado antes na jornada, o sistema deve permitir selecionar ou autocompletar esse valor nas telas seguintes (*ABNT NBR 17225; WCAG 2.2 C.S. 3.3.7 - Nível A*).
- [ ] Em transações de dinheiro, assinatura de contratos ou deleção de contas, o sistema tem a obrigação de dar ao usuário uma etapa para checar e aprovar (ou reverter) a ação antes do disparo final (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 3.3.4 - Nível AA e 3.3.6 - Nível AAA*).
- [ ] Quando houver falhas na digitação, identificar o erro usando linguagem humana e sem jargões indecifráveis do servidor. A interface deve apontar com clareza o campo específico afetado (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 3.3.1 - Nível A*).
- [ ] Além de apontar o erro, o sistema deve sugerir caminhos fáceis e formatados de como o usuário resolve aquele problema (desde que a dica não exponha falhas de segurança) (*Guia do Reino Unido; ABNT NBR 17225; WCAG 2.2 C.S. 3.3.3 - Nível AA*).
- [ ] Se a página recarregar ou exibir o painel de erros, garantir que o foco seja auxiliado e movido em direção ao formulário em alerta, sem nunca penalizar o usuário apagando o que já foi preenchido com sucesso (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.3 - Nível A e 3.3.1 - Nível A*).

---

## 7. Jornada do Usuário (User Journey) e Fluxos de Navegação (User Flow)

- [ ] Dividir tarefas longas ou complexas em etapas menores e sequenciais (divulgação progressiva / *progressive disclosure*), informando sempre de forma visual e em texto em qual etapa o usuário está (ex: "Passo 2 de 4").
- [ ] Fornecer orientações prévias antes de iniciar fluxos exigentes (como preencher um cadastro longo), informando de antemão o tempo estimado e quais documentos ou informações serão necessários.
- [ ] Evitar "becos sem saída" (*dead ends*): garantir que toda tela ou estado do sistema ofereça um próximo passo claro (Call to Action principal) ou um link fácil para retornar à página inicial.
- [ ] Permitir o salvamento automático do progresso ou oferecer a opção de "Salvar rascunho", garantindo que o usuário possa interromper a jornada, descansar e retomar o fluxo mais tarde de onde parou.
- [ ] Oferecer "saídas de emergência" claras em qualquer ponto do fluxo, com botões visíveis de "Cancelar" ou "Voltar", permitindo que o usuário aborte a operação sem medo de consequências acidentais ou perda total de dados.
- [ ] Manter uma consistência rígida no modelo mental ao longo de toda a jornada: a posição dos botões de ação (ex: "Voltar" sempre à esquerda/secundário, "Avançar" à direita/primário), o tom de voz e os padrões de interação não devem mudar drasticamente entre as telas de um mesmo processo.
- [ ] Exibir telas de confirmação claras (Mensagens de Sucesso) após a conclusão do fluxo, resumindo brevemente o que foi feito, o que vai acontecer a seguir (ex: "Você receberá um e-mail em 5 minutos") e oferecendo atalhos lógicos para a próxima ação.
- [ ] Projetar *Empty States* (telas sem conteúdo, como um carrinho vazio ou uma lista de favoritos sem itens) de forma instrutiva e acolhedora, explicando o que deveria estar ali e exibindo um botão de ação para ajudar o usuário a começar a popular aquela tela.
- [ ] Minimizar as trocas de contexto (*context switching*): evitar obrigar o usuário a sair do aplicativo, ir para o e-mail, copiar um código e voltar para o aplicativo no meio de um fluxo crítico, a menos que seja estritamente necessário para segurança.

---

## Entendendo os "Porquês" (Justificativas Práticas do Checklist)

Abaixo, detalhamos o motivo de cada bloco do checklist existir, explicando o impacto real na vida de quem usa o sistema e a base normativa que sustenta essas exigências. A acessibilidade universal é um direito e sua aplicação prática garante que a tecnologia sirva a todos com autonomia.

### 1. Desenvolvimento, Semântica e Testes
O código HTML é a verdadeira ponte de acesso das tecnologias assistivas. Se ele for montado com improvisos visuais (como o uso crônico de `<div>` para montar barras ou botões), a página se torna uma muralha invisível. Elementos nativos do HTML (`<button>`, `<a>`) e regiões bem delimitadas por landmarks (`nav`, `main`) permitem que uma pessoa cega, por exemplo, "pule" direto para a área que lhe interessa usando atalhos do leitor de tela, não precisando escutar a narração do menu superior todas as vezes. E vale ressaltar: ferramentas automáticas pegam no máximo 30% das falhas reais, motivo pelo qual a norma obriga a testagem humana em diferentes aparelhos e, principalmente, ouvindo quem de fato convive com a deficiência.

### 2. Privacidade, Segurança e Controle de Tempo
Sessões com cronômetros curtos e inajustáveis são uma barreira cruel. Elas excluem automaticamente idosos, pessoas com espasmos motores, usuários com dislexia e indivíduos neurodivergentes, que tendem a precisar de mais tempo para absorver o que está na tela e digitar os dados de volta. Encerrar uma sessão repentinamente sem reter as respostas apaga a jornada e frustra qualquer ser humano. Isso também se aplica a barreiras na entrada: exigir que a pessoa resolva quebra-cabeças visuais (como um CAPTCHA onde deve-se reconhecer semáforos) proíbe quem não enxerga ou tem baixa cognição de sequer acessar os serviços da plataforma.

### 3. Navegação, Foco e Interação
Devemos assumir, de partida, que o mouse não é a única forma de interagir com o computador. O sistema deve fluir com naturalidade apenas pelo teclado. Nesse contexto, se a borda ao redor dos itens (o "foco visível") for tênue ou inexistente, é como se a pessoa navegasse às cegas na tela. Componentes complexos que aprisionam a navegação (modais problemáticas que geram "armadilhas de teclado") são o terror de quem não usa apontador físico. Interações que peçam gestos elaborados demais no celular (como deslizar com dois dedos ou inclinar o aparelho) também bloqueiam cadeirantes ou pessoas com limitações severas de movimento fino.

### 4. Conteúdo, Linguagem e Mídia
A comunicação tem a obrigação de ser fácil de perceber. Em uma internet saturada por mídias, vídeos sem legenda privam as pessoas surdas da informação, assim como vídeos ausentes de audiodescrição e imagens vitais postadas sem texto alternativo (`alt`) segregam os usuários com deficiência visual. Pelo lado cognitivo, interfaces com textos carregados de jargão jurídico, jargão tecnológico ou áudios e banners incontroláveis causam esgotamento e desvio de foco severos para quem possui TDAH, além de ofuscarem o próprio leitor de tela do usuário. Finalmente, piscar cores vibrantes rapidamente é terminantemente vetado pela legislação, dado o potencial letal de desencadear crises de epilepsia fotossensível.

### 5. Design, Tipografia e Layout Responsivo
A excelência visual respeita e engloba as customizações do próprio navegador do usuário. Se a arquitetura CSS quebrar, sobrepor informações ou exigir rolagem para o lado apenas porque uma pessoa com baixa visão ativou um zoom de 200%, a acessibilidade falhou. Na pintura das telas, a paleta de cores não pode carregar sozinha a responsabilidade de passar mensagens de falha ou sucesso; os índices de daltonismo tornam o uso de texturas e ícones adicionais essencial. Contrastes firmes e fontes arredondadas com bom tamanho, desenhadas com áreas de clique generosas para quem tem tremores na mão, demonstram a maturidade de um design centrado nas realidades do corpo humano, e não em meras tendências estéticas.

### 6. Formulários e Prevenção de Falhas
Na arquitetura da informação, os formulários são os grandes gargalos de erro na navegação. Eliminar os antigos placeholders (a dica em cinza fraco) e colocar o nome dos campos visualmente do lado de fora em um `<label>` resguarda a memória de curto prazo, já que o usuário não precisará apagar o que escreveu para lembrar o que o campo pedia. Quando o erro humano de preenchimento acontece, a máquina precisa usar empatia programada: apontar o erro visualmente de imediato, traduzir o problema de forma educada e sugerir a correção correta, conduzindo o foco de volta e preservando o esforço já dedicado na jornada. Transações sensíveis simplesmente precisam admitir revisão prévia para proteger pessoas de danos irreparáveis.

### 7. Jornada do Usuário (User Journey) e Fluxos de Navegação (User Flow)
Um fluxo mal desenhado não é apenas um problema de conversão comercial; é uma barreira cognitiva severa. Quando jogamos um formulário de 40 campos em uma única tela sem aviso prévio, causamos ansiedade e fadiga imediata, punindo especialmente usuários neurodivergentes (como pessoas com TDAH) e idosos. Ao quebrar tarefas complexas em passos curtos, permitir que o progresso seja salvo e projetar rotas de saída seguras ("Cancelar"), devolvemos o controle da máquina para o humano. O usuário precisa saber, a cada segundo, onde ele está, o que acabou de fazer, o que precisa fazer agora e para onde pode ir depois. Previsibilidade em uma interface não é tédio, é conforto e acessibilidade.
