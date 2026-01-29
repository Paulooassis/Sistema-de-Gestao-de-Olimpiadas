# OrganizationUnitQuery

A classe **OrganizationUnitQuery** centraliza queries SQL relacionadas à entidade **OrganizationUnit**, seguindo o padrão de queries especializadas do sistema.

## Query Disponível

- **FIND_BY_PARENT_ID**:
    
    Consulta responsável por buscar todas as unidades organizacionais que possuem um **parent_id** específico. É utilizada para recuperar os filhos diretos de uma unidade na hierarquia.
    
- **FIND_HIERARCHY_BY_ID**:
    
    Consulta responsável por buscar toda a **hierarquia de unidades organizacionais** a partir de uma unidade raiz informada.
    
    A query utiliza uma **CTE (Common Table Expression)** recursiva para montar a hierarquia. Inicialmente, a CTE seleciona a unidade informada e, em seguida, percorre recursivamente seus filhos, retornando todos os níveis abaixo dela.
    
    O resultado final representa a árvore hierárquica completa da unidade organizacional, mantendo todas as informações relevantes de cada nível.
    
- **FIND_TOP_HIERARCHY**:
    
    Consulta responsável por buscar todas as unidades organizacionais que estão no **topo da hierarquia**, ou seja, aquelas que não possuem unidade pai (`parent_id IS NULL`).
    
- **FIND_SQUADS_AND_TRIBES_WITHOUT_CHILDREN**:
    
    Consulta responsável por buscar unidades organizacionais ativas do tipo **SQUAD** ou **TRIBE** que **não possuem unidades filhas**.
    
    A query garante que apenas unidades finais da hierarquia sejam retornadas, ordenando o resultado pelo tipo de organização e pelo nome da unidade.