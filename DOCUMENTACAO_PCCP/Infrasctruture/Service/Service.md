# Service

A **camada de Service** é responsável por concentrar a **lógica de negócio** da aplicação.

Enquanto os **repositories** cuidam do acesso e persistência dos dados, os **services** atuam como intermediários entre os repositórios e os controladores (controllers), garantindo que as regras e processos sejam aplicados corretamente.

---

## 🔹 Objetivos da Service

- **Encapsular regras de negócio**: evitar que a lógica fique espalhada em diferentes partes do sistema.
- **Orquestrar chamadas aos repositórios**: combinar consultas e operações de persistência de forma consistente.
- **Tratar exceções e erros**: lançar exceções personalizadas como `ServiceException` quando necessário.
- **Facilitar manutenção e testes**: separar responsabilidades, tornando o código mais limpo e modular.

---

## 🔹 Principais Responsabilidades

1. **Validação de dados**
    - Antes de salvar ou atualizar informações, a service valida se os dados estão corretos e completos.
2. **Regras de negócio**
    - Implementa cálculos, verificações e condições específicas da aplicação.
    - Exemplo: impedir a criação de um `Assessment` duplicado para a mesma unidade organizacional e período.
3. **Integração entre entidades**
    - Coordena operações que envolvem múltiplos repositórios (ex.: salvar uma `Answer` vinculada a um `Assessment` e `Question`).
4. **Tratamento de erros**
    - Utiliza `ErrorMessageEnum` e `ServiceException` para padronizar mensagens e status HTTP.
    - Garante que os erros sejam propagados de forma clara para a camada de apresentação (API).

---

## 🔹 Lista de Services

- **ActionService**
- **AnswerService**
- **AssessmentService**
- **CommentService**
- **DeliverableService**
- **OrganizationUnitService**
- **OrganizationTypeService**
- **ProductService**
- **QuestionService**
- **QuestionSetItemService**
- **QuestionSetService**
- **SegmentService**