# Meu Próximo Passo — Categorias

## 1. Objetivo deste documento

Este documento define o que é uma categoria, quais são as categorias do MVP, como cada uma participa da rotina e de onde vêm suas tarefas.

Termos seguem `product/glossary.md`. Itens marcados como **(proposta)** precisam de confirmação do autor.

---

## 2. O que é uma categoria

Uma categoria é uma área de desenvolvimento que participa da rotina do usuário.

Ela carrega as informações que permitem ao sistema saber:

* **quando** ela deve participar da rotina;
* **o que** ela possui disponível para execução;
* **por quanto tempo** uma execução costuma durar.

---

## 3. Categorias definidas

| Categoria | Ícone | Fonte de tarefas | Frequência | Duração |
| --- | --- | --- | --- | --- |
| Programação | 💻 | Backlog de projetos (issues) | Contínua | Até concluir a tarefa |
| Inglês | 🇺🇸 | Plano semanal | Todos os dias | 20 min |
| LinkedIn | 💼 | Plano semanal | Segunda a sábado | Por etapa (ver §5.3) |
| Treino (Calistenia) | 💪 | Plano diário; conteúdo em app de exercícios externo | Todos os dias | 20 a 30 min |

> **Ícone de bandeira:** no Windows, emojis de bandeira (🇺🇸) aparecem como as letras "US". Se a interface precisar exibir a bandeira em qualquer sistema, usar um ícone SVG em vez de emoji. Decisão de UI, a registrar em `ux/`.

---

## 4. Regra fundamental

> **Toda categoria ativa possui um próximo passo disponível até ser finalizada.**

Não existe categoria vazia. Uma categoria existe porque há algo a fazer nela.

```text
Categoria ativa
      +
Sem tarefa em aberto
      ↓
Estado que precisa ser resolvido
      ↓
Sistema pergunta ao usuário:
  • adicionar uma nova tarefa?
  • finalizar a categoria?
```

**(proposta)** Enquanto o usuário não resolve, a categoria não aparece na rotina do dia (mantém RF-11), mas o sistema traz a pergunta na conversa.

**Não existem tarefas avulsas.** Toda tarefa pertence à fonte de tarefas da sua categoria: o backlog ou o plano.

**Não existem dependências entre categorias.** Cada categoria sugere apenas o que ela própria faz.

---

## 5. Detalhamento por categoria

### 5.1 💻 Programação

Programação é uma **lista de projetos**. Cada projeto possui suas **issues**, e o próximo passo é a próxima issue em aberto.

```text
Programação
├── Soberana
│   ├── Issue #1  ✅ concluída
│   ├── Issue #2  ◀ próximo passo
│   └── Issue #3  aguardando a #2
├── Projeto B
│   └── Issue #1  ◀ próximo passo
└── … (6 projetos atualmente)
```

Regras decididas:

* Issues são cadastradas **na formação da categoria/projeto** e **adicionadas pela conversa** (DEC-02).
* As issues de um projeto possuem **ordem**: uma issue pode depender da anterior (DEC-03).
* Uma issue adiada continua sendo opção no dia seguinte (DEC-04).
* É desejável que todos os projetos avancem, mas o usuário contextualiza qual projeto trabalhar; o contexto vem antes da decisão do Planner (DEC-05).
* **Sem duração fixa:** a execução vai até concluir a tarefa (DEC-16).

### 5.2 🇺🇸 Inglês

Plano semanal, 20 min por dia:

| Dia | Tema | Estrutura |
| --- | --- | --- |
| Segunda | 📖 Aula KNN + vocabulário | 8 min livro + 5 min vocabulário + 7 min falando |
| Terça | 🎧 Listening | 8 min áudio/vídeo + 5 min repetir + 7 min compreender |
| Quarta | 🗣️ Speaking | 5 min revisão + 10 min falando + 5 min correção |
| Quinta | 📖 Gramática aplicada | 8 min livro + 7 min criar frases + 5 min falar |
| Sexta | 💻 English + Programming | 5 min vocabulário + 10 min explicar o código + 5 min revisão |
| Sábado | 🎧 Listening + repetição | 10 min vídeo/áudio + 10 min repetir |
| Domingo | 🔄 Revisão | 10 min revisar a semana + 5 min falar + 5 min planejar |

Regras decididas:

* **Apenas a tarefa do dia é oferecida.** A tarefa do plano não realizada não é oferecida em outro dia (DEC-10).

**(proposta)** Ao fim do dia, a tarefa do plano não realizada é registrada no histórico como **não realizada** — um fato, sem julgamento. O estado definitivo fica em `task-states.md`.

### 5.3 💼 LinkedIn

Plano semanal (DEC-14):

| Dia | Etapa | Duração |
| --- | --- | --- |
| 🟨 Segunda | 💻 Post — projeto | Até concluir · **obrigatória** |
| 🟩 Terça | 🤝 Networking | 15 min |
| 🟨 Quarta | 🧠 Post — aprendizado | Até concluir |
| 🟩 Quinta | 🤝 Networking | 15 min |
| 🟨 Sexta | 👨‍💻 Post — carreira/projeto | Até concluir |
| 🟩 Sábado | 📊 Revisar resultados | A definir |
| Domingo | — | — |

O conteúdo dos posts vem do que o autor está construindo, mas **o sistema não liga o LinkedIn às issues de Programação**. A categoria sugere apenas a etapa do dia.

Regras decididas:

* Mesma regra do Inglês: **uma etapa não feita não é sugerida no dia seguinte** (DEC-10).
* **Exceção — etapa obrigatória:** o **Post — projeto** de segunda continua sendo oferecido nos dias seguintes **até ser concluído** (DEC-17).

```text
Segunda: Post — projeto não concluído
      ↓
Terça: Networking (etapa do dia)  +  Post — projeto (obrigatória pendente)
      ↓
… até ser concluído
```

### 5.4 💪 Treino (Calistenia)

Treino diário de **20 a 30 min**. O conteúdo do treino está em um **app de exercícios externo** (DEC-15).

O sistema não conhece os exercícios. O próximo passo é a sessão do dia:

```text
💪 Treino — fazer o treino do dia no app — 20 a 30 min
```

Montar o treino dentro do sistema fica para evolução futura (FUT-06).

---

## 6. Fontes de tarefas

| | Backlog | Plano |
| --- | --- | --- |
| De onde vem a tarefa | Cadastro (formação + conversa) | Agenda, conforme o dia |
| Se não for feita hoje | Continua em aberto amanhã | Não é oferecida em outro dia, **exceto etapa obrigatória** |
| Organização interna | Projetos → issues ordenadas | Dias da semana |
| Categorias | Programação | Inglês; LinkedIn; Treino |

### Etapa obrigatória

Etapa de um plano que, se não for concluída no seu dia, continua sendo oferecida até ser concluída. No MVP, a única etapa obrigatória é o **Post — projeto** do LinkedIn.

O nome "obrigatória" descreve a regra de persistência, não uma cobrança: a etapa aparece como opção, nunca com mensagem de atraso.

---

## 7. Campos da categoria **(proposta)**

| Campo | Descrição | Exemplo |
| --- | --- | --- |
| Nome | Identificação da categoria | Inglês |
| Ícone | Representação visual | 🇺🇸 |
| Lema | Sentido da categoria para o usuário | Aumentar minhas possibilidades |
| Status | Ativa ou Finalizada | Ativa |
| Fonte de tarefas | Backlog ou Plano | Plano |
| Frequência | Regularidade na rotina | Diária |
| Plano | Agenda por dia, com marcação de etapa obrigatória (apenas fonte Plano) | Seg: Aula KNN… |
| Duração | Valor fixo, intervalo ou "até concluir" | 20 min / 20–30 min / até concluir |
| Palavras-chave | Termos que identificam a categoria na conversa | inglês, english, knn |
| Criada em / Finalizada em | Datas de ciclo de vida | — |

Campos do projeto (apenas Programação) **(proposta)**: nome, palavras-chave, status (ativo / concluído), ordem das issues.

---

## 8. Ciclo de vida

### Categoria

```text
        cadastro
           ↓
        ATIVA  ──── concluída ────→  FINALIZADA
           ↑                              │
           └──────── reativação ──────────┘
```

* Uma categoria é **finalizada por conclusão**.
* Uma categoria finalizada **nunca é apagada**. O histórico permanece.
* Ao reativar, ela precisa voltar a ter um próximo passo (regra fundamental).

### Projeto **(proposta)**

Um projeto pode ser concluído sem que Programação seja finalizada. A mesma lógica de nunca apagar e permitir reativação vale para projetos.

---

## 9. Frequência **(proposta)**

| Formato | Significado | Categoria |
| --- | --- | --- |
| Diária | Participa todos os dias | Inglês, Treino |
| Dias do plano | Participa nos dias que têm etapa no plano | LinkedIn (segunda a sábado) |
| Contínua | Participa sempre que houver tarefa em aberto | Programação |

Regras de peso entre categorias ficam em `planner-rules.md`.

---

## 10. Duração

Cada categoria possui sua própria duração (RF-31). Não existe duração global. Três formas:

* **Fixa** — Inglês, 20 min;
* **Intervalo** — Treino, 20 a 30 min;
* **Até concluir** — Programação e os posts do LinkedIn: a execução termina quando a tarefa é concluída ou o usuário registra outro resultado.

Em categorias de plano, a duração pode variar **por etapa** (LinkedIn: networking 15 min, posts até concluir).

O ajuste da duração com base no histórico fica para evolução futura (FUT-03).

---

## 11. Pendências

* **LinkedIn — Revisar resultados:** duração.
* **LinkedIn — obrigatória acumulada:** se o Post — projeto não for concluído até a segunda seguinte, a nova segunda gera um segundo post ou continua o mesmo?
* **Ordem das issues:** dependência estrita (#3 só aparece após a #2) ou apenas ordem preferencial.
* **Projeto:** confirmar campos e ciclo de vida (§7, §8).
* **Cadastro:** fluxo de formação de categoria e de projeto (tela, conversa ou ambos).
* **Finalização:** o que acontece com tarefas em aberto quando uma categoria é finalizada.