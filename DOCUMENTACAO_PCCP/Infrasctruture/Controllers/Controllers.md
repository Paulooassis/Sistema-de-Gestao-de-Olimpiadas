# Controllers

Este documento descreve o papel, os padrões e as boas práticas adotadas para a camada de **Controllers** no projeto **PCCP**.

## Visão Geral

As **Controllers** representam a camada responsável por expor os **endpoints da aplicação**, seguindo o padrão **RESTful**. Elas atuam como ponto de entrada das requisições HTTP, recebendo dados do cliente, delegando o processamento para a camada de **Service** e retornando respostas adequadas, sempre com o **HttpStatus** correto e utilizando **DTOs** como modelo de resposta.

O principal objetivo dessa camada é **orquestrar a comunicação HTTP**, sem conter regras de negócio ou lógica complexa.

## Padrão RESTful

Os endpoints definidos nas controllers seguem os princípios REST, tais como:

- Uso adequado dos métodos HTTP (`GET`, `POST`, `PUT`, `PATCH`, `DELETE`);
- Endpoints orientados a recursos;
- Respostas padronizadas e previsíveis;
- Uso correto dos códigos de status HTTP;
- Comunicação baseada em DTOs.

## Integração com Swagger

No projeto **PCCP**, utilizamos o arquivo **`swagger.yml`** como base para a definição dos contratos da API.

Esse arquivo é utilizado para:

- Definir endpoints, parâmetros e modelos de dados;
- Gerar a interface das controllers;
- Garantir padronização entre documentação e implementação;
- Facilitar o entendimento e consumo da API.

> 📌 Para entender como utilizar e atualizar o `swagger.yml`, consulte o arquivo [**README.md**](http://README.md) do projeto.
> 

## Estrutura das Controllers

Cada controller é composta por:

- **Interface da Controller**: definida a partir do contrato gerado pelo Swagger;
- **ControllerImpl**: classe responsável por implementar a interface.

### ControllerImpl

Nos arquivos `ControllerImpl`, é **obrigatório** implementar todos os métodos definidos na interface da controller.

Essas classes devem seguir rigorosamente as seguintes regras:

- ✅ Ter acesso **apenas à camada de Service**;
- ❌ Não realizar mapeamentos (Mappers);
- ❌ Não conter regras de negócio;
- ❌ Não tratar exceções diretamente;
- ❌ Não construir lógica complexa;
- ✅ Apenas delegar a chamada para o service correspondente;
- ✅ Retornar a resposta correta com o `HttpStatus` adequado.

A controller deve ser **simples, objetiva e previsível**.

## Uso de DTOs

As respostas das controllers devem sempre utilizar **DTOs**, garantindo:

- Isolamento entre o domínio interno e a API;
- Maior controle sobre os dados expostos;
- Facilidade de manutenção e evolução da API.

O tipo de retorno da controller deve ser um `HttpResponse<DTO>`, respeitando o contrato definido no Swagger.

## Códigos de Status HTTP

O uso correto dos **HttpStatus** é de suma importância para a clareza e padronização da API. Alguns exemplos comuns:

- **200 OK**: Requisição realizada com sucesso;
- **201 Created**: Recurso criado com sucesso;
- **204 No Content**: Operação realizada com sucesso, sem corpo de resposta;
- **400 Bad Request**: Erro de validação ou requisição inválida;
- **401 Unauthorized**: Usuário não autenticado;
- **403 Forbidden**: Usuário autenticado, porém sem permissão;
- **404 Not Found**: Recurso não encontrado;
- **409 Conflict**: Conflito de estado (ex: recurso duplicado);
- **500 Internal Server Error**: Erro inesperado no servidor.

Cada endpoint deve retornar **sempre o status que melhor represente o resultado da operação**, conforme definido no Swagger.

## Responsabilidades da Controller

Em resumo, a controller deve:

- Expor endpoints REST;
- Delegar o processamento para a camada de Service;
- Retornar DTOs com o HttpStatus correto;
- Seguir fielmente o contrato definido no Swagger.

[ActionControllerImpl](ActionControllerImpl%200d3bf7e4088c4b37b977760bacbab659.md)

[AnswerControllerImpl](AnswerControllerImpl%201ff9709e63ec4ad4905d850bbf209876.md)

[AssessmentControllerImpl](AssessmentControllerImpl%20baa3b542262b4fe69d35016543a422bf.md)

[CommentControllerImpl](CommentControllerImpl%206d675aba21114fec8e448d0194a6aaa4.md)

[DeliverableControllerImpl](DeliverableControllerImpl%20ae3fe0d53be14c4393ec7a72b52697df.md)

[OrganizationUnitControllerImpl](OrganizationUnitControllerImpl%202f6e7573f936807c8d98cf2a6cfbd299.md)

[ProductControllerImpl](ProductControllerImpl%202f6e7573f9368063bcf9e2240ad30d4f.md)

[QuestionControllerImpl](QuestionControllerImpl%202f6e7573f936806d8e8fdbea14de41d3.md)

[QuestionSetControllerImpl](QuestionSetControllerImpl%202f6e7573f936807e8f97d241314089cf.md)

[QuestionSetItemControllerImpl](QuestionSetItemControllerImpl%202f6e7573f936804e84c6f91c95499b73.md)

[SegmentControllerImpl](SegmentControllerImpl%202f6e7573f93680e2b58fd0e2e9d7a994.md)