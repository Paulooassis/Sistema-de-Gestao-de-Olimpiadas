# QuestionControllerImpl

Documentação da controller **QuestionControllerImpl**, descrevendo os métodos disponíveis, seus objetivos, parâmetros e tipos de retorno.

---

## Métodos

### createQuestion

Descrição:

Cria uma nova Question (pergunta).

Parâmetros:

- `QuestionRequest questionRequest` – Dados necessários para a criação da pergunta.

Retorno:

- `201 Created` – Objeto `QuestionResponse`

---

### deleteQuestion

Descrição:

Remove uma pergunta a partir do seu identificador.

Parâmetros:

- `Long id` – Identificador da pergunta.

Retorno:

- `204 No Content`

---

### getAllQuestions

Descrição:

Lista todas as perguntas cadastradas.

Parâmetros:

- Não possui.

Retorno:

- `200 OK` – Lista de `QuestionResponse`

---

### getQuestionById

Descrição:

Busca uma pergunta específica pelo seu identificador.

Parâmetros:

- `Long id` – Identificador da pergunta.

Retorno:

- `200 OK` – Objeto `QuestionResponse`

---

### updateQuestion

Descrição:

Atualiza os dados de uma pergunta existente.

Parâmetros:

- `Long id` – Identificador da pergunta.
- `QuestionRequest questionRequest` – Dados atualizados da pergunta.

Retorno:

- `200 OK` – Objeto `QuestionResponse`