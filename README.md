# IHC 2026.2 — Grupo 03: Avaliação de Acessibilidade Digital

Repositório dedicado ao estudo, sistematização e avaliação prática de acessibilidade digital para a disciplina de Interação Humano-Computador (IHC).

---

## 📚 Documentos Disponíveis no Repositório

1. 🏆 **[Relatório Geral Unificado de Aplicação do Checklist](file:///c:/Users/pluca/IHC_2026.2_Grupo03/RELATORIO_GERAL_APLICACAO_CHECKLIST.md)** *(DOCUMENTO MASTER CONSOLIDADO)*
   - **O documento definitivo que reúne tudo em um único lugar:**
     - Aplicação integral item a item dos **127 critérios do checklist**;
     - Auditoria técnica automatizada com motor **axe-core 4.x**;
     - Auditoria da **Árvore de Acessibilidade (*Accessibility Tree*)** do leitor de tela (simulação de saída vocal exata);
     - Avaliação empírica com usuários reais (**P1:** 48 anos com baixa visão; **P2:** 21 anos com tremor essencial) e pontuação SUS;
     - Diagnóstico completo dos **6 passos do registro de manifestações**;
     - Relação exata dos **18 itens que ainda demandam validação humana especializada**.

2. 📋 **[Guia e Checklist de Acessibilidade Digital](file:///c:/Users/pluca/IHC_2026.2_Grupo03/GUIA_ACESSIBILIDADE.md)**
   - O guia teórico completo baseado na **ABNT NBR 17225:2025**, **WCAG 2.2** e **Guia UK-Brasil**, contendo as 7 seções e o detalhamento pedagógico dos *"Porquês"*.

2. 🔍 **[Relatório de Avaliação Técnica de Acessibilidade — Portal Fala.BR](file:///c:/Users/pluca/IHC_2026.2_Grupo03/AVALIACAO_ACESSIBILIDADE_FALABR.md)**
   - Avaliação técnica e detalhada aplicada ao portal da Controladoria-Geral da União (**Fala.BR**):
     - **Página Inicial:** `https://falabr.cgu.gov.br/v2/`
     - **Fluxo de Registro de Manifestação em 6 Passos:** `https://falabr.cgu.gov.br/v2/manifestacoes/registrar` (Relato, Tipo e Assunto, Local, Envolvidos, Revisão e Conclusão).
   - Auditoria automatizada com navegador real *Headless Chrome* e motor de regras **axe-core 4.x**, contendo:
     - Diagnóstico completo de cada um dos critérios do checklist;
     - Classificação explícita do que foi aprovado, reprovado, o que **requer teste humano** (com as justificativas fundamentadas) e o que **não se aplica ao site**;
     - Análise etapa por etapa do fluxo de manifestação;
     - Plano de correções prioritárias recomendadas.

3. 👥 **[Checklist de Itens que Demandam Revisão Humana Obrigatória](file:///c:/Users/pluca/IHC_2026.2_Grupo03/ITENS_REVISAO_HUMANA.md)**
   - Documento detalhado e focado exclusivamente em **todos os critérios que robôs não conseguem avaliar** com segurança:
     - Justificativa técnica e normativa (ABNT NBR 17225 / WCAG 2.2 / Guia UK-BR);
     - Por que as ferramentas automatizadas falham nesses cenários;
     - Como a equipe de avaliadores humanos e pessoas com deficiência (PcD) deve proceder em cada teste.

4. 🔊 **[Simulação e Auditoria Técnica: Como os Leitores de Tela Leem o Fala.BR](file:///c:/Users/pluca/IHC_2026.2_Grupo03/ANALISE_LEITORES_DE_TELA.md)**
   - Extração profunda da **Árvore de Acessibilidade (*Accessibility Tree*)** do Chromium (exatamente a mesma camada computada entregue ao NVDA, JAWS e TalkBack):
     - Transcrição do que o sintetizador de voz efetivamente anuncia em cada botão e campo;
     - Diagnóstico do "eco de botões fantasmas" (`aria-label="Botão"`);
     - Verificação da leitura da caixa de relato, stepper de 6 etapas e alertas de erro.

---

## 🛠️ Tecnologias e Ferramentas Empregadas na Avaliação

- **Puppeteer & Google Chrome Headless:** Inspeção profunda de árvore DOM e Single Page Application (Vue.js).
- **axe-core:** Validador e motor de regras para conformidade internacional WCAG 2.2 e ABNT NBR 17225.
- **Python / Node.js:** Rastreio estruturado de nós de falhas, seletores, testes de contraste e responsividade.
