# ContextEnum (Enum de Contexto)

**Valores:**

- `PRODUCT`
- `ENGINEERING`

**Propósito:**
Enum de uso interno no backend. É utilizado para validar o contexto de execução de uma requisição ou regra de negócio, direcionando o fluxo correto do código e permitindo o tratamento de contextos inválidos (ex: `ServiceException(ErrorMessageEnum.INVALID_CONTEXT)`).