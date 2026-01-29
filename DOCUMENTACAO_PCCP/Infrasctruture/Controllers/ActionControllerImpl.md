# ActionControllerImpl

**1. ActionControllerImpl**

Documentação da controller **ActionControllerImpl**, descrevendo os métodos disponíveis, seus objetivos, parâmetros e tipos de retorno.

## Métodos

### createAction

**Descrição:**

Cria uma nova Action.

**Parâmetros:**

- `ActionRequest actionRequest` – Dados necessários para criação da Action.

**Retorno:**

- `200 OK`

### deleteAction

**Descrição:**

Remove uma Action a partir do seu identificador.

**Parâmetros:**

- `Long id` – Identificador da Action.

**Retorno:**

- `204 No Content`

### getActionById

**Descrição:**

Busca uma Action específica pelo seu identificador.

**Parâmetros:**

- `Long id` – Identificador da Action.

**Retorno:**

- `200 OK`

### getAllActions

**Descrição:**

Lista todas as Actions, permitindo a aplicação de filtros opcionais.

**Parâmetros:**

- `Long productId` (opcional) – Identificador do produto.
- `Long organizationUnitId` (opcional) – Identificador da unidade organizacional.
- `Long deliverableId` (opcional) – Identificador do entregável.

**Retorno:**

- `200 OK` – Lista de `ActionResponse`

### getAllActionsByQuestionID

**Descrição:**

Lista todas as Actions associadas a uma Question específica.

**Parâmetros:**

- `Long id` – Identificador da Question.

**Retorno:**

- `200 OK` – Lista de `ActionResponse`

### updateAction

**Descrição:**

Atualiza os dados de uma Action existente.

**Parâmetros:**

- `Long id` – Identificador da Action.
- `ActionRequest actionRequest` – Dados atualizados da Action.

**Retorno:**

- `200 OK`