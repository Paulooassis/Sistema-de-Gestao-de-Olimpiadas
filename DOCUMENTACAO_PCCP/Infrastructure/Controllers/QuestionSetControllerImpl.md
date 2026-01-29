# QuestionSetControllerImpl

Documentação da controller **QuestionSetControllerImpl**, descrevendo os métodos disponíveis, seus objetivos, parâmetros e tipos de retorno.

---

## Métodos

### createQuestionSet

Descrição:
Cria um novo QuestionSet (conjunto de perguntas).

Parâmetros:

- `QuestionSetRequest questionSetRequest` – Dados necessários para criação do conjunto de perguntas.

Retorno:

- `201 Created` – Objeto `QuestionSetResponse`

---

### deleteQuestionSet

Descrição:
Remove um conjunto de perguntas a partir do seu identificador.

Parâmetros:

- `Long id` – Identificador do QuestionSet.

Retorno:

- `204 No Content`

---

### getAllQuestionSet

Descrição:
Lista todos os conjuntos de perguntas cadastrados.

Parâmetros:

- Não possui.

Retorno:

- `200 OK` – Lista de `QuestionSetResponse`

---

### getQuestionByQuestionSetId

Descrição:Descrição: Recupera todas as perguntas associadas a um conjunto (QuestionSet), realizando a resolução completa dos dados de cada pergunta e seu respectivo segment(tema das avaliações), retornando-as agrupadas.

Parâmetros:

- `Long questionSetId` – Identificador do QuestionSet.

Retorno:

- `200 OK` – Lista de `QuestionSegmentResponse`