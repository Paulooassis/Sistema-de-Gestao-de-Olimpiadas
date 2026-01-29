# Segment

Representa um **tema de avaliação**, utilizado para agrupar um conjunto de **Questions** relacionadas a um mesmo assunto dentro do sistema.

### Propósito

- **Agrupamento de perguntas**: Organiza as questions por tema ou área de análise (ex: Segurança, Monitoramento, Infraestrutura).
- **Cálculos específicos**: Permite a realização de cálculos de maturidade considerando apenas perguntas de um determinado segmento.
- **Perguntas dinâmicas**: Possibilita a exibição de questions de acordo com os segmentos relevantes ao contexto da avaliação.

### Atributos principais

- **id**: Identificador único do segmento.
- **name**: Nome do tema que agrupa um conjunto de questions.
- **createdAt**: Data de criação do registro

O **Segment** é utilizado como critério de filtragem e agrupamento tanto na interface de preenchimento quanto nos serviços de cálculo de maturidade do PCCP.