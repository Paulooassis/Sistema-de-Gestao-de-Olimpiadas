# Deliverable

Representa o contexto de **engenharia**, utilizado para organizar e contextualizar métricas, ações e comentários técnicos dentro da aplicação, tendo informações sobre os entregáveis.

### Propósito

- É a principal entidade avaliada na frente "Certo Produto" (CP) para as áreas de Engenharia, Dados e Segurança. A avaliação é feita de forma granular por entregável.
- **Criticidade**: Permite definir a criticidade de um componente, o que impacta diretamente na ponderação das perguntas críticas nos cálculos de maturidade.

### Atributos principais

- **id**: Identificador único do deliverable.
- **name**: Nome do entregável.
- **type**: Tipo do entregável.
- **criticality**: Grau de criticidade associado.
- **active**: Define se o entregável está ativo no sistema.
- **createdAt**: Data de criação do registro.

### Relacionamentos

Os relacionamentos utilizam carregamento **LAZY** e armazenam apenas o *id* da entidade associada:

- **organizationUnit**: Chave estrangeira que o vincula à unidade organizacional (squad/tribo) responsável por ele.
- **product**: Opcionalmente, pode ser vinculado a um product (produto) ao qual pertence.

Essencial para a granularidade da avaliação de CP, permitindo que diferentes componentes de um mesmo squad sejam avaliados individualmente. A criticality (criticidade) do entregável é um fator chave nas regras de negócio para os cálculos do CP