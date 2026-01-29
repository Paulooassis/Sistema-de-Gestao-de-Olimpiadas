# Infrastructure

**Propósito:**
Contém os detalhes de implementação e a integração com tecnologias externas, como banco de dados, frameworks e APIs.

**Conteúdo:**

[Controllers](./Controllers/Controllers.md)

[Query](./Query/Query.md)

- **/mapper**: Conversores de objetos, utilizando **MapStruct**, para transformar entidades em DTOs e vice-versa. **Como por exemplo:**

```java
@Named("requestToEntity")
@Mapping(target = "id", ignore = true)
@Mapping(target = "createdAt", ignore = true)
@Mapping(target = "organizationUnit.id", source = "organizationUnitId")
@Mapping(target = "product.id", source = "productId")
@Mapping(target = "deliverable.id", source = "deliverableId")
@Mapping(target = "question.id", source = "questionId")
Action requestToEntity(ActionRequest request);

@Named("entityToResponse")
@Mapping(target = "organizationUnitId", source = "organizationUnit.id")
@Mapping(target = "productId", source = "product.id")
@Mapping(target = "deliverableId", ignore = true)
@Mapping(target = "questionId", source = "question.id")
ActionResponse entityToResponse(Action entity);

@IterableMapping(qualifiedByName = "entityToResponse")List<ActionResponse> entityToResponseList(List<Action> entities);
```

- **/repository**: Implementações das interfaces de repositório(**as escritas na camada application/repository**, contendo a lógica específica de acesso ao banco de dados (SQL Server).
- **/exceptionhandler**: Camada responsável por capturar e tratar exceções, retornando respostas HTTP padronizadas.
- **/provider**: define os contratos de integração da aplicação com recursos externos, como banco de dados ou serviços. Ela contém abstrações que permitem que a camada de aplicação dependa de interfaces, e não de implementações concretas.