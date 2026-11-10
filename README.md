# IHC 2026.2 — Grupo 03: Avaliação de Acessibilidade Digital e Usabilidade

Repositório dedicado ao estudo, sistematização e avaliação prática de acessibilidade digital para a disciplina de **Interação Humano-Computador (IHC)** na **Universidade de Brasília (UnB)**.

---

## Estrutura de Arquivos do Repositório

### 1. [Guia e Pocket de Acessibilidade Digital e IHC](./GUIA_ACESSIBILIDADE.md) (`GUIA_ACESSIBILIDADE.md`)
- O guia teórico, metodológico e checklist fundamental de acessibilidade e IHC, integrando:
  - **Bases Normativas:** ABNT NBR 17225:2025, W3C WCAG 2.2 (A, AA, AAA), Guia Reino Unido-Brasil e LBI (Lei nº 13.146/2015);
  - **Fundamentos de IHC e UX:** Personas inclusivas e Espectro de Habilidades, Design Empático e Mapa de Empatia, Service Blueprint (5 camadas integradas à jornada), Canvas de IHC / UX Canvas;
  - **As 10 Heurísticas de Usabilidade de Nielsen** aplicadas à acessibilidade;
  - **Catálogo de Ferramentas:** Leitores de tela (NVDA, TalkBack, VoiceOver), validadores (axe-core, WAVE, Lighthouse, ASES, VLibras), simuladores de cor e escala SUS;
  - **Pocket Checklist Normativo:** 127 itens distribuídos em 7 classes temáticas e a seção completa de *"Entendendo os Porquês"*.

### 2. [Resultados da Avaliação Macro e Micro — Portal Fala.BR](./RESULTADOS_AVALIACAO.md) (`RESULTADOS_AVALIACAO.md`)
- **Visão Macro:** Painel executivo consolidado com percentuais e distribuição por classes de conformidade (testes automatizados, testes com usuários e testes de código).
- **Visão Micro:** Avaliação individual e detalhada passando por **cada um dos 127 checks**, acompanhado de evidências técnicas, comportamento na Árvore de Acessibilidade (*Accessibility Tree*), diagnóstico dos 6 passos do formulário e restrições éticas de produção.

### 3. [Análise de Dados, Gráficos e Métodos de IHC — Fala.BR](./ANALISE_DADOS_ACESSIBILIDADE.md) (`ANALISE_DADOS_ACESSIBILIDADE.md`)
- Análise quantitativa e qualitativa sintetizada de forma leve e direta, integrando:
  - **Gráficos e Indicadores:** Distribuição do checklist (45,8% conforme em itens aplicáveis) e decomposição das falhas críticas;
  - **Métricas Empíricas de Testes:** Cronometragem por tarefa (P1 — Baixa Visão vs. P2 — Tremor Essencial) e escore SUS (68,75 pontos);
  - **Personas Inclusivas do Fala.BR:** Maria Helena (Baixa Visão) e Lucas Ferreira (Tremor Essencial);
  - **Mapa de Empatia:** Mapeamento sensorial e emocional da interação com o Fala.BR;
  - **Service Blueprint:** Mapeamento em 5 camadas do fluxo de denúncia anônima com pontos de ruptura;
  - **UX Canvas do Fala.BR:** Framework estratégico de intervenção e acessibilidade;
  - **Avaliação das 10 Heurísticas de Nielsen no Fala.BR:** Diagnóstico heurístico sistemático de cada princípio com severidade;
  - **Síntese Instrumental:** Ferramentas orquestradas na auditoria.

### 4. [Relatório Final do Teste de Usabilidade (PDF Base)](./RELATORIO_TESTE_USABILIDADE.md) (`RELATORIO_TESTE_USABILIDADE.md`)
- Documento consolidado conforme as regras formais da especificação oficial `Tg_IHC-03` (limite de 6 páginas):
  - Perfil dos participantes (estudo de caso com deficiência);
  - Métricas e tempos reais cronometrados em vídeo com desfechos oficiais;
  - Decomposição psicométrica do Questionário SUS (68,75 pontos);
  - Síntese das entrevistas inicial e final;
  - **Tabela Oficial de Problemas de Usabilidade com Severidade de Nielsen (0 a 4)**;
  - Relação direta dos problemas com os itens do Pocket de Acessibilidade;
  - **Cinco Recomendações Priorizadas** fundamentadas nas evidências;
  - Declaração de uso ético de Inteligência Artificial conforme Seção 6.

### 5. Pasta de Testes de Usuário e Entrevistas (`entrevistas/`)
- **[Roteiro da Sessão de Teste de Usabilidade](./entrevistas/roteiro_entrevista.md)** (`roteiro_entrevista.md`): Protocolo completo de acolhida, entrevista inicial, tarefas guiadas (*think-aloud*), questionário SUS e encerramento.
- **[Transcrição Participante 1](./entrevistas/transcricao_participante_1.md)** (`transcricao_participante_1.md`): Mulher, 48 anos, baixa visão / presbiopia severa (demanda ampliação e zoom).
- **[Transcrição Participante 2](./entrevistas/transcricao_participante_2.md)** (`transcricao_participante_2.md`): Homem, 20 anos, com limitação motora (Tremor Essencial).
- **Termos de Consentimento Assinados (PDF):**
  - `Termo_Consentimento_Participante_1_assinado.pdf`
  - `Termo_Consentimento_Participante_2_assinado.pdf`
