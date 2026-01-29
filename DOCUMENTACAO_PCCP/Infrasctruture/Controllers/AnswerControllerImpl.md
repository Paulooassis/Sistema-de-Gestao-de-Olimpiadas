# AnswerControllerImpl

Documentação da controller **AnswerControllerImpl**, descrevendo os métodos disponíveis, seus objetivos, parâmetros e tipos de retorno.

---

## Métodos

### createAnswer

**Descrição:**

Cria uma nova Answer.

**Parâmetros:**

- `AnswerRequest answerRequest` – Dados necessários para criação da Answer.

**Retorno:**

- `200 OK`

---

### deleteAnswer

**Descrição:**

Remove uma Answer a partir do seu identificador.

**Parâmetros:**

- `Long id` – Identificador da Answer.

**Retorno:**

- `204 No Content`

---

### getAllAnswers

**Descrição:**

Lista todas as Answers cadastradas.

**Parâmetros:**

- Não possui.

**Retorno:**

- `200 OK` – Lista de `AnswerResponse`

---

### getAnswerById

**Descrição:**

Busca uma Answer específica pelo seu identificador.

**Parâmetros:**

- `Long id` – Identificador da Answer.

**Retorno:**

- `200 OK`

---

### getAnswersByAssessmentId

**Descrição:**

Lista todas as Answers associadas a um Assessment(avaliação) específico.

**Parâmetros:**

- `Long assessmentId` – Identificador do Assessment.

**Retorno:**

- `200 OK` – Lista de `AnswerResponse`

---

### updateAnswer

**Descrição:**

Atualiza os dados de uma Answer existente.

**Parâmetros:**

- `Long id` – Identificador da Answer.
- `AnswerRequest answerRequest` – Dados atualizados da Answer.

**Retorno:**

- `200 OK`

---

### getFilteredQuestionsByAssessmentId

**Descrição:**

Retorna as Questions agrupadas por avaliação, aplicando filtro opcional por forecast.

**Parâmetros:**

- `Long assessmentId` – Identificador do Assessment.
- `Boolean filterByForecast` (opcional) – Indica se deve filtrar por forecast.

**Retorno:**

- `200 OK` – Lista de `QuestionSegmentResponse`