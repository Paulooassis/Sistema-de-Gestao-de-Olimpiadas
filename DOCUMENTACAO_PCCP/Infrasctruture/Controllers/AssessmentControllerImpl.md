# AssessmentControllerImpl

Documentação da controller **AssessmentControllerImpl**, descrevendo os métodos disponíveis, seus objetivos, parâmetros e tipos de retorno.

---

## Métodos

### createAssessment

**Descrição:**

Cria um novo Assessment.

**Parâmetros:**

- `AssessmentRequest assessmentRequest` – Dados necessários para criação do Assessment.

**Retorno:**

- `201 Created` – Objeto `AssessmentResponse`

---

### deleteAssessment

**Descrição:**

Remove um Assessment a partir do seu identificador.

**Parâmetros:**

- `Long id` – Identificador do Assessment.

**Retorno:**

- `204 No Content`

---

### getAllAssessments

**Descrição:**

Lista todos os Assessments cadastrados.

**Parâmetros:**

- Não possui.

**Retorno:**

- `200 OK` – Lista de `AssessmentResponse`

---

### getAssessmentById

**Descrição:**

Busca um Assessment específico pelo seu identificador.

**Parâmetros:**

- `Long id` – Identificador do Assessment.

**Retorno:**

- `200 OK` – Objeto `AssessmentResponse`

---

### updateAssessment

**Descrição:**

Atualiza os dados de um Assessment existente.

**Parâmetros:**

- `Long id` – Identificador do Assessment.
- `AssessmentRequest assessmentRequest` – Dados atualizados do Assessment.

**Retorno:**

- `201 Created` – Objeto `AssessmentResponse`

---

### getAssessmentsByOrganizationUnitId

**Descrição:**

Lista todos os Assessments associados a uma Unidade Organizacional específica.

**Parâmetros:**

- `Long organizationUnitId` – Identificador da Unidade Organizacional.

**Retorno:**

- `200 OK` – Lista de `AssessmentResponse`

---

### getLastAssessmentByOrganizationUnitId

**Descrição:**

Busca o último Assessment realizado por uma Unidade Organizacional, filtrado pelo tipo de avaliação.

**Parâmetros:**

- `Long organizationUnitId` – Identificador da Unidade Organizacional.
- `String assessmentType` – Tipo do Assessment para o filtro.

**Retorno:**

- `200 OK` – Objeto `AssessmentResponse`

---

### getAssessmentPercentage

**Descrição:**

Calcula o percentual da nota e do forecast de um Assessment específico.

**Parâmetros:**

- `Long id` – Identificador do Assessment.

**Retorno:**

- `200 OK` – Objeto `PercentageResponse` - com a nota e o forecast.