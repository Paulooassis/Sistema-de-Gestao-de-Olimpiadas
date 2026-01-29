# OrganizationType

Representa o **tipo de unidade organizacional**, atuando como um catálogo de classificação para as **OrganizationUnit** existentes no sistema.

O **OrganizationType** define como uma unidade organizacional é categorizada, influenciando a forma como o PCCP interpreta e organiza sua estrutura.

### Propósito

- **Padronização**: Garante que as unidades organizacionais sejam classificadas de forma consistente (ex: *Squad*, *Tribo*, *Cliente*).
- **Flexibilidade**: Permite que o sistema trate diferentes tipos de unidades organizacionais de maneira apropriada, podendo influenciar regras de negócio, aplicação de perguntas e cálculos de maturidade.

### Atributos principais

- **id**: Identificador único do tipo de unidade organizacional.
- **name**: Nome do tipo de unidade organizacional.
- **createdAt**: Data e hora de criação do registro.

O **OrganizationType** é utilizado como referência pelas **OrganizationUnit**, permitindo a categorização das unidades e garantindo consistência na organização hierárquica e no contexto das avaliações do PCCP.