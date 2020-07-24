# Desafio: Conceitos do Node.js

O desafio consiste na criação de uma aplicação para armazenar repositórios do seu portfólio, que irá permitir a criação, listagem, atualização e remoção dos repositórios, e além disso permitir que os repositórios possam receber "likes".

## Comandos utilizados no projeto

- yarn init -y
- yarn add express
- yarn add uuidv4
- yarn add nodemon -D

## Comando para execução

- yarn dev

## Comando para realizar testes

- yarn test

# Anotações

## Métodos HTTP:

- GET: Buscar informações do Back-end
- POST: Criar uma informação no Back-end
- DELETE: Deletar uma informação no Back-end
- PUT/PATCH: Alterar uma informação no Back-end

## Tipos de parâmetros:

- Query Params: Filtros e paginação ('?chave=valor')
- Route Params: Identificar recursos para atualizar ou deletar ('/:parametro')
- Request Body: Conteúdo na hora de criar ou editar um recurso (JSON)

## Middleware:

Interceptador de requisições que interrompe totalmente a requisição
Pode alterar dados da requisição

Exemplo:

``` javascript
function validateId(request, response, next) {
  const { id } = request.params;
  if (!isUuid(id)) {
    return response.status(400).json({ error: 'Invalid repository ID.' });
  }
  return next();
}
app.use('/repositories:id', validateId);

```

Feito por [Leonardo Soares](https://www.linkedin.com/in/leonardo-soares/). 🚀
