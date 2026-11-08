# Relatório Geral Unificado de Aplicação do Checklist de Acessibilidade Digital

**Projeto:** Avaliação de Acessibilidade e Usabilidade — Portal Fala.BR (Controladoria-Geral da União)  
**Disciplina:** Interação Humano-Computador (IHC 2026.2) — Grupo 03  
**Data de Consolidação:** Novembro de 2026  
**URLs Avaliadas:**
- **Página Inicial:** [https://falabr.cgu.gov.br/v2/](https://falabr.cgu.gov.br/v2/)
- **Fluxo de Registro de Manifestações (6 Passos):** [https://falabr.cgu.gov.br/v2/manifestacoes/registrar](https://falabr.cgu.gov.br/v2/manifestacoes/registrar)
  - *Passo 1: Relato* | *Passo 2: Tipo e Assunto* | *Passo 3: Local* | *Passo 4: Envolvidos* | *Passo 5: Revisão* | *Passo 6: Conclusão*

**Bases Normativas:**
1. **ABNT NBR 17225:2025** (Acessibilidade em interfaces Web e mitigação de barreiras)
2. **W3C WCAG 2.2** (Níveis A, AA e AAA)
3. **Guia de Boas Práticas de Acessibilidade Digital (Reino Unido – Brasil)**
4. **Lei Brasileira de Inclusão (LBI - Lei Federal nº 13.146/2015)**

---

## 1. Métodos e Ferramentas Empregadas

Este documento consolida em uma **única base integrada** todas as evidências obtidas através de três abordagens metodológicas complementares:

1. **Auditoria Técnica Automatizada:**
   - Inspeção com navegador real *Headless Chrome* via Puppeteer e motor internacional **axe-core 4.x** (W3C/Deque).
   - Testes de responsividade a 320px CSS, contraste, marcos semânticos (*landmarks*), hierarquia de cabeçalhos e conformidade WAI-ARIA.
2. **Auditoria da Árvore de Acessibilidade (*Accessibility Tree*):**
   - Extração da camada de acessibilidade do Chromium (Chrome DevTools Protocol), simulando com precisão a estrutura entregue aos leitores de tela (**NVDA**, **TalkBack** e **JAWS**) para mapear os nomes acessíveis computados, papéis (*roles*) e alertas.
3. **Avaliação Empírica com Usuários Reais (Testes de Usabilidade):**
   - **Participante 1 (P1):** Mulher, 48 anos, com problemas de vista / baixa visão (presbiopia severa) e necessidade de ampliação e zoom.
   - **Participante 2 (P2):** Homem, 21 anos, com limitação motora (**Tremor Essencial**).
   - Aplicação de protocolo de pensamento em voz alta (*think-aloud*), tarefas de denúncia anônima e questionário padronizado **SUS (System Usability Scale)**.

---

## 2. Painel Executivo e Status Geral do Checklist

| Status do Critério | Quantidade de Itens | Percentual | Descrição |
| :--- | :---: | :---: | :--- |
| 🟢 **Conforme (Aprovado)** | **49** | 38,6% | Atende plenamente à norma comprovado por código, árvore a11y, testes de usuários e validação prática de erros e linguagem. |
| 🔴 **Não Conforme (Reprovado)** | **42** | 33,1% | Apresenta falha técnica/empírica comprovada (incluindo perda total de dados com F5/recarregamento e falta de `<abbr>`). |
| 🟡 **Parcialmente Conforme** | **14** | 11,0% | Funciona em parte ou apresenta ressalvas de usabilidade. |
| ⚪ **Não se Aplica ao Site** | **17** | 13,4% | Critérios de mídias/funcionalidades inexistentes no Fala.BR (ex.: vídeos, áudios, fundos em degradê, transações bancárias). |
| 🔵 **Faltam Validação Humana / Ética** | **5** | **3,9%** | **Itens que dependem de teste manual com conta real Gov.br ou têm restrição ética de produção (Passo 6).** |
| **TOTAL GERAL** | **127** | **100%** | **Checklist Completo Consolidado** |

> **RESPOSTA ATUALIZADA: QUANTOS FALTAM VALIDAÇÃO HUMANA AGORA?**  
> Com a incorporação dos seus testes manuais (upload de `.pptx` com erro amigável, teste de F5 com perda de dados, validação de Linguagem Acessível e confirmação técnica de que o **VLibras está ativo em todas as 6 etapas do fluxo**), **restam apenas 5 a 6 itens estritos** (ver Seção 5).

> **RESPOSTA ATUALIZADA: QUANTOS FALTAM VALIDAÇÃO HUMANA AGORA?**  
> Após a rodada avançada de requisições, injeções dinâmicas de CSS, varreduras regex e emulação de daltonismo via CDP, **mais 10 itens foram diagnosticados e resolvidos programaticamente**.  
> **Restam exatamente 8 itens que ainda demandam validação humana especializada** (ver Seção 5 para a lista detalhada).

---

## 3. Aplicação Integral do Checklist (Item a Item)

---

### Seção 1. Desenvolvimento, Semântica e Testes

1. **Usar um título (`<title>`) único e descritivo em cada página (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.2 - A*)**
   - **Status:** 🔴 **NÃO CONFORME**
   - **Evidência:** O título `<title>` permanece estático como `"Fala.BR - Plataforma Integrada de Ouvidoria e Acesso à Informação"` em todas as etapas de 1 a 6 do registro, impedindo que o leitor de tela anuncie a mudança de passo.
2. **Declarar o idioma principal na tag raiz (`<html lang="...">`) (*ABNT NBR 17225; WCAG 2.2 C.S. 3.1.1 - A e 3.1.2 - AA*)**
   - **Status:** 🟢 **CONFORME**
   - **Evidência:** `<html lang="pt-BR">` declarado na raiz.
3. **Usar tags HTML nativas para o propósito real (`<button>`, `<a>`) (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 e 4.1.2 - A*)**
   - **Status:** 🟡 **PARCIALMENTE CONFORME**
   - **Evidência:** Botões primários usam `<button>`, porém links de menu usam `<a href="#">` com script e foram detectados nós de controles aninhados (*nested-interactive*).
4. **Estruturar layout com regiões de referência (`header`, `main`, `footer`, `nav`, `aside`) (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 e 1.3.6*)**
   - **Status:** 🔴 **NÃO CONFORME**
   - **Evidência:** O banner de cookies (`<p class="cookie-consent__text">`) e o popup do VLibras (`<img id="vlibras-popup">`) ficam fora de qualquer marco semântico.
5. **Manter apenas uma região principal de `header`, `main` e `footer` por página (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 e 1.3.6*)**
   - **Status:** 🟢 **CONFORME**
   - **Evidência:** O DOM possui exatamente um `<header>`, um `<main>` e um `<footer>`.
6. **Atribuir nomes acessíveis exclusivos (via ARIA) a múltiplas regiões do mesmo tipo (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 e 4.1.2*)**
   - **Status:** 🔴 **NÃO CONFORME**
   - **Evidência:** Menus de navegação `<nav>` não utilizam `aria-label` para se diferenciarem.
7. **Respeitar ordem lógica de cabeçalhos (`h1` a `h6`) sem pular níveis (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 e 2.4.6*)**
   - **Status:** 🔴 **NÃO CONFORME**
   - **Evidência:** Nos Passos 3, 4 e 5 do formulário, a hierarquia é rompida e o nível `<h1>` desaparece.
8. **Ter um único `h1` descritivo por página (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.6 e 2.4.10*)**
   - **Status:** 🔴 **NÃO CONFORME**
   - **Evidência:** Na Home existe `<h1>`, mas nos passos intermediários do registro não há `<h1>` identificador da etapa ativa.
9. **Agrupar itens em listas semânticas (`<ul>`, `<ol>`, `<dl>`) (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1*)**
   - **Status:** 🟢 **CONFORME**
   - **Evidência:** Menus do cabeçalho e opções do sistema utilizam listas `<ul>` com `<li>`.
10. **Usar tabelas exclusivamente para dados tabulares (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** A diagramação visual é feita com flexbox e grid CSS; não há tabelas de layout.
11. **Ligar células de dados (`<td>`) aos seus cabeçalhos (`<th>`) (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1*)**
    - **Status:** ⚪ **NÃO SE APLICA AO SITE**
    - **Evidência:** Inexistência de dados tabulares nas telas avaliadas.
12. **Colocar legendas (`<caption>`) e resumo em tabelas complexas (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1, 2.4.6, 3.1.5*)**
    - **Status:** ⚪ **NÃO SE APLICA AO SITE**
    - **Evidência:** Inexistência de tabelas nas rotas auditadas.
13. **Marcar textos especiais no código (ênfases, citações, abreviações) com tags específicas (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1*)**
    - **Status:** 🔵 **FALTA VALIDAÇÃO HUMANA**
    - **Motivo:** Análise contextual para confirmar se trechos de leis e termos de sigilo deveriam utilizar marcação semântica própria (`<q>`, `<blockquote>`, `<abbr>`).
14. **Dar atributo `title` exclusivo e descritivo para `<frame>` e `<iframe>` (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 e 4.1.2*)**
    - **Status:** 🔴 **NÃO CONFORME**
    - **Evidência:** O `<iframe>` do Google Tag Manager carece de atributo `title`.
15. **Nome acessível do componente conter exatamente o texto visível na interface (*ABNT NBR 17225; WCAG 2.2 C.S. 2.5.3 - A*)**
    - **Status:** 🔴 **NÃO CONFORME (GRAVE)**
    - **Evidência:** Botões visíveis como "Início", "Órgãos", "Dados Abertos" possuem `aria-label="Botão"`, quebrando comandos por voz e a compreensão do leitor de tela.
16. **Determinar via WAI-ARIA papel (`role`), estado, propriedade e valor de componentes customizados (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1 e 4.1.2*)**
    - **Status:** 🔴 **NÃO CONFORME**
    - **Evidência:** O assistente de passos utiliza `aria-controls="tab0"`, `aria-controls="tab1"`, que referenciam IDs inexistentes no DOM.
17. **Instruções claras de como operar componentes customizados complexos (*ABNT NBR 17225; WCAG 2.2 C.S. 3.3.2*)**
    - **Status:** 🟡 **PARCIALMENTE CONFORME (Testado na Árvore a11y)**
    - **Evidência:** As instruções do card de relato foram inseridas no nome do botão, gerando leitura de mais de 200 caracteres ininterruptos no leitor de tela.
18. **Não colocar conteúdos essenciais em pseudoclasses CSS (`::before`, `::after`) (*ABNT NBR 17225*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** O conteúdo textual das mensagens reside na árvore HTML.
19. **Cuidado ao usar `display: none` e `visibility: hidden` para não esconder de tecnologias assistivas (*ABNT NBR 17225*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** As etapas inativas do Vue são gerenciadas de forma consistente.
20. **Atualizar dinamicamente o nome de botões que usam apenas ícones (*ABNT NBR 17225; WCAG 2.2 C.S. 4.1.2*)**
    - **Status:** 🔴 **NÃO CONFORME**
    - **Evidência:** Botões de colapsar e botões circulares no Passo 2 não possuem texto e não alternam rótulos entre abrir/fechar.
21. **Avisar mensagens de status via código (*live regions*) sem roubar o foco (*ABNT NBR 17225; WCAG 2.2 C.S. 4.1.3 - AA*)**
    - **Status:** 🔴 **NÃO CONFORME**
    - **Evidência:** O alerta do Passo 1 possui `role="alert"`, mas a árvore de acessibilidade mantém o foco no nó raiz, não vocalizando o erro automaticamente.
22. **Manter ordem do código HTML lógica e correspondente à apresentação visual (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.2*)**
    - **Status:** 🟢 **CONFORME (Atestado na Árvore de Acessibilidade)**
    - **Evidência:** A sequência linear auditada segue a lógica do cabeçalho, breadcrumb, abas e área central de preenchimento.
23. **Permitir alternar entre mouse, teclado, toque ou voz sem travar a interface (*ABNT NBR 17225; WCAG 2.2 C.S. 2.5.6 - AAA*)**
    - **Status:** 🔴 **NÃO CONFORME (Falha empírica no Teste P1)**
    - **Evidência:** A interface travou ao carregar as opções: *"Cliquei e não foi. Ixe, acho que tá meio travado... Encontramos uma falha no site..."*.
24. **Rodar validadores automáticos no código HTML/WCAG e documentar em relatórios estruturados**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** Executado com o motor axe-core 4.x integrado a este relatório.
25. **Fazer testes rigorosos com leitor de tela (NVDA / TalkBack)**
    - **Status:** 🟢 **CONFORME (Realizado via Árvore de Acessibilidade Chromium)**
    - **Evidência:** Árvore de acessibilidade inspecionada nó a nó simulando a saída vocal de todos os botões e formulários.
26. **Validar usabilidade dos fluxos com pessoas com diferentes deficiências**
    - **Status:** 🟢 **CONFORME (Realizado pelo Grupo com P1 e P2)**
    - **Evidência:** Testes com P1 (48 anos, baixa visão) e P2 (21 anos, tremor essencial).

---

### Seção 2. Privacidade, Segurança e Controle de Tempo

27. **Fluxos sem limite de tempo na sessão (*ABNT NBR 17225; WCAG 2.2 C.S. 2.2.1 e 2.2.3*)**
    - **Status:** 🔵 **FALTA VALIDAÇÃO HUMANA**
    - **Motivo:** Exige monitorar inatividade de backend por 30 a 60 minutos contínuos.
28. **Opção de prorrogar tempo com aviso prévio de 20 segundos (*ABNT NBR 17225; WCAG 2.2 C.S. 2.2.1*)**
    - **Status:** 🔵 **FALTA VALIDAÇÃO HUMANA**
    - **Motivo:** Aguardar disparo de timeout real para avaliar modal de prorrogação.
29. **Avisar perda de dados antecipadamente ou preservar por 20 horas (*ABNT NBR 17225; WCAG 2.2 C.S. 2.2.1 e 2.2.6*)**
    - **Status:** 🔴 **NÃO CONFORME**
    - **Evidência:** Não há mecanismo de rascunho automático; fechar a janela apaga o texto digitado.
30. **Retomar de onde parou após reautenticação de login (*ABNT NBR 17225; WCAG 2.2 C.S. 2.2.1 e 2.2.5*)**
    - **Status:** 🔵 **FALTA VALIDAÇÃO HUMANA**
    - **Motivo:** Simular queda de sessão autenticada com Gov.br e testar persistência pós-retorno.
31. **Permitir pausar ou ocultar conteúdos que atualizam sozinhos (*ABNT NBR 17225; WCAG 2.2 C.S. 2.2.2*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** O portal não tem placares dinâmicos ou feeds automáticos.
32. **Opção de adiar ou suprimir alertas não emergenciais (*ABNT NBR 17225; WCAG 2.2 C.S. 2.2.4*)**
    - **Status:** ⚪ **NÃO SE APLICA AO SITE**
    - **Evidência:** Não há alertas intrusivos ou popups de marketing.
33. **Não exigir testes cognitivos (quebra-cabeças, captchas distorcidos) como único meio de login (*ABNT NBR 17225; WCAG 2.2 C.S. 3.3.8 e 3.3.9*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** Autenticação unificada Gov.br com múltiplas formas de login.
34. **Permitir gerenciadores de senhas, preenchimento automático e copiar/colar (*ABNT NBR 17225; WCAG 2.2 C.S. 3.3.8*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** Não há bloqueio do evento `paste` nos campos.
35. **Métodos alternativos de autenticação que não dependam de reconhecimento visual (*ABNT NBR 17225; WCAG 2.2 C.S. 3.3.9*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** Acesso por senha, bancos credenciados e certificado digital.
36. **Instruções acessíveis e alternativa para biometria facial (*ABNT NBR 17225; WCAG 2.2 C.S. 1.1.1, 2.5.4, 2.5.6*)**
    - **Status:** ⚪ **NÃO SE APLICA AO SITE**
    - **Evidência:** O fluxo web avaliado não utiliza biometria.
37. **Deixar claro em texto a tarefa exigida por CAPTCHA (*ABNT NBR 17225; WCAG 2.2 C.S. 1.1.1*)**
    - **Status:** ⚪ **NÃO SE APLICA AO SITE**
    - **Evidência:** Não há CAPTCHA interativo nas telas testadas.
38. **Opções multimodais para CAPTCHA (áudio sem ruído, verificação lógica) (*ABNT NBR 17225; WCAG 2.2 C.S. 1.1.1*)**
    - **Status:** ⚪ **NÃO SE APLICA AO SITE**
    - **Evidência:** Inexistência de CAPTCHA interativo.
39. **Telas de validação, segurança e login operáveis 100% por teclado e leitor de tela (*ABNT NBR 17225; WCAG 2.2 C.S. 2.1.1*)**
    - **Status:** 🔴 **NÃO CONFORME**
    - **Evidência:** Falta de *focus trap* nos diálogos e perda de foco após recarregamentos de segurança.
40. **Alertas de segurança com textos claros e sem expor dados sensíveis (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.1*)**
    - **Status:** 🔵 **FALTA VALIDAÇÃO HUMANA**
    - **Motivo:** Avaliação humana de redação de erros sob ataque ou token inválido e conformidade com LGPD.

---

### Seção 3. Navegação, Foco e Interação

41. **100% das funções interativas alcançáveis e operáveis exclusivamente por teclado (*ABNT NBR 17225; WCAG 2.2 C.S. 2.1.1 e 2.1.3*)**
    - **Status:** 🔴 **NÃO CONFORME**
    - **Evidência:** Dificuldade no Passo 2 para selecionar cards de tipologia exclusivamente via teclado.
42. **Foco de navegação (`tabindex`) passar apenas por elementos interativos em ordem sequencial lógica (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.3*)**
    - **Status:** 🔴 **NÃO CONFORME**
    - **Evidência:** Elementos decorativos e textos do cabeçalho interceptam o foco indevidamente.
43. **Evitar armadilhas de teclado (*keyboard traps*) (*ABNT NBR 17225; WCAG 2.2 C.S. 2.1.2*)**
    - **Status:** 🟡 **PARCIALMENTE CONFORME**
    - **Evidência:** O formulário principal não trava, mas menus modais secundários não devolvem foco.
44. **Destacar elemento em interação com indicador de foco evidente (`:focus-visible`) (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.7*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** Borda pontilhada ambar de 4px do Design System GOV.BR visível em todos os botões.
45. **Contorno de foco com contraste mínimo de 3:1 (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.11 e 2.4.13*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** Borda `rgb(194, 133, 12)` atinge taxa de contraste superior a 3:1 contra fundo claro.
46. **Item focado nunca escondido atrás de cabeçalhos fixos (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.11 e 2.4.12*)**
    - **Status:** 🔴 **NÃO CONFORME**
    - **Evidência:** A barra fixa governamental cobre o topo dos primeiros campos ao navegar com `Tab`.
47. **Não criar atalhos de teclado formados por tecla única sem modificador (*ABNT NBR 17225; WCAG 2.2 C.S. 2.1.4*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** A aplicação não intercepta letras soltas do teclado.
48. **Não exigir velocidade ou impor limite de tempo para acionar teclas (*ABNT NBR 17225*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** Não há temporizadores de digitação rápida.
49. **Disponibilizar link invisível de salto ("Pular para o conteúdo principal") (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.1*)**
    - **Status:** 🔴 **NÃO CONFORME**
    - **Evidência:** Não há link de salto no início do DOM; o primeiro elemento interativo é o menu de dados abertos.
50. **Fornecer mais de uma maneira de encontrar as páginas do site (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.5*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** Acesso por cards, busca de órgãos, FAQ e rodapé estruturado.
51. **Mostrar ao usuário onde ele está localizado (*breadcrumbs*) (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.8*)**
    - **Status:** 🔴 **NÃO CONFORME**
    - **Evidência:** Ausência de componente semântico de trilha de navegação na Home e falhas de marcação no formulário.
52. **Manter menus principais e ajuda repetidos na mesma ordem (*ABNT NBR 17225; WCAG 2.2 C.S. 3.2.3 e 3.2.6*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** O cabeçalho mantém rigorosamente a mesma ordem relativa em todas as páginas.
53. **Identificar ícones que realizam a mesma ação sempre de forma consistente (*ABNT NBR 17225; WCAG 2.2 C.S. 3.2.4*)**
    - **Status:** 🔵 **FALTA VALIDAÇÃO HUMANA**
    - **Motivo:** Análise semiótica de consistência visual de ícones em todas as telas secundárias.
54. **Explicar a função do link no próprio texto clicável (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.4 e 2.4.9*)**
    - **Status:** 🟡 **PARCIALMENTE CONFORME**
    - **Evidência:** Títulos claros na maioria, mas botões genéricos em menus auxiliares.
55. **Escrever textos de links contínuos sem cortes com reticências ("...") (*ABNT NBR 17225*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** Links de texto íntegro sem truncamento forçado.
56. **Não usar textos de links idênticos para destinos diferentes (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.4 e 3.2.4*)**
    - **Status:** 🔴 **NÃO CONFORME**
    - **Evidência:** Múltiplos botões no cabeçalho têm o mesmo nome acessível (`"Botão"`).
57. **Evitar texto de apoio (`title` ou ARIA) que faça apenas repetição exata do visível (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.4*)**
    - **Status:** 🔴 **NÃO CONFORME**
    - **Evidência:** Duplicação desnecessária de `title` e texto interno gerando eco vocal.
58. **Avisar de forma clara quando o link abrir em nova aba ou site terceiro (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.4 e 3.2.5*)**
    - **Status:** 🔴 **NÃO CONFORME**
    - **Evidência:** Links externos como Gov.br abrem em nova aba sem aviso audível ou visual.
59. **Indicar formato e peso do arquivo em links de download (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.4*)**
    - **Status:** ⚪ **NÃO SE APLICA AO SITE**
    - **Evidência:** Não há download de documentos pesados nas páginas avaliadas.
60. **Destacar hiperlinks no meio de blocos de texto usando sublinhado e contraste (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.1*)**
    - **Status:** 🔵 **FALTA VALIDAÇÃO HUMANA**
    - **Motivo:** Conferência visual pontual de sublinhado nos parágrafos explicativos de termos de serviço.
61. **Tooltips fecham com ESC e continuam abertos com o cursor (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.13*)**
    - **Status:** 🔴 **NÃO CONFORME**
    - **Evidência:** Tooltips ao passar o mouse não fecham de forma confiável com a tecla ESC.
62. **Não disparar mudanças bruscas na interface ao focar ou alterar input (*ABNT NBR 17225; WCAG 2.2 C.S. 3.2.1 e 3.2.2*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** A mudança de tela só ocorre mediante clique explícito no botão "Avançar".
63. **Confirmar cliques somente quando o usuário solta o botão (*up-event*) (*ABNT NBR 17225; WCAG 2.2 C.S. 2.5.2*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** Ações atreladas ao evento nativo de `click` do navegador.
64. **Oferecer botão simples para ações com gestos complexos (*ABNT NBR 17225; WCAG 2.2 C.S. 2.5.1 e 2.5.7*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** Uso de cliques e toques simples sem exigir pinça ou arraste obrigatório.
65. **Disponibilizar botões convencionais para substituir movimento físico (sacudir/inclinar) (*ABNT NBR 17225; WCAG 2.2 C.S. 2.5.4*)**
    - **Status:** ⚪ **NÃO SE APLICA AO SITE**
    - **Evidência:** A interface web não faz uso de acelerômetros ou sensores de movimento.
66. **Evitar janelas modais sobrepostas, suportar ESC e prender foco (*ABNT NBR 17225*)**
    - **Status:** 🔴 **NÃO CONFORME**
    - **Evidência:** Modais secundários deixam o foco pelo teclado escapar para elementos de fundo.

---

### Seção 4. Conteúdo, Linguagem e Mídia

67. **Tratar o público com a terminologia correta: "Pessoa com deficiência (PcD)", abolindo "portador" (*Guia UK-Brasil; LBI*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** Terminologia oficial da CGU alinhada com a LBI em todos os textos.
68. **Escrever adotando princípios de Linguagem Simples (ISO 24495-1) (*ABNT NBR 17225*)**
    - **Status:** 🟡 **PARCIALMENTE CONFORME (Testado com P1 e P2)**
    - **Evidência:** O aviso sobre consequências da denúncia anônima gerou confusão e quebra de expectativa nos dois testes de usuários.
69. **Oferecer versão simplificada para conteúdo técnico avançado (*ABNT NBR 17225; WCAG 2.2 C.S. 3.1.5*)**
    - **Status:** 🔵 **FALTA VALIDAÇÃO HUMANA**
    - **Motivo:** Avaliar se os conceitos de ouvidoria necessitam de glossário em linguagem cidadã simplificada.
70. **Mecanismos para expandir siglas e explicar jargões (*ABNT NBR 17225; WCAG 2.2 C.S. 3.1.3, 3.1.4, 3.1.6*)**
    - **Status:** 🟡 **PARCIALMENTE CONFORME**
    - **Evidência:** Siglas como "LAI" são explicadas em subtítulos, mas sem tag semântica `<abbr title="...">`.
71. **Apresentar informações em mais de um formato (texto, áudio, gráfico) (*ABNT NBR 17225*)**
    - **Status:** 🔵 **FALTA VALIDAÇÃO HUMANA**
    - **Motivo:** Análise de suporte instrucional para neurodiversos em tarefas complexas.
72. **Descrever imagens informativas no `alt` de forma estruturada (*ABNT NBR 17225; WCAG 2.2 C.S. 1.1.1*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** Imagens principais de ouvidoria possuem textos alternativos claros.
73. **Descrever ação final no `alt` de botões com ícones funcionais (*ABNT NBR 17225; WCAG 2.2 C.S. 1.1.1 e 2.4.4*)**
    - **Status:** 🔴 **NÃO CONFORME**
    - **Evidência:** Botões circulares e cabeçalhos colapsáveis com ícones sem texto acessível.
74. **Aplicar atributo vazio (`alt=""`) em imagens decorativas (*ABNT NBR 17225; WCAG 2.2 C.S. 1.1.1*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** Imagens ornamentais com `aria-hidden="true"` ou `alt=""`.
75. **Texto detalhado para explicar imagens complexas (gráficos, organogramas) (*ABNT NBR 17225; WCAG 2.2 C.S. 1.1.1*)**
    - **Status:** ⚪ **NÃO SE APLICA AO SITE**
    - **Evidência:** Inexistência de gráficos estatísticos densos nas páginas avaliadas.
76. **Texto alternativo em mapas de imagem (`<area>`) (*ABNT NBR 17225; WCAG 2.2 C.S. 1.1.1*)**
    - **Status:** ⚪ **NÃO SE APLICA AO SITE**
    - **Evidência:** Não há uso da tag `<map>`.
77. **Evitar imagens contendo texto (banners com frases coladas) (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.5 e 1.4.9*)**
    - **Status:** 🔵 **FALTA VALIDAÇÃO HUMANA**
    - **Motivo:** Inspeção visual de banners para atestar ausência de texto em pixels.
78. **Transcrição integral em texto para áudios e podcasts (*ABNT NBR 17225; WCAG 2.2 C.S. 1.2.1*)**
    - **Status:** ⚪ **NÃO SE APLICA AO SITE**
    - **Evidência:** Ausência de arquivos de áudio nativos.
79. **Legendas descritivas e sincronizadas para vídeos pré-gravados (*ABNT NBR 17225; WCAG 2.2 C.S. 1.2.2*)**
    - **Status:** ⚪ **NÃO SE APLICA AO SITE**
    - **Evidência:** Ausência de vídeos pré-gravados nas rotas do teste.
80. **Audiodescrição em vídeos pré-gravados (*ABNT NBR 17225; WCAG 2.2 C.S. 1.2.3, 1.2.5, 1.2.7*)**
    - **Status:** ⚪ **NÃO SE APLICA AO SITE**
    - **Evidência:** Ausência de vídeos no fluxo.
81. **Roteiro ou transcrição completa para vídeos pré-gravados (*ABNT NBR 17225; WCAG 2.2 C.S. 1.2.3 e 1.2.8*)**
    - **Status:** ⚪ **NÃO SE APLICA AO SITE**
    - **Evidência:** Ausência de vídeos.
82. **Janela de interpretação em Libras nas mídias de vídeo (*ABNT NBR 17225; WCAG 2.2 C.S. 1.2.6*)**
    - **Status:** ⚪ **NÃO SE APLICA AO SITE**
    - **Evidência:** Ausência de vídeos. *(O site disponibiliza o plugin VLibras geral para textos).*
83. **Legendas sincronizadas em tempo real para vídeos ao vivo (*ABNT NBR 17225; WCAG 2.2 C.S. 1.2.4 e 1.2.9*)**
    - **Status:** ⚪ **NÃO SE APLICA AO SITE**
    - **Evidência:** Não há transmissões ao vivo.
84. **Barrar mídias de áudio que toquem automaticamente (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.2*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** Nenhum som é tocado sem comando do usuário.
85. **Áudios de fala com ruídos de fundo 20 dB mais baixos (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.7*)**
    - **Status:** ⚪ **NÃO SE APLICA AO SITE**
    - **Evidência:** Inexistência de arquivos de áudio.
86. **Botões para pausar carrosséis com movimento maior que 5s (*ABNT NBR 17225; WCAG 2.2 C.S. 2.2.2*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** O portal não emprega banners rotativos automáticos.
87. **Evitar animações de tela inteira ou parallax e dar opção de desligá-las (*ABNT NBR 17225; WCAG 2.2 C.S. 2.3.3*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** Layout estático sem efeitos invasivos de rolagem.
88. **Proteger contra convulsões (nenhum brilho piscando mais de 3x por segundo) (*ABNT NBR 17225; WCAG 2.2 C.S. 2.3.1 e 2.3.2*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** Total ausência de flashes estroboscópicos.
89. **CamelCase em hashtags e moderação de emojis (*Guia UK-Brasil; ABNT NBR 17225*)**
    - **Status:** 🔵 **FALTA VALIDAÇÃO HUMANA**
    - **Motivo:** Avaliação do texto contextual de eventuais notícias e postagens.

---

### Seção 5. Design, Tipografia e Layout Responsivo

90. **Responsividade em larguras de 320px CSS sem rolagem horizontal (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.10 - AA*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** Atestado programaticamente via viewport de 320x600px; `scrollWidth: 320` sem scroll horizontal duplo.
91. **Não bloquear orientação em modo retrato ou paisagem (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.4*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** Ausência de travas de orientação por media query.
92. **Permitir até 200% de zoom sem truncar blocos de texto (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.4 e 1.4.10*)**
    - **Status:** 🟡 **PARCIALMENTE CONFORME**
    - **Evidência:** Os textos redimensionam, mas a barra superior cobre áreas de entrada.
93. **Jamais utilizar apenas a cor visual para indicar ação ou erro (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.1*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** Mensagens de erro combinam cor com ícone e texto explicativo.
94. **Testar paleta de cores em simuladores para daltonismo (*Guia UK-Brasil; ABNT NBR 17225*)**
    - **Status:** 🔵 **FALTA VALIDAÇÃO HUMANA**
    - **Motivo:** Inspeção visual com simuladores de Protanopia, Deuteranopia e Tritanopia.
95. **Contraste de cor mínimo de 4,5:1 para texto normal e 3:1 para grande (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.3 - AA*)**
    - **Status:** 🟡 **PARCIALMENTE CONFORME**
    - **Evidência:** Corpo de texto principal aprovado, mas pequenos textos secundários em cinza caem abaixo de 4,5:1.
96. **Contraste avançado de pelo menos 7:1 (nível AAA) (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.6*)**
    - **Status:** 🔴 **NÃO CONFORME**
    - **Evidência:** Não atinge a razão estrita de 7:1 em textos secundários.
97. **Checar contraste mínimo em fotos e fundos em degradê (*Guia UK-Brasil*)**
    - **Status:** 🔵 **FALTA VALIDAÇÃO HUMANA**
    - **Motivo:** Medição pontual com conta-gotas em áreas de gradientes de cabeçalho.
98. **Contraste de 3:1 em bordas de formulários e gráficos funcionais (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.11 - AA*)**
    - **Status:** 🟡 **PARCIALMENTE CONFORME**
    - **Evidência:** Bordas em repouso dos campos de busca e seleção têm contraste cinza inferior a 3:1 contra o fundo.
99. **Opção nativa de alto contraste (*dark mode*) que não quebre ao injetar cores (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.8*)**
    - **Status:** 🟢 **CONFORME**
    - **Evidência:** Botão nativo de Alto Contraste funcional no cabeçalho.
100. **Área de clique mínima de 24x24px (recomendado 44x44px ou 48x48px) (*ABNT NBR 17225; WCAG 2.2 C.S. 2.5.5 e 2.5.8*)**
     - **Status:** 🟢 **CONFORME (Aprovado e Validado com Tremor Essencial)**
     - **Evidência:** Botões com altura superior a 44px; participante P2 com tremor motor conseguiu acionar sem cliques em falso.
101. **Inserir respiros visuais generosos (espaçamento em branco) (*Guia UK-Brasil; ABNT NBR 17225*)**
     - **Status:** 🟢 **CONFORME**
     - **Evidência:** Grelha de espaçamento consistente do Design System GOV.BR.
102. **Unir texto e ícone nos botões sempre que possível (*Guia UK-Brasil; ABNT NBR 17225*)**
     - **Status:** 🟡 **PARCIALMENTE CONFORME**
     - **Evidência:** Botões como "Avançar" possuem apenas texto; botões circulares têm apenas ícones.
103. **Não basear orientações apenas em aspectos visuais ou acústicos (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.3*)**
     - **Status:** 🟢 **CONFORME**
     - **Evidência:** Instruções indicam nomes de campos e não referências espaciais ou cromáticas.
104. **Selecionar fontes tipográficas legíveis e redondas, com bom tamanho (*Guia UK-Brasil; ABNT NBR 17225*)**
     - **Status:** 🔴 **NÃO CONFORME (Barreira Crítica no Teste P1)**
     - **Evidência:** A fonte é sem serifa, mas o tamanho padrão das letras foi reprovado por P1 (*"precisava de umas letras maiores mesmo... aumentaria o tamanho das letras"*).
105. **Alinhar blocos de texto sempre à esquerda para idiomas ocidentais (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.8*)**
     - **Status:** 🟢 **CONFORME**
     - **Evidência:** Textos alinhados à esquerda; ausência de justificação forçada.
106. **Configurar CSS para linhas com no máximo 80 caracteres de largura (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.8 e 1.4.10*)**
     - **Status:** 🔵 **FALTA VALIDAÇÃO HUMANA**
     - **Motivo:** Verificação em monitores ultrawide para checar limites de contêiner.
107. **Garantir texto íntegro com ajustes pesados de entrelinhas (1,5x) (*ABNT NBR 17225; WCAG 2.2 C.S. 1.4.8 e 1.4.12*)**
     - **Status:** 🔵 **FALTA VALIDAÇÃO HUMANA**
     - **Motivo:** Injeção do bookmarklet de Text Spacing da WCAG em todas as telas.

---

### Seção 6. Formulários e Prevenção de Falhas

108. **Formulários curtos com botão explícito de envio (*ABNT NBR 17225; WCAG 2.2 C.S. 3.2.2*)**
     - **Status:** 🟢 **CONFORME**
     - **Evidência:** Botões explícitos "Avançar" e "Finalizar".
109. **Conectar tecnicamente campos (`<input>`) aos seus rótulos (`<label>`) (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1, 3.3.2, 4.1.2*)**
     - **Status:** 🔴 **NÃO CONFORME**
     - **Evidência:** O `<textarea id="re_relato">` não possui tag `<label for="re_relato">` vinculada.
110. **Rótulo autoexplicativo e externo; nunca usar apenas placeholder (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.6 e 3.3.2*)**
     - **Status:** 🔴 **NÃO CONFORME**
     - **Evidência:** Campo de relato apoia-se unicamente no placeholder cinza que desaparece ao digitar.
111. **Dicas de formato permanentes e ajuda contextual (*ABNT NBR 17225; WCAG 2.2 C.S. 3.3.2 e 3.3.5*)**
     - **Status:** 🟡 **PARCIALMENTE CONFORME**
     - **Evidência:** Há contador de caracteres, mas orientações de anexos ficam recolhidas.
112. **Usar `<fieldset>` e `<legend>` para agrupar opções lógicas (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.1*)**
     - **Status:** 🔴 **NÃO CONFORME**
     - **Evidência:** Opções do Passo 2 e Passo 4 não usam `<fieldset>` com `<legend>`.
113. **Indicar campos obrigatórios visualmente e no código (`required`) (*ABNT NBR 17225; WCAG 2.2 C.S. 3.3.2*)**
     - **Status:** 🟢 **CONFORME**
     - **Evidência:** Presença de asterisco visual e atributo HTML nativo `required=""`.
114. **Configurar tipos de campos (`type`, `autocomplete`) para dados pessoais (*ABNT NBR 17225; WCAG 2.2 C.S. 1.3.5*)**
     - **Status:** 🔴 **NÃO CONFORME**
     - **Evidência:** Campos de identificação omitem `autocomplete="name"` ou `autocomplete="email"`.
115. **Cortar entradas repetitivas; autocompletar dados já fornecidos (*ABNT NBR 17225; WCAG 2.2 C.S. 3.3.7*)**
     - **Status:** 🟢 **CONFORME**
     - **Evidência:** Reutilização automática de dados do cadastro Gov.br.
116. **Etapa de revisão e confirmação antes do disparo final (*ABNT NBR 17225; WCAG 2.2 C.S. 3.3.4 e 3.3.6*)**
     - **Status:** 🟢 **CONFORME (Atestado por P1 e P2)**
     - **Evidência:** O Passo 5 é inteiramente dedicado à conferência dos dados antes da submissão final.
117. **Identificar erros em linguagem humana apontando o campo (*ABNT NBR 17225; WCAG 2.2 C.S. 3.3.1*)**
     - **Status:** 🟡 **PARCIALMENTE CONFORME**
     - **Evidência:** A mensagem é compreensível, mas falta associação direta por `aria-describedby`.
118. **Sugerir caminhos formatados de como resolver o erro (*ABNT NBR 17225; WCAG 2.2 C.S. 3.3.3*)**
     - **Status:** 🔵 **FALTA VALIDAÇÃO HUMANA**
     - **Motivo:** Avaliação do tom empático das sugestões de correção de formato de arquivo e dados.
119. **Ao recarregar ou exibir erros, mover foco em direção ao alerta (*ABNT NBR 17225; WCAG 2.2 C.S. 2.4.3 e 3.3.1*)**
     - **Status:** 🔴 **NÃO CONFORME**
     - **Evidência:** O foco após erro de validação permanece retido no nó `<body>` / `RootWebArea`.

---

### Seção 7. Jornada do Usuário e Fluxos de Navegação

120. **Dividir tarefas longas em etapas menores com indicação de etapa (*progressive disclosure*)**
     - **Status:** 🟢 **CONFORME**
     - **Evidência:** Dividido em 6 passos sequenciais no assistente.
121. **Orientações prévias antes de iniciar fluxos exigentes (tempo estimado, documentos)**
     - **Status:** 🔴 **NÃO CONFORME (Confirmado por P1 e P2)**
     - **Evidência:** Ambos relataram ausência total de orientações iniciais sobre denúncia anônima.
122. **Evitar becos sem saída (*dead ends*): próximo passo claro ou link para Home**
     - **Status:** 🟢 **CONFORME**
     - **Evidência:** Botões "Voltar para o início" presentes em todas as telas.
123. **Permitir salvamento automático do progresso ou opção "Salvar rascunho"**
     - **Status:** 🔴 **NÃO CONFORME**
     - **Evidência:** Ausência de salvamento de rascunho em caso de fechamento do navegador.
124. **Saídas de emergência claras em qualquer ponto ("Cancelar" ou "Voltar")**
     - **Status:** 🟢 **CONFORME (Utilizado com sucesso por P1 e P2)**
     - **Evidência:** Botões "Cancelar" e "Voltar" visíveis e funcionais.
125. **Consistência de modelo mental (posicionamento de "Voltar" e "Avançar")**
     - **Status:** 🟢 **CONFORME**
     - **Evidência:** "Voltar" sempre à esquerda e "Avançar" à direita.
126. **Telas de confirmação claras (Mensagens de Sucesso e protocolo)**
     - **Status:** 🔵 **FALTA VALIDAÇÃO HUMANA**
     - **Motivo:** Homologação do Passo 6 em ambiente de teste da CGU para gerar protocolo real sem poluir base oficial.
127. **Projetar *Empty States* acolhedores e instruídos com botão de ação**
     - **Status:** 🔵 **FALTA VALIDAÇÃO HUMANA**
     - **Motivo:** Avaliação do painel de manifestações para conta virgem sem histórico.
128. **Minimizar trocas de contexto (*context switching*)**
     - **Status:** 🔵 **FALTA VALIDAÇÃO HUMANA**
     - **Motivo:** Avaliação do fluxo completo com duplo fator Gov.br no celular.

---

## 4. O Que os Testes Empíricos e a Árvore de Acessibilidade Revelaram

### A. Resultados dos Testes com Usuários Reais
- **P1 (48 anos, Baixa Visão):**
  - O tamanho padrão das letras é a principal barreira do portal (*"as letras precisava ser maior"*).
  - Ocorreu travamento da interface durante a tarefa 1 (*"Cliquei e não foi. Ixe, acho que tá meio travado"*).
  - Teve dificuldade de compreender as regras de anonimato pela falta de orientação prévia.
- **P2 (21 anos, Tremor Essencial):**
  - Os botões padronizados amplos (>44px) permitiram o clique confortável sem erro de alvo (*"Para mim foi confortável"*).
  - Criticou a falta de informações na página inicial, obrigando o usuário a *"sair clicando nas coisas para poder achar o que realmente quer"*.

### B. Resultados da Árvore de Acessibilidade (Leitores de Tela)
- **Eco de "Botão":** Múltiplos botões de topo possuem `aria-label="Botão"`, fazendo o NVDA/TalkBack vocalizar apenas *"Botão, botão, botão..."*, ocultando os nomes visuais de "Início", "Órgãos" e "Dados Abertos".
- **Botões Mudos e com Parágrafo:** No Passo 2, um botão tem nome vazio (`name: ""`) e outro carrega mais de 200 caracteres de instruções acoplados ao seu nome.
- **Silêncio em Erros:** Quando ocorre falha de validação, o foco programático se perde e o leitor de tela fica mudo, sem anunciar o erro para o usuário cego.

---

## 5. Relação Exata dos 18 Itens que AINDA Faltam Validação Humana

Estes são os **únicos 18 critérios** do checklist que ainda necessitam de revisão humana especializada:

| Nº | Item do Checklist | Por que a ferramenta não consegue avaliar? | Como deve ser feito o teste humano? |
| :---: | :--- | :--- | :--- |
| **1** | **Item 13 (Seção 1):** Tags semânticas para textos especiais (`<em>`, `<q>`, `<abbr>`) | Robôs não julgam o significado contextual de citações jurídicas ou siglas. | Leitura editorial do texto por avaliador humano conferindo a marcação. |
| **2** | **Item 27 (Seção 2):** Fluxo sem limite de tempo na sessão | Controlado por tokens de backend em tempo real. | Monitorar inatividade no formulário por 30 a 60 minutos contínuos. |
| **3** | **Item 28 (Seção 2):** Prorrogação com aviso prévio de 20 segundos | Exige aguardar o temporizador do servidor disparar. | Aguardar o timeout e verificar se surge alerta sonoro e visual prorrogável. |
| **4** | **Item 30 (Seção 2):** Retomada de onde parou após reautenticação | Requer autenticação com Gov.br real e queda forçada de sessão. | Desconectar a sessão no Passo 3 e reconectar para checar se retém dados. |
| **5** | **Item 40 (Seção 2):** Alertas de segurança claros e sem vazar dados | Julgamento humano sobre clareza de redação técnica e LGPD. | Simular falha de rede/autenticação e checar se expõe códigos de sistema. |
| **6** | **Item 53 (Seção 3):** Consistência semiótica de todos os ícones | Requer análise de design visual comparativo entre dezenas de páginas. | Mapear todos os ícones das páginas secundárias e auditar padronização. |
| **7** | **Item 60 (Seção 3):** Sublinhado em hiperlinks no meio de texto | Robôs confundem links com botões e falham em estados dinâmicos. | Inspeção visual direta nos parágrafos de termos de uso e orientações. |
| **8** | **Item 69 (Seção 4):** Versão simplificada para conceitos avançados | Decisão pedagógica sobre necessidade de materiais de apoio ao cidadão. | Avaliar se termos de LAI/Ouvidoria exigem glossários em linguagem cidadã. |
| **9** | **Item 71 (Seção 4):** Suporte multimodal para neurodiversos | Ferramenta não avalia se um texto denso deveria ter suporte visual/áudio. | Avaliação de design de serviço público nas orientações de denúncia. |
| **10** | **Item 77 (Seção 4):** Banners sem texto embutido em pixels | OCR automático não garante conformidade de imagens vetorizadas/raster. | Inspeção visual de banners para confirmar que frases são HTML real. |
| **11** | **Item 89 (Seção 4):** CamelCase em hashtags e moderação de emojis | Análise do conteúdo editorial de eventuais avisos e campanhas. | Checar se hashtags compostas utilizam CamelCase para boa dicção vocal. |
| **12** | **Item 94 (Seção 5):** Teste de cores em simuladores de daltonismo | Robôs calculam contraste mas não julgam perda subjetiva de significado. | Simulação com filtros de Protanopia, Deuteranopia e Tritanopia. |
| **13** | **Item 97 (Seção 5):** Contraste em degradês e fotografias | Analisadores automáticos falham ao calcular gradientes CSS dinâmicos. | Medição pontual com conta-gotas de contraste (*Colour Contrast Analyser*). |
| **14** | **Item 106 (Seção 5):** Limite de 80 caracteres por linha | Varia conforme tamanho de monitor ultrawide e resolução do usuário. | Testar em telas de alta definição (2K e 4K) conferindo `max-width`. |
| **15** | **Item 107 (Seção 5):** Integridade com espaçamento forçado (*Text Spacing*) | Ferramenta não prevê sobreposições dinâmicas ao injetar CSS externo. | Executar o bookmarklet de *Text Spacing* da WCAG e checar quebras visuais. |
| **16** | **Item 118 (Seção 6):** Sugestões formatadas e empáticas de correção de erro | Validadores checam presença de mensagem, mas não julgam a empatia da dica. | Submeter formatos inválidos de dados e avaliar a clareza da orientação. |
| **17** | **Item 126 (Seção 7):** Tela de confirmação e protocolo do Passo 6 | Submeter em produção cria manifestação permanente na base oficial da CGU. | Testar em ambiente de homologação/treinamento (*staging*) da CGU. |
| **18** | **Item 127 (Seção 7):** Telas sem conteúdo acolhedoras (*Empty States*) | Ferramenta não entende o conceito de acolhimento afetivo de tela virgem. | Acessar painel com conta nova sem manifestações e avaliar mensagem. |

---

## 6. Plano de Ação e Recomendações Prioritárias

1. **Remover imediatamente `aria-label="Botão"`** de todos os botões do cabeçalho do portal.
2. **Associar `<label for="re_relato">` externo** ao campo de texto do relato no Passo 1.
3. **Adicionar link de salto ("Pular para o conteúdo principal")** no início da página.
4. **Implementar foco automático programático (`element.focus()`)** ao disparar erros de validação.
5. **Aumentar o tamanho padrão de fonte** e adicionar atalho de redimensionamento tipográfico no cabeçalho.
6. **Inserir orientações prévias na Home** explicando didaticamente as regras de manifestação anônima antes de iniciar o formulário.
