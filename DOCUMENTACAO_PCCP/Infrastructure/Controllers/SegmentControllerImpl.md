# SegmentControllerImpl

Documentação da controller **SegmentControllerImpl**, descrevendo os métodos disponíveis, seus objetivos, parâmetros e tipos de retorno. Nesta aplicação, os **Segments** representam os temas abordados dentro das avaliações.

---

## Métodos

### createSegment

Descrição:
Cria um novo Segment (tema de avaliação).

Parâmetros:

- `SegmentRequest segmentRequest` – Dados necessários para a criação do tema.

Retorno:

- `201 Created` – Objeto `SegmentResponse`

---

### deleteSegment

Descrição:
Remove um tema (Segment) a partir do seu identificador.

Parâmetros:

- `Long id` – Identificador do tema.

Retorno:

- `204 No Content`

---

### getAllSegments

Descrição:
Lista todos os temas de avaliação cadastrados.

Parâmetros:

- Não possui.

Retorno:

- `200 OK` – Lista de `SegmentResponse`

---

### getSegmentById

Descrição:
Busca um tema específico pelo seu identificador.

Parâmetros:

- `Long id` – Identificador do tema.

Retorno:

- `200 OK` – Objeto `SegmentResponse`

---

### updateSegment

Descrição:
Atualiza os dados de um tema (Segment) existente.

Parâmetros:

- `Long id` – Identificador do tema.
- `SegmentRequest segmentRequest` – Dados atualizados do tema.

Retorno:

- `200 OK` – Objeto `SegmentResponse`