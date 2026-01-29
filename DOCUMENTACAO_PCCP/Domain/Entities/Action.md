# Action

Representa uma **ação planejada** por uma organização sobre uma determinada métrica (Question), podendo pertencer a **apenas um contexto por vez**: Operações, Produto ou Engenharia.

### Atributos principais

- **id**: Identificador único da ação.
- **name**: Nome da ação.
- **question**: Referência à métrica associada (armazena apenas o *id*).
- **responsibleName**: Nome do responsável pela execução da ação.
- **description**: Descrição do que a ação irá realizar.
- **status**: Estado da ação (ex: pendente ou concluída).
- **expectedDate**: Data prevista para conclusão.
- **concludedDate**: Data efetiva de conclusão.

### Contexto da ação

A ação pode estar vinculada a **somente um** dos contextos abaixo. Os relacionamentos armazenam apenas o *id* da entidade associada, utilizando carregamento **LAZY**:

- **organizationUnit**: Utilizado quando a ação pertence ao contexto de **Operações**. Será `null` para Produto ou Engenharia.
- **product**: Utilizado quando a ação pertence ao contexto de **Produto**. Será `null` para Operações ou Engenharia.
- **deliverable**: Utilizado quando a ação pertence ao contexto de **Engenharia**. Será `null` para Operações ou Produto.
