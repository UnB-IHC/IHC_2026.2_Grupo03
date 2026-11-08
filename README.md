# IHC 2026.2 — Grupo 03: Avaliação de Acessibilidade Digital

Repositório dedicado ao estudo, sistematização e avaliação prática de acessibilidade digital para a disciplina de Interação Humano-Computador (IHC).

---

## 📚 Documentos Disponíveis no Repositório

1. 📋 **[Guia e Checklist de Acessibilidade Digital](file:///c:/Users/pluca/IHC_2026.2_Grupo03/GUIA_ACESSIBILIDADE.md)**
   - O guia completo e estruturado de diretrizes de acessibilidade para web, baseado em:
     - **ABNT NBR 17225:2025**
     - **W3C WCAG 2.2** (Níveis A, AA e AAA)
     - **Guia de Boas Práticas de Acessibilidade Digital (Reino Unido – Brasil)**
   - Reúne as 7 seções práticas com cada um dos seus itens de checklist e as justificativas técnicas e humanas detalhadas na seção *"Entendendo os 'Porquês'"*.

2. 🔍 **[Relatório de Avaliação Técnica de Acessibilidade — Portal Fala.BR](file:///c:/Users/pluca/IHC_2026.2_Grupo03/AVALIACAO_ACESSIBILIDADE_FALABR.md)**
   - Avaliação técnica e detalhada aplicada ao portal da Controladoria-Geral da União (**Fala.BR**):
     - **Página Inicial:** `https://falabr.cgu.gov.br/v2/`
     - **Fluxo de Registro de Manifestação em 6 Passos:** `https://falabr.cgu.gov.br/v2/manifestacoes/registrar` (Relato, Tipo e Assunto, Local, Envolvidos, Revisão e Conclusão).
   - Auditoria automatizada com navegador real *Headless Chrome* e motor de regras **axe-core 4.x**, contendo:
     - Diagnóstico completo de cada um dos critérios do checklist;
     - Classificação explícita do que foi aprovado, reprovado, o que **requer teste humano** (com as justificativas fundamentadas) e o que **não se aplica ao site**;
     - Análise etapa por etapa do fluxo de manifestação;
     - Plano de correções prioritárias recomendadas.

---

## 🛠️ Tecnologias e Ferramentas Empregadas na Avaliação

- **Puppeteer & Google Chrome Headless:** Inspeção profunda de árvore DOM e Single Page Application (Vue.js).
- **axe-core:** Validador e motor de regras para conformidade internacional WCAG 2.2 e ABNT NBR 17225.
- **Python / Node.js:** Rastreio estruturado de nós de falhas, seletores, testes de contraste e responsividade.
