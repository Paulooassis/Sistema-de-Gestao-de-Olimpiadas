# QuestionResponseType (Tipo de Resposta da Pergunta)

**Valores:**

- `NUMERIC` — Numérico
- `TEXT` — Texto
- `BOOLEAN` — Booleano

**Propósito:**
Define o tipo de dado esperado para a resposta de uma pergunta. Esse enum influencia:

- a interface do usuário (campo numérico, texto ou seletor Sim/Não);
- a forma de persistência da resposta na tabela `answer` (`value_numeric` ou `value_text`).