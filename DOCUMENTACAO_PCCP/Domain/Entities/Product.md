# Product

Representa um **produto** de uma organização, centralizando informações de negócio, time e desenvolvimento.

### Propósito

- É a principal entidade avaliada na frente "Produto Certo" (PC), que foca em produto e design.

### Atributos principais

- **id**: Identificador único do produto.
- **name**: Nome do produto.
- **solution**: Solução sobre o produto.
- **active**: Define se o produto está ativo no sistema.
- **productOwner**: Nome do Product Owner responsável.
- **designer**: Nome do designer associado ao produto.
- **numberOfDevs**: Quantidade de desenvolvedores no time.
- **teamProducts**: Nome dos produtos do time.
- **contract**: Modelo de contrato utilizado.
- **framework**: Framework principal adotado no desenvolvimento.
- **tool**: Ferramenta de gestão utilizada.
- **createdAt**: Data de criação do registro.

### Relacionamentos

O relacionamento utiliza carregamento **LAZY** e armazena apenas o *id* da entidade associada:

- **organizationUnit**: Chave estrangeira que o vincula à unidade organizacional (squad/tribo) responsável por ele.