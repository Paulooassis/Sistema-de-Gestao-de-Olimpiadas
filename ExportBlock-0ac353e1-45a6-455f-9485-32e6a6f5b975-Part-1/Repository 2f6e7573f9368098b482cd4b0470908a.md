# Repository

Este módulo contém diversas **interfaces de repositórios** responsáveis por abstrair operações de persistência e consulta de entidades do domínio.

Todas seguem o padrão de **CRUD (Create, Read, Update, Delete)**, além de métodos específicos para consultas personalizadas.

---

## 🔹 ActionRepository

Gerencia a entidade **Action**.

- `save`, `updateById`, `deleteById`, `findById` → operações básicas.
- Consultas específicas:
    - `findByContext(productId, orgUnitId, deliverableId)` → busca ações por contexto.
    - `findByQuestionId(questionId)` → busca ações relacionadas a uma questão.

---

## 🔹 AnswerRepository

Gerencia a entidade **Answer**.

- CRUD completo.
- Consultas específicas:
    - `findByAssessmentId` → respostas de um assessment.
    - `findByAssessmentAndQuestionIn` → respostas filtradas por questões e avaliação.
    - `findByAssessmentIdWithOptionalForecastFilter` → respostas com filtro opcional de previsão e por avaliação.

---

## 🔹 AssessmentRepository

Gerencia a entidade **Assessment**.

- CRUD completo.
- Consultas específicas:
    - `existsByOrganizationUnitIdAndYearAndMonth` → verifica existência por unidade organizacional e período.
    - `findByOrganizationUnitId` → assessments de uma unidade.
    - `findByOrganizationUnitIdOrderByCreatedAtDesc` → último assessment criado, de uma organização.
    - `findByOrganizationUnitIdAndTypeOrderByCreatedAtDesc` → último assessment por tipo e uma organização.

---

## 🔹 CommentRepository

Gerencia a entidade **Comment**.

- CRUD básico.
- Consultas específicas:
    - `findByContext(productId, deliverableId, orgUnitId)` → comentários por contexto.
    - `findByQuestionIdOrderByCreatedAtAsc` → comentários de uma questão ordenados por criação.
    - `findByProductIsNotNull` / `findByDeliverableIsNotNull` → comentários vinculados a produto ou entregável.

---

## 🔹 DeliverableRepository

Gerencia a entidade **Deliverable**.

- CRUD completo.
- Consultas específicas:
    - `findAllByOrganizationUnitId` → entregáveis de uma unidade organizacional.

---

## 🔹 OrganizationTypeRepository

Gerencia a entidade **OrganizationType**.

- Apenas consulta por ID (`findById`).

---

## 🔹 OrganizationUnitRepository

Gerencia a entidade **OrganizationUnit**.

- CRUD completo.
- Consultas específicas:
    - `findByParentId` → busca unidades filhas.
    - `existsByName` → verifica existência por nome.
    - `findHierarchyById` → hierarquia de uma organização.
    - `findTopHierarchy` → unidades no topo da hierarquia.
    - `findSquadsAndTribesWithoutChildren` → squads e tribos sem filhos.

---

## 🔹 ProductRepository

Gerencia a entidade **Product**.

- CRUD completo.
- Consultas específicas:
    - `findByOrganizationUnitId` → produtos de uma unidade organizacional.

---

## 🔹 QuestionRepository

Gerencia a entidade **Question**.

- CRUD completo.
- Consultas específicas:
    - `findByIdIn` → busca múltiplas questões por lista de IDs.

---

## 🔹 QuestionSetItemRepository

Gerencia a entidade **QuestionSetItem**.

- CRUD completo.
- Consultas específicas:
    - `findByQuestionSetId` → itens de um conjunto de questões.

---

## 🔹 QuestionSetRepository

Gerencia a entidade **QuestionSet**.

- CRUD completo.
- Consultas específicas:
    - `existsById` → verifica existência por ID.

---

## 🔹 SegmentRepository

Gerencia a entidade **Segment**.

- CRUD completo.
- Consultas específicas:
    - `findAllById` → busca múltiplos segmentos por lista de IDs.