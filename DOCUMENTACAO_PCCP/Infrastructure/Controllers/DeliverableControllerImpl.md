# DeliverableControllerImpl

Documentação da controller **DeliverableControllerImpl**, descrevendo os métodos disponíveis, seus objetivos, parâmetros e tipos de retorno.

---

## Métodos

### createDeliverable

**Descrição:**

Cria um novo Deliverable (entregável).

**Parâmetros:**

- `DeliverableRequest deliverableRequest` – Dados necessários para a criação do entregável.

**Retorno:**

- `201 Created` – Objeto `DeliverableResponse`

---

### deleteDeliverable

**Descrição:**

Remove um entregável a partir do seu identificador.

**Parâmetros:**

- `Long id` – Identificador do entregável.

**Retorno:**

- `204 No Content`

---

### getAllDeliverables

**Descrição:**

Lista todos os entregáveis cadastrados.

**Parâmetros:**

- Não possui.

**Retorno:**

- `200 OK` – Lista de `DeliverableResponse`

---

### getDeliverableById

**Descrição:**

Busca um entregável específico pelo seu identificador.

**Parâmetros:**

- `Long id` – Identificador do entregável.

**Retorno:**

- `200 OK` – Objeto `DeliverableResponse`

---

### getProductDeliverablesByOrganizationUnitId

**Descrição:**

Busca os entregáveis e seus respectivos produtos associados a uma Unidade Organizacional.

**Parâmetros:**

- `Long organizationUnitId` – Identificador da Unidade Organizacional.

**Retorno:**

- `200 OK` – Lista de `ProductDeliverableResponse`

---

### updateDeliverable

**Descrição:**

Atualiza os dados de um entregável existente.

**Parâmetros:**

- `Long id` – Identificador do entregável.
- `DeliverableRequest deliverableRequest` – Dados atualizados do entregável.

**Retorno:**

- `201 Created` – Objeto `DeliverableResponse`