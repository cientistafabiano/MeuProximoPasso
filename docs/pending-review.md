# Meu Próximo Passo — Pendências de Revisão

## Objetivo

Este arquivo acumula **inconsistências entre documentos** e **decisões novas que afetam documentos já escritos**.

Ele não é um documento oficial. Serve como lista de trabalho para a revisão que será feita ao fechar `docs/product/`.

Cada item, ao ser resolvido, deve:

1. ser decidido com o autor;
2. ser aplicado nos documentos afetados;
3. ter seu status alterado para **Resolvido**, com a decisão tomada.

Ideias novas além do MVP não entram aqui: vão para `roadmap/future-ideas.md`.

---

## A. Inconsistências entre documentos

| ID | Documentos | Descrição | Status |
| --- | --- | --- | --- |
| INC-01 | `vision.md` §3 × Registro §1 | `vision.md` lista 🧠 Mente como quinta área; o Registro diz que Mente foi descartada como categoria de tarefas. Decidir se Mente sai da visão ou permanece como dimensão (não categoria). | Aberto |
| INC-02 | `vision.md` §8 × `requirements.md` RF-15 | `vision.md` exemplifica check-in com energia/humor/ansiedade de 0 a 10; RF-15 diz que o check-in do MVP não deve ter escalas numéricas. | Aberto |
| INC-03 | `vision.md` §7 × RF-31/RF-32 × Registro §17 | `vision.md` fixa duração inicial de 10–30 min; os demais documentos dizem que não existe duração global. | Aberto |
| INC-04 | `scope.md` §8 × estrutura de pastas | `scope.md` referencia `categories.md`, que não existia na estrutura. Atualizar a estrutura no README / `docs_` com os arquivos novos: `product/glossary.md`, `domain/categories.md`, `domain/conversation-rules.md`, `roadmap/future-ideas.md` e `pending-review.md`. | Aberto |
| INC-10 | `vision.md` §3 × `categories.md` | A visão pode descrever o LinkedIn como publicações avulsas; agora é um plano semanal. Conferir na revisão. | Aberto |
| INC-05 | `requirements.md` RF-05, Registro §2 | "Programação" usado no sentido de agenda da categoria. Proposta: usar **Plano** (ver glossário). | Aberto |
| INC-06 | Todos | "Adiada" e "postergada" usados como sinônimos. Proposta: padronizar **adiada**. | Aberto |
| INC-07 | Documentação Inicial §10 × Registro §7 | O modelo de dados inicial tem `Goal` (Objetivo); o Registro não usa Objetivo. Decidir se Objetivo existe como entidade. | Aberto |
| INC-08 | Documentação Inicial §13 × `requirements.md` | O estado `planned` aparece na Documentação Inicial, mas não nos requisitos. Resolver em `task-states.md`. | Aberto |
| INC-09 | `vision.md` §3 × `categories.md` | A visão lista 💪 Calistenia; a categoria passa a se chamar Treino (Calistenia). Alinhar nomes em todos os documentos. | Aberto |

---

## B. Decisões que exigem atualizar documentos existentes

| ID | Documentos afetados | Decisão | Status |
| --- | --- | --- | --- |
| DEC-01 | `requirements.md`, `categories.md` | Toda categoria ativa possui um próximo passo até ser finalizada por conclusão. Revisar RF-10/RF-11. | `categories.md` aplicado; requirements pendente |
| DEC-02 | `requirements.md`, `scope.md` | Tarefas de projeto são cadastradas na formação da categoria e adicionadas pela conversa. Importação do GitHub → FUT-04. | `categories.md` aplicado; requirements/scope pendentes |
| DEC-03 | `requirements.md`, `planner-rules.md` | Issues possuem ordem/dependência. | Aplicar |
| DEC-04 | `planner-rules.md` | Issue adiada é opção no dia seguinte. | Aplicar |
| DEC-05 | `planner-rules.md` | O usuário contextualiza qual projeto trabalhar; contexto vem antes do Planner. | Aplicar |
| DEC-06 | — | Sugestão proativa de 15 min. | Movido para FUT-01 |
| DEC-07 | — | Lembrete por ausência. | Movido para FUT-02 |
| DEC-08 | — | Ajuste da duração de referência. | Movido para FUT-03 |
| DEC-09 | `success-criteria.md` | Validação de 2 semanas; observações em lista e no banco; nota diária + revisões nos dias 7 e 14. | Resolvido |
| DEC-10 | `requirements.md`, `planner-rules.md`, `task-states.md` | Categoria de plano oferece apenas a tarefa do dia. | `categories.md` aplicado; demais pendentes |
| DEC-11 | — | ~~Tarefa avulsa possui um dia na categoria de plano.~~ Revogada: não existem tarefas avulsas. | Revogada |
| DEC-12 | — | ~~Cada projeto é uma categoria.~~ Revogada (interpretação equivocada): Programação é uma categoria com uma lista de projetos e suas issues. | Revogada |
| DEC-13 | `success-criteria.md`, glossário, `ux/chat-flow.md` | Próximo passo já adiado ou rejeitado exibe uma tag de origem. Substitui a proposta original do CS-15. | Resolvido (CS-15 reescrito) |
| DEC-14 | `requirements.md`, `planner-rules.md` | LinkedIn é um plano semanal (seg a sáb): posts de projeto, aprendizado e carreira; networking 15 min; revisão de resultados. Sem ligação com as issues de Programação no sistema. | `categories.md` aplicado |
| DEC-17 | `requirements.md`, `planner-rules.md`, `task-states.md` | Etapa obrigatória: Post — projeto (LinkedIn, segunda) continua sendo oferecido até ser concluído. Demais etapas de plano seguem a regra do Inglês. | `categories.md` aplicado |
| DEC-15 | `requirements.md`, `vision.md` | Treino (Calistenia): todos os dias, 20 a 30 min, conteúdo em app de exercícios externo. | `categories.md` aplicado |
| DEC-16 | `requirements.md` RF-31/32, `task-states.md` | Programação e os posts do LinkedIn não têm duração fixa: a execução vai até concluir a tarefa. | `categories.md` aplicado |

---

## C. Em discussão

| ID | Documento | Questão | Status |
| --- | --- | --- | --- |
| DIS-01 | `success-criteria.md` CS-15 | Manter ou remover "sugestões explicáveis". | Resolvido por DEC-13 |
| DIS-02 | `success-criteria.md` §6 | Frequência de revisão. | Resolvido por DEC-09 |
| DIS-03 | `data-model.md` | Observações de validação persistidas no banco implicam uma entidade própria (ex.: `ValidationNote`). | Avaliar no modelo de dados |
| DIS-04 | `categories.md` | Proposta de Grupo. | Descartada com a revogação da DEC-12 |
| DIS-05 | `ux/` | Emoji de bandeira 🇺🇸 aparece como "US" no Windows; avaliar ícone SVG. | Avaliar na UI |