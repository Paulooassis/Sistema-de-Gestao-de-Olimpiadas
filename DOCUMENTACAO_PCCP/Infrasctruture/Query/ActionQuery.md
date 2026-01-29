# ActionQuery

A classe **ActionQuery** centraliza queries SQL relacionadas à entidade **Action**, seguindo o padrão de queries especializadas do sistema.

## Query Disponível

- **FIND_ACTIONS_FILTERED**:
Consulta responsável por buscar ações aplicando filtros opcionais por **produto**, **unidade organizacional** e **entregável**.
    
    Os filtros são aplicados apenas quando os parâmetros correspondentes não são nulos, permitindo uma busca flexível e personalizada. O resultado é ordenado pela data de criação de forma decrescente. Caso os 3 valores sejam nulos, ela retorna todas as ações em ordem de data de criação de forma decrescente.