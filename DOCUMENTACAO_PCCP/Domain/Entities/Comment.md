# Comment

Representa um **comentário** associado a uma métrica (Question), utilizado para registrar observações e histórico nos contextos de **Operações**, **Produto** ou **Engenharia**.

### Atributos principais

- **id**: Identificador único do comentário.
- **description**: Texto do comentário.
- **createdAt**: Data e hora de criação do comentário (gerada automaticamente).
- **question**: Métrica associada ao comentário (armazena apenas o *id*).

### Contexto do comentário

O comentário pode estar vinculado a **somente um** dos contextos abaixo. Os relacionamentos utilizam carregamento **LAZY**, armazenando apenas o *id* da entidade relacionada:

- **organizationUnit**: Comentários do contexto de **Operações**. Será `null` para Produto ou Engenharia.
- **product**: Comentários do contexto de **Produto**. Será `null` para Operações ou Engenharia.
- **deliverable**: Comentários do contexto de **Engenharia**. Será `null` para Operações ou Produto.