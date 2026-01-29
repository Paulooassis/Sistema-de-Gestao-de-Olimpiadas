# QuestionSetItemControllerImpl

Documentação da controller **QuestionSetItemControllerImpl**, descrevendo os métodos disponíveis, seus objetivos, parâmetros e tipos de retorno.

---

## Métodos

### createQuestionSetItem

Descrição:

Cria um novo item de conjunto de perguntas (QuestionSetItem), estabelecendo o vínculo entre uma Question e um QuestionSet.

Parâmetros:

- `QuestionSetItemRequest questionSetItemRequest` – Dados necessários para a criação do vínculo.

Retorno:

- `201 Created` – Objeto `QuestionSetItemResponse`

---

### deleteQuestionSetItem

Descrição:

Remove um item de conjunto de perguntas a partir do seu identificador.

Parâmetros:

- `Long id` – Identificador do QuestionSetItem.

Retorno:

- `204 No Content`

---

### getAllQuestionSetItem

Descrição:

Lista todos os itens de conjuntos de perguntas cadastrados no sistema.

Parâmetros:

- Não possui.

Retorno:

- `200 OK` – Lista de `QuestionSetItemResponse`

---

### getQuestionSetItemsByQuestionSetId

Descrição:

Lista todos os itens vinculados a um QuestionSet (conjunto de perguntas) específico.

Parâmetros:

- `Long questionSetId` – Identificador do QuestionSet.

Retorno:

- `200 OK` – Lista de `QuestionSetItemResponse`