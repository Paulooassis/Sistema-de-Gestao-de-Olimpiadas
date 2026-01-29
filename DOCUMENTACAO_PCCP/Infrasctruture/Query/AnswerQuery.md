# AnswerQuery

A classe **AnswerQuery** centraliza queries SQL relacionadas à entidade **Answer**, seguindo o padrão de queries especializadas do sistema.

## Query Disponível

- **FIND_BY_ASSESSMENT_ID_WITH_OPTIONAL_FORECAST_FILTER**:
    
    Consulta responsável por buscar respostas vinculadas a um **assessment**, com a possibilidade de aplicar um filtro opcional baseado em **forecast**.
    
    O filtro é aplicado apenas quando o parâmetro **filterByForecast** é informado. Quando nulo ou igual a `0`, a consulta retorna todas as respostas do assessment. Quando igual a `1`, são retornadas apenas as respostas cujo valor numérico é menor que o valor de forecast.