# Checklist Atualizado: Itens que Ainda Demandam Revisão Humana

**Última Atualização:** Novembro de 2026 (Pós-testes empíricos com P1 e P2)

Após a realização dos testes práticos de usabilidade com os dois usuários reais:
- **Participante 1 (P1):** 48 anos, com problemas de vista / baixa visão (presbiopia severa).
- **Participante 2 (P2):** 21 anos, com limitação motora (**Tremor Essencial**).

O volume de itens pendentes de revisão humana foi **reduzido de 40 itens para 28 itens na tabela ampla (ou 19 critérios específicos)**.

---

## 1. Resumo Quantitativo

- **Total de critérios do checklist:** 127 itens
- **Itens que precisavam de avaliação humana originalmente:** 40 itens (31,5%)
- **Itens avaliados e solucionados pelos testes de P1 e P2:** 12 itens (9,4%)
- **Itens que AINDA precisam de revisão humana:** **28 itens (22,0%)**

---

## 2. O que os Testes com P1 e P2 já Resolveram (12 itens avaliados)

1. **Item 1.26:** Validação com pessoas com deficiência (P1 - baixa visão; P2 - tremor essencial) -> **Validado em campo**.
2. **Item 1.23:** Estabilidade e travamento da interface durante uso real -> **Reprovado (travamento na tarefa de P1)**.
3. **Item 5.15:** Adequação de tipografia e tamanho de fontes para baixa visão -> **Reprovado severamente por P1**.
4. **Item 5.11:** Tamanho de botão e área de clique para tremor essencial -> **Aprovado na prática por P2 (>44px)**.
5. **Item 7.2:** Orientações prévias de tarefa e denúncia anônima -> **Reprovado por ambos os usuários**.
6. **Item 4.2:** Linguagem Simples nas orientações de denúncia anônima -> **Parcialmente reprovado por ambiguidade**.
7. **Itens 6.9, 7.5 e 7.6:** Clareza da tela de Revisão (Passo 5) e saídas de emergência (Voltar/Cancelar) -> **Aprovado por ambos**.

---

## 3. Os 28 Itens (19 Critérios-Chave) que AINDA Precisam de Revisão Humana

Estes itens dividem-se em 4 frentes de trabalho humano que não puderam ser cobertas pelos testes de P1 e P2:

### Frente A: Testes com Leitor de Tela Puro (Pessoas Cegas - NVDA / TalkBack)
*(P1 utilizou visão com zoom e P2 utilizou visão direta; nenhum navegou exclusivamente por áudio)*
1. **Item 1.5:** Teste manual navegando 100% via teclado com leitor de tela (NVDA no desktop e TalkBack no mobile).
2. **Item 1.3:** Conferência da ordem auditiva do DOM vs. ordem visual da tela.
3. **Item 1.13:** Checagem semântica de textos especiais (`<em>`, `<q>`, `<abbr>`, citações legais).
4. **Item 1.17:** Clareza auditiva de instruções em componentes customizados de upload e seleção.
5. **Item 1.4:** Alternância concorrente com comandos de voz (ex.: *Dragon* ou *Voice Access*).

### Frente B: Avaliação Especializada de Design Visual e Visão de Cores
*(Exige simuladores de daltonismo e ferramentas manuais de contraste pontual)*
6. **Item 5.1:** Simulação visual de Protanopia, Deuteranopia e Tritanopia (daltonismo).
7. **Item 5.2:** Medição pontual de contraste em fotos e degradês CSS com conta-gotas (*Colour Contrast Analyser*).
8. **Item 5.3:** Conferência do limite de 80 caracteres por linha em monitores *ultrawide*.
9. **Item 5.4:** Injeção do bookmarklet de *Text Spacing* da WCAG para checar quebras de caixa.
10. **Item 3.2:** Inspeção visual de sublinhado em hiperlinks inseridos no meio de parágrafos.
11. **Item 4.4:** Identificação visual de textos embutidos em pixels em banners promocionais.
12. **Item 3.1:** Análise semiótica de consistência dos ícones em todas as telas secundárias.

### Frente C: Testes de Sessão Prolongada e Segurança
*(Exige aguardar minutos/horas de inatividade de backend e queda forçada de autenticação)*
13. **Item 2.1:** Medição do tempo limite real de inatividade da sessão de backend.
14. **Item 2.2:** Verificação do surgimento do aviso prévio de 20 segundos antes de derrubar o formulário.
15. **Item 2.3:** Teste de reautenticação no Gov.br para checar se preserva o rascunho preenchido.
16. **Item 2.4:** Avaliação qualitativa de clareza das mensagens de erro e proteção de dados sensíveis (LGPD).

### Frente D: Homologação do Passo 6 e Fluxos de Borda
*(Exige ambiente de homologação/staging para não poluir o banco de dados oficial da CGU)*
17. **Item 7.1:** Avaliação da tela de conclusão do Passo 6 (emissão do número de protocolo e comprovante oficial).
18. **Item 7.3:** Avaliação de telas vazias (*Empty States*) para novos usuários cadastrados.
19. **Item 7.4:** Medição da carga cognitiva em trocas de contexto com app Gov.br no smartphone (MFA).
