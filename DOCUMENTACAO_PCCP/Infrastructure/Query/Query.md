# Query

Este módulo do sistema é responsável por centralizar **queries especializadas**, utilizadas para realizar buscas mais aprofundadas e personalizadas no banco de dados.

## Objetivo

A pasta **Query** tem como principal objetivo **desacoplar a lógica de consulta** das classes de repositório, promovendo um código mais:

- ✅ Organizado
- ✅ Manutenível
- ✅ Reutilizável
- ✅ Fácil de evoluir

## Estrutura e Convenções

- As classes presentes nesta pasta **não representam entidades** do domínio.
- Cada classe possui **apenas métodos estáticos**.
- Cada método estático representa **uma query específica**, claramente nomeada de acordo com sua responsabilidade.

```java
public final class ExampleQuery {

    public static String findByActiveStatus() {
        return "SELECT e FROM Entity e WHERE e.active = true";
    }
}

```

## Uso nas Repositories

As queries definidas nesse módulo são utilizadas como **valor** nas anotações ou métodos das repositories, por exemplo:

```java
@Query(value = ExampleQuery.findByActiveStatus(), nativeQuery = true)
List<Entity> findActiveEntities();

```

Dessa forma:

- A repository fica responsável apenas pelo **contrato de acesso aos dados**.
- A definição da query fica isolada, facilitando manutenção e reutilização.

## Benefícios

- 🔹 Redução de duplicação de código
- 🔹 Padronização das consultas
- 🔹 Facilidade para refatorar ou otimizar queries
- 🔹 Melhor leitura e entendimento das repositories

[ActionQuery](./ActionQuery.md)

[AnswerQuery](./AnswerQuery.md)

[CommentQuery](./CommentQuery.md)

[OrganizationUnitQuery](./OrganizationUnitQuery.md)