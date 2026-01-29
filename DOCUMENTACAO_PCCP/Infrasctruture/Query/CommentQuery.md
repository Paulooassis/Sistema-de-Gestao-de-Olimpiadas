# CommentQuery

A classe **CommentQuery** centraliza queries SQL relacionadas à entidade **Comment**, seguindo o padrão de queries especializadas do sistema.

## Query Disponível

- **FIND_COMMENTS_FILTRED**:
    
    Consulta responsável por buscar comentários aplicando filtros opcionais por **produto**, **unidade organizacional** e **entregável**.
    
    A query utiliza uma **CTE (Common Table Expression)**, que é uma estrutura SQL usada para criar um resultado temporário e reutilizável dentro da própria consulta. Nesse contexto, a CTE é usada para identificar, para cada **métrica**, a data do comentário mais antigo registrado.
    
    A partir desse resultado, a consulta principal retorna todos os comentários e os organiza de forma lógica, garantindo que comentários associados a métricas mais antigas apareçam primeiro. Dentro de cada métrica, os comentários são ordenados pela data de criação em ordem crescente.
    
    Os filtros são aplicados apenas quando os parâmetros correspondentes não são nulos. Caso todos os filtros sejam nulos, a consulta retorna todos os comentários, mantendo a ordenação por métrica e data de criação.