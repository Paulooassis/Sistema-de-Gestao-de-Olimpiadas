# OrganizationUnitControllerImpl

Documentação da controller **OrganizationUnitControllerImpl**, descrevendo os métodos disponíveis, seus objetivos, parâmetros e tipos de retorno.

---

## Métodos

### createOrganizationUnit

Descrição:
Cria uma nova Unidade Organizacional (Organization Unit).

Parâmetros:

- `OrganizationUnitRequest organizationUnitRequest` – Dados necessários para criação da unidade.

Retorno:

- `201 Created` – Objeto `OrganizationUnitResponse`

---

### createParent

Descrição:
Cria uma unidade pai e a associa a uma unidade existente.

Parâmetros:

- `Long id` – Identificador da unidade filha.
- `OrganizationUnitRequest organizationUnitRequest` – Dados da nova unidade pai.

Retorno:

- `201 Created` – Objeto `OrganizationUnitResponse`

---

### updateOrganizationUnit

Descrição:
Atualiza os dados de uma Unidade Organizacional existente.

Parâmetros:

- `Long id` – Identificador da unidade.
- `OrganizationUnitRequest organizationUnitRequest` – Dados atualizados da unidade.

Retorno:

- `200 OK` – Objeto `OrganizationUnitResponse`

---

### deleteOrganizationUnit

Descrição:
Remove uma Unidade Organizacional a partir do seu identificador.

Parâmetros:

- `Long id` – Identificador da unidade.

Retorno:

- `204 No Content`

---

### getAllOrganizationUnit

Descrição:
Lista todas as Unidades Organizacionais cadastradas.

Parâmetros:

- Não possui.

Retorno:

- `200 OK` – Lista de `OrganizationUnitResponse`

---

### getAllParentHierarchy

Descrição:
Lista a hierarquia completa de todas as unidades pai do sistema.

Parâmetros:

- Não possui.

Retorno:

- `200 OK` – Lista de `OrganizationUnitResponseList`

---

### getParentHierarchy

Descrição:
Busca a hierarquia de pais de uma unidade específica.

Parâmetros:

- `Long id` – Identificador da unidade.

Retorno:

- `200 OK` – Objeto `OrganizationUnitResponseList`

---

### getSquads

Descrição:
Lista todas as unidades organizacionais classificadas como Squads ou tribos sem filho.

Parâmetros:

- Não possui.

Retorno:

- `200 OK` – Lista de `OrganizationUnitResponse`