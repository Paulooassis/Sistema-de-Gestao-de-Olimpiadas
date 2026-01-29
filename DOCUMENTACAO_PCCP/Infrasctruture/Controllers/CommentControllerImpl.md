# CommentControllerImpl

Documentação da controller **CommentControllerImpl**, descrevendo os métodos disponíveis, seus objetivos, parâmetros e tipos de retorno.

---

## Métodos

### createComment

**Descrição:**

Cria um novo comentário.

**Parâmetros:**

- `CommentRequest commentRequest` – Dados necessários para criação do comentário.

**Retorno:**

- `201 Created` – Objeto `CommentResponse`

---

### updateComment

**Descrição:**

Atualiza os dados de um comentário existente.

**Parâmetros:**

- `Long id` – Identificador do comentário.
- `CommentRequest commentRequest` – Dados atualizados do comentário.

**Retorno:**

- `200 OK` – Objeto `CommentResponse`

---

### deleteComment

**Descrição:**

Remove um comentário a partir do seu identificador.

**Parâmetros:**

- `Long id` – Identificador do comentário.

**Retorno:**

- `204 No Content`

---

### getAllComments

**Descrição:**

Lista todos os comentários cadastrados, permitindo filtros opcionais por produto, entregável ou unidade organizacional.

**Parâmetros:**

- `Long productId` (opcional) – Identificador do produto.
- `Long deliverableId` (opcional) – Identificador do entregável.
- `Long organizationUnitId` (opcional) – Identificador da unidade organizacional.

**Retorno:**

- `200 OK` – Lista de `CommentResponse`

---

### getCommentHistoryByOrganizationAndContext

**Descrição:**

Busca o histórico de comentários baseado em uma unidade organizacional e um contexto específico.

**Parâmetros:**

- `Long organizationUnitId` – Identificador da unidade organizacional.
- `String context` – O contexto para filtragem dos comentários.

**Retorno:**

- `200 OK` – Lista de `CommentResponse`

---

### getCommentsByQuestionId

**Descrição:**

Lista todos os comentários associados a uma pergunta específica.

**Parâmetros:**

- `Long questionId` – Identificador da pergunta.

**Retorno:**

- `200 OK` – Lista de `CommentResponse`