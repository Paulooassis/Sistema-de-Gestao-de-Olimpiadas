# Domain

**Propósito:**
Contém o núcleo da aplicação e a lógica de negócio mais pura. É a camada mais interna da arquitetura e **não depende de frameworks ou detalhes de infraestrutura**.

**Conteúdo:**

- **/entity**: Classes que representam as entidades do domínio e refletem as tabelas do banco de dados (ex: `Assessment`, `Question`, `OrganizationUnit`).
- **/enums**: Enumeradores que definem valores constantes e permitidos no domínio (ex: `AssessmentStatus`, `QuestionTargetType`).

[Enums](Enums%20c176d846211a4b68829b337a967a6274.md)

[Entities](Entities%2065c5efa621334690af098c4fc1ba4701.md)