# Question

A pasta **Question** concentra as entidades responsáveis por definir as **métricas avaliativas do sistema**, sua organização em conjuntos e o relacionamento entre esses elementos.

Ela permite estruturar perguntas, agrupá-las por tema e controlar quais métricas estão ativas em cada contexto.

## Question

Representa uma **métrica avaliativa**, utilizada para medir maturidade, práticas ou processos dentro de um determinado tema (**Segment**).

Cada question descreve cenários ideais e não ideais, além de definir seu tipo de resposta e público-alvo.

### Atributos principais

- **id**: Identificador único da question.
- **name**: Título da métrica.
- **description**: Descrição detalhada do que está sendo avaliado.
- **bestScenario**: Descrição do cenário ideal esperado.
- **worstScenario**: Descrição do pior cenário possível.
- **level**: Nível de maturidade associado à question.
- **segment**: Tema ao qual a question pertence.
- **categoryType**: Categoria da question (PRODUCT, OPERATIONS, ENGINEERING, TEAM).
- **targetType**: Contexto alvo da avaliação (SQUAD, DELIVERABLE, PRODUCT).
- **responseType**: Tipo de resposta esperada (NUMERIC, TEXT, BOOLEAN).
- **criticality**: Indica se a question é crítica (TRUE, FALSE).
- **active**: Indica se a question está ativa no sistema.
- **createdAt**: Data de criação do registro.

---

## QuestionSet

Representa um **conjunto de perguntas** utilizado como base para a aplicação das **avaliações de maturidade** no App PCCP.

O **QuestionSet** atua como um contêiner lógico que agrupa questions relacionadas, permitindo que avaliações sejam realizadas de forma consistente, direcionada e reutilizável entre diferentes contextos e unidades organizacionais.

### Propósito

- **Agrupar questões** tematicamente relacionadas ou voltadas a um tipo específico de avaliação (ex: Produto, Engenharia).
- **Facilitar a criação de assessments**, permitindo selecionar rapidamente o conjunto de perguntas a ser aplicado.
- **Padronizar avaliações**, garantindo consistência nos critérios de análise de maturidade.

### Funcionamento no fluxo do sistema

- As **questions** são cadastradas individualmente no sistema.
- Em seguida, são criados os **question_sets**, que agrupam essas questions por meio da entidade **QuestionSetItem**.
- Cada **question_set** pode ser vinculado a uma **organizationUnit**, possibilitando avaliações adaptadas à realidade de diferentes squads, tribos ou áreas.
- Os **question_sets** são utilizados como base para iniciar **sessões de avaliação (assessments)**.

### Atributos principais

- **id**: Identificador único do conjunto.
- **name**: Nome do conjunto de perguntas (ex: *PC - Produto e Design*, *CP - Engenharia*).
- **type**: Tipo do conjunto de perguntas.
- **organization_unit_id**: Chave estrangeira que vincula o question_set a uma unidade organizacional (organization_[unit.id](http://unit.id)).
- **active**: Indica se o conjunto está ativo no sistema.
- **createdAt**: Data de criação do registro.

---

## QuestionSetItem

Representa um **item de um conjunto de perguntas**, sendo responsável por **vincular uma question a um question_set**.

O **QuestionSetItem** permite controlar quais perguntas fazem parte de um determinado conjunto e se elas estão **ativas ou desativadas** naquele contexto específico, sem afetar a pergunta em outros conjuntos.

### Propósito

- **Vincular perguntas a conjuntos**: Define quais questions compõem um question_set.
- **Gerenciar ativação por contexto**: Permite desabilitar uma pergunta dentro de um conjunto específico, mantendo-a disponível em outros question_sets.

Essa abordagem oferece flexibilidade para adaptar avaliações conforme o perfil de squads, produtos ou unidades organizacionais, sem necessidade de duplicar ou remover perguntas.

### Atributos principais

- **id**: Identificador único do item.
- **question**: Referência à pergunta associada (armazena apenas o *id*).
- **questionSet**: Referência ao conjunto de perguntas ao qual o item pertence (armazena apenas o *id*).
- **disabled**: Indica se a pergunta está desabilitada (`true`) ou habilitada (`false`) dentro daquele question_set.