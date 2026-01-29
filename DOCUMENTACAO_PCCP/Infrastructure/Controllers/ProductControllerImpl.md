# ProductControllerImpl

Documentação da controller **ProductControllerImpl**, descrevendo os métodos disponíveis, seus objetivos, parâmetros e tipos de retorno.

---

## Métodos

### createProduct

Descrição:
Cria um novo Produto.

Parâmetros:

- `ProductRequest productRequest` – Dados necessários para criação do produto.

Retorno:

- `201 Created` – Objeto `ProductResponse`

---

### deleteProduct

Descrição:
Remove um produto a partir do seu identificador.

Parâmetros:

- `Long id` – Identificador do produto.

Retorno:

- `204 No Content`

---

### getAllProducts

Descrição:
Lista todos os produtos cadastrados.

Parâmetros:

- Não possui.

Retorno:

- `200 OK` – Lista de `ProductResponse`

---

### getProductById

Descrição:
Busca um produto específico pelo seu identificador.

Parâmetros:

- `Long id` – Identificador do produto.

Retorno:

- `200 OK` – Objeto `ProductResponse`

---

### getProductsByOrganizationUnitId

Descrição:
Lista todos os produtos associados a uma Unidade Organizacional específica.

Parâmetros:

- `Long organizationUnitId` – Identificador da Unidade Organizacional.

Retorno:

- `200 OK` – Lista de `ProductResponse`

---

### updateProduct

Descrição:
Atualiza os dados de um produto existente.

Parâmetros:

- `Long id` – Identificador do produto.
- `ProductRequest productRequest` – Dados atualizados do produto.

Retorno:

- `201 Created` – Objeto `ProductResponse`