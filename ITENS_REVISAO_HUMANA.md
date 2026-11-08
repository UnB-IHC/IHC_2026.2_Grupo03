# Checklist Atualizado: Itens que Restam Validação Humana Estrita

**Data da Consolidação:** Novembro de 2026 (Pós-auditorias automatizadas, testes de P1 e P2 e testes empíricos do avaliador humano)

Com os testes práticos que você realizou diretamente no portal, conseguimos validar mais pontos decisivos:
1. **Envio de arquivo não suportado (`.pptx`):** O sistema retornou mensagem clara e amigável (*"tipo não permitido"*), sem expor erros de backend ou dados sensíveis (**Item 40: 🟢 CONFORME**).
2. **Teste de recarregamento (F5):** Ao dar F5, o texto digitado sumiu completamente, confirmando a ausência de rascunho automático local (**Itens 29 e 123: 🔴 NÃO CONFORME SEVERO**).
3. **Avaliação de Linguagem:** O texto das instruções e do fluxo foi avaliado como acessível e compreensível (**Item 69: 🟢 CONFORME**).
4. **Verificação do VLibras:** Inspecionamos todas as etapas do fluxo de manifestações e confirmamos que **o plugin do VLibras está presente e carregado em 100% das 6 etapas do assistente** (`https://vlibras.gov.br/app/vlibras-plugin.js`).

---

## 1. Novo Painel Quantitativo

- **Total de critérios do checklist:** 127 itens
- **Itens diagnosticados e resolvidos:** **121 itens (95,3%)**
- **Itens que AINDA dependem de validação humana ou têm restrição ética:** **Apenas 5 a 6 itens (4,7%)**

---

## 2. Relação dos Únicos Itens Restantes

| Nº | Item do Checklist | Por que o robô não faz sozinho? | O que é necessário para avaliar? |
| :---: | :--- | :--- | :--- |
| **1** | **Item 30 (Seção 2):** Retomada de onde parou após reautenticação | Requer login pessoal com conta Gov.br real (CPF e senha pessoal). | Desconectar a sessão no Passo 3 e verificar se os dados persistem ao relogar pelo Gov.br. |
| **2** | **Item 27 (Seção 2):** Tempo real de inatividade de sessão de backend | Controlado pelo servidor em tempo real. | Deixar a página aberta sem mexer por 30 a 60 minutos e checar o encerramento. |
| **3** | **Item 71 (Seção 4):** Suporte multimodal didático para neurodiversos | Julgamento pedagógico sobre inclusão de infográficos em denúncias. | Avaliar se a diferenciação entre denúncia anônima e reservada se beneficiaria de infográficos didáticos. |
| **4** | **Item 77 (Seção 4):** Banners sem texto embutido em pixels | Garantir que eventuais novos banners institucionais não usem tipografia rasterizada. | Auditoria visual humana periódica nos materiais publicitários da página inicial. |
| **5** | **Item 126 (Seção 7):** Tela de confirmação e protocolo (Passo 6) | **Restrição Ética e Legal:** Submeter em produção cria denúncia/ouvidoria oficial real no banco da CGU. | Acessar ambiente de homologação/staging da CGU para gerar protocolo simulado com autorização. |
