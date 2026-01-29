# Entities

As **Entities** representam as tabelas do banco de dados e são responsáveis por definir a estrutura de persistência do sistema.

Elas modelam os dados conforme o domínio da aplicação e fazem o mapeamento objeto-relacional (ORM), permitindo que as informações sejam armazenadas e recuperadas do banco de forma transparente.

### Principais responsabilidades

- Definir **chaves primárias**, incluindo a estratégia de geração de valores (por exemplo: `AUTO`, `IDENTITY`, `SEQUENCE`).
- Declarar **relacionamentos entre entidades** (1:1, 1:N, N:N), especificando suas regras de navegação e integridade.
- Configurar **restrições de campos**, como `nullable`, tamanho máximo (`length`), unicidade (`unique`) e obrigatoriedade.
- Determinar o **tipo de carregamento (fetch)** dos relacionamentos:
    - **LAZY**: carrega apenas os identificadores das entidades relacionadas, buscando os dados completos sob demanda.
    - **EAGER / FETCH**: carrega automaticamente a entidade relacionada junto com a entidade principal.

Essas definições garantem consistência, integridade dos dados e melhor controle sobre desempenho e comportamento das consultas ao banco.

---

[Action](./Action.md)

[Answer](./Answer.md)

[Assessment](./Assessment.md)

[Comment](./Comment.md)

[Deliverable](./Deliverable.md)

[Product](./Product.md)

[Segment](./Segment.md)

[Question](./Question.md)

[OrganizationUnit](./OrganizationUnit.md)

[OrganizationType](./OrganizationType.md)