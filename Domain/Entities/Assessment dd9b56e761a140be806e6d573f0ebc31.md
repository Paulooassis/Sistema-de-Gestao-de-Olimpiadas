# Assessment

Representa uma **sessão de avaliação** realizada para uma unidade organizacional (squad ou tribo) em um período específico, utilizando um **conjunto de perguntas (QuestionSet)** previamente definido.

O **Assessment** é o ponto central do processo de avaliação de maturidade no PCCP, servindo como base para o registro das respostas e para o cálculo dos indicadores de PC e CP.

### Propósito

- **Registro e agendamento**: Representa cada avaliação ou acompanhamento periódico da maturidade.
- **Histórico de avaliações**: Permite acompanhar a evolução ou regressão da maturidade ao longo do tempo.
- **Contextualização da avaliação**: Armazena informações como período, tipo de avaliação e participantes externos.

### Atributos principais

- **id**: Identificador único da avaliação.
- **year**: Ano em que a avaliação foi realizada.
- **month**: Mês em que a avaliação foi realizada.
- **type**: Tipo da avaliação (ex: PC ou CP).
- **status**: Status da avaliação (ex: `DRAFT` ou `COMPLETED`).
- **outsider**: Nome ou identificador de um participante externo (sabatinador).
- **organizationUnit**: Unidade organizacional avaliada (armazena apenas o *id*).
- **questionSet**: Conjunto de perguntas utilizado na avaliação (armazena apenas o *id*).
- **createdAt**: Data e hora de criação da avaliação.
- **completedAt**: Data e hora de finalização da avaliação.

O **Assessment** é utilizado como referência principal pelos serviços de cálculo de maturidade, que buscam suas respostas associadas para gerar os indicadores do PCCP.