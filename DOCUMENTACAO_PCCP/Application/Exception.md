# Exception

Este módulo possui **3 classes principais** responsáveis pelo tratamento e padronização de erros dentro da aplicação:

`ErrorDomain`, `ErrorMessageEnum` e `ServiceException`.

## 🔹 ErrorDomain

### Descrição

A classe **ErrorDomain** é responsável por encapsular informações sobre erros ocorridos na aplicação.

Ela guarda:

- Uma lista de mensagens de erro (`messages`)
- O código de status HTTP (`httpStatus`)

### Principais características

- Permite criar instâncias de erro de forma simples e padronizada.
- Facilita o retorno de erros estruturados em APIs REST.
- Garante consistência entre mensagens e status HTTP.

### Métodos estáticos

- `ErrorDomain.of(List<String> message, int httpStatus)`
Cria um objeto de erro com mensagens e status HTTP definido.
- `ErrorDomain.of(List<String> message)`
Cria um objeto de erro apenas com mensagens, sem status explícito.

---

## 🔹 ErrorMessageEnum

### Descrição

A classe **ErrorMessageEnum** é uma enumeração personalizada que contém:

- O **texto da mensagem de erro** (ex.: "Recurso não encontrado").
- O **tipo/status HTTP** associado ao erro (ex.: `400`, `404`, `403`, `422` etc).

### Principais características

- Centraliza todas as mensagens de erro da aplicação.
- Evita duplicação de mensagens e códigos em diferentes pontos do sistema.
- Facilita manutenção e internacionalização de mensagens.

### Exemplos de uso

- `COMMENT_NOT_FOUND("Comentário não encontrado", HttpStatus.BAD_REQUEST);`

---

## 🔹 ServiceException

### Descrição

A classe **ServiceException** é uma exceção personalizada que estende `HttpException`.

Ela é utilizada para lançar erros de serviço de forma controlada e padronizada.

### Principais características

- Possui um atributo `HttpStatus status` que define o tipo de erro.
- Pode ser instanciada de duas formas:
    1. **Com mensagem e causa** → Define o status como `INTERNAL_SERVER_ERROR`.
    2. **Com um `ErrorMessageEnum`** → Define a mensagem e o status conforme o enum.

### Construtores

- `ServiceException(String message, Throwable cause)`
Cria uma exceção com mensagem e causa, atribuindo status `500`.
- `ServiceException(ErrorMessageEnum errorEnum)`
Cria uma exceção com base em um enum de erro, atribuindo mensagem e status definidos.