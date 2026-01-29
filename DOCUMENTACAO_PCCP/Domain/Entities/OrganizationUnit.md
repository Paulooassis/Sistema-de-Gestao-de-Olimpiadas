# OrganizationUnit

Representa uma **unidade organizacional** dentro da estrutura avaliada ou gerenciada pelo PCCP, como uma **Tribo**, **Squad** ou outro agrupamento equivalente.

A **OrganizationUnit** é uma das entidades centrais do sistema, servindo como o principal elo entre avaliações, produtos e regras de maturidade.

### Propósito

- **Gestão centralizada**: Centraliza o cadastro e o gerenciamento das unidades organizacionais que participam do PCCP.
- **Estrutura hierárquica**: Permite modelar a hierarquia organizacional por meio de relações pai-filho (ex: Tribo > Squad).
- **Contexto de avaliação**: Define a unidade à qual um assessment se refere, servindo como base para associações com produtos, entregáveis e conjuntos de perguntas.
- **Nível de maturidade**: Armazena o nível de maturidade da unidade, utilizado para determinar a relevância das perguntas e a aplicação das regras de cálculo.

### Atributos principais

- **id**: Identificador único da unidade organizacional.
- **name**: Nome da unidade organizacional.
- **level**: Nível de maturidade da unidade.
- **type**: Tipo da unidade organizacional (ex: Squad, Tribo).
- **parent**: Unidade organizacional pai na hierarquia.
- **subOrganizationUnit**: Lista de unidades organizacionais filhas.
- **active**: Indica se a unidade organizacional está ativa.
- **createdAt**: Data e hora de criação do registro.

### Relacionamentos

O relacionamento utiliza carregamento **EAGER** e armazena o *id* da entidade e retorna a *enitdade* associada:

- **parent, subOeganizationUnit**: Chave estrangeira que o vincula à unidade organizacional (squad/tribo) responsável por ele.
- **type**: Chave estrangeira que vincula ao tipo da organização.

A **OrganizationUnit** é utilizada como referência estrutural pelos serviços do PCCP, influenciando diretamente a seleção de perguntas, o agrupamento de resultados e os cálculos de maturidade.