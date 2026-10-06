# Meu Próximo Passo — Ideias Futuras

## Objetivo

Este arquivo guarda ideias novas que vão **além do MVP**.

Regra de trabalho: toda ideia nova trazida durante a construção entra aqui primeiro. Ela só passa para o escopo quando houver uma decisão consciente, seguindo `scope.md` §7 (critério para inclusão de novas funcionalidades).

Uma ideia registrada aqui não é requisito.

---

| ID | Ideia | Origem | Depende de | Status |
| --- | --- | --- | --- | --- |
| FUT-01 | **Sugestão proativa:** se o sistema foi aberto e a conversa não foi iniciada, após ~15 min sugerir um passo com base na hora do dia e no histórico. | Autor, 05/10 | Histórico suficiente; regras de horário no Planner | Registrada |
| FUT-02 | **Lembrete por ausência:** avisar o usuário após um período sem entrar no sistema. | Autor, 05/10 | Canal de notificação (navegador, e-mail, outro) | Registrada |
| FUT-03 | **Ajuste da duração de referência:** quando o usuário faz mais que a referência (ex.: Inglês > 20 min), alterar a configuração da categoria. Sugestão: o sistema propõe e o usuário confirma. | Autor, 05/10 | Registro de duração real; regra de gatilho | Registrada |
| FUT-04 | **Importação de issues do GitHub** para categorias de projeto. | Autor, 05/10 | Integração com a API do GitHub | Registrada |
| FUT-06 | **Montar o treino no sistema**, em vez de depender do app de exercícios externo. | Autor, 06/10 | Modelagem de exercícios | Registrada |
| FUT-05 | **Adaptação ao estado do usuário** com parâmetros derivados de pesquisa científica. | Registro §18; `scope.md` §5.2 | Pesquisa a ser feita | Registrada |

---

## Notas por ideia

### FUT-01 — Sugestão proativa

* Nos primeiros dias, sem histórico, poderia usar apenas a rotina do dia.
* Sugestão: no máximo uma vez por abertura, para não virar insistência.
* Avaliar se o usuário pode desativar.

### FUT-03 — Ajuste da duração

A decidir quando entrar:

* quantas execuções acima da referência disparam a proposta;
* quanto acima (ex.: +25%);
* se o ajuste também pode ser para baixo;
* em categorias de plano, se o ajuste muda também a estrutura dos blocos do dia.