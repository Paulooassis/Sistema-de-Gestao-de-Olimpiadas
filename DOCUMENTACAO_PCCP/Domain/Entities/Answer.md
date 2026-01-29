# Answer

Representa uma **resposta individual** a uma pergunta dentro de uma avaliação específica (**Assessment**), incluindo tanto o valor atual quanto o **forecast** (previsão futura).

A entidade **Answer** é a principal fonte de dados para os cálculos de maturidade realizados pelo sistema.

### Propósito

- **Registro das respostas**: Armazena as respostas fornecidas para cada pergunta em uma avaliação.
- **Acompanhamento de evolução**: Permite registrar previsões futuras, viabilizando análises de progresso.
- **Base para cálculos**: Fornece os dados necessários para o cálculo dos indicadores de PC e CP.

### Atributos principais

- **id**: Identificador único da resposta.
- **valueText**: Resposta em formato textual.
- **valueNumeric**: Resposta em formato numérico (ex: níveis de maturidade).
- **valueBoolean**: Resposta em formato booleano (ex: Sim / Não).
- **forecastText**: Texto descritivo da previsão futura.
- **forecastNumeric**: Valor numérico da previsão futura.
- **forecastBoolean**: Valor booleano da previsão futura.
- **assessment**: Avaliação à qual a resposta pertence (armazena apenas o *id*).
- **question**: Pergunta respondida (armazena apenas o *id*).
- **organizationUnit**: Unidade organizacional associada à resposta (armazena apenas o *id*).
- **product**: Produto associado, quando aplicável (armazena apenas o *id*).
- **deliverable**: Entregável associado, quando aplicável (armazena apenas o *id*).
- **createdAt**: Data e hora de criação da resposta.

As respostas podem variar conforme o tipo de avaliação (PC ou CP), sendo frequentemente **binárias no CP** e **graduais no PC**.

Os campos de **forecast** são essenciais para análises comparativas entre estado atual e evolução esperada.