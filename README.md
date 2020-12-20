# JWT - Autenticação e melhores práticas

Repositório de melhores práticas usando JWT.

## Requisitos

Este projeto consiste de uma API feita em Node.js que consome um banco PostgreSQL. Há um arquivo `.nvmrc` no projeto caso queira realizar a instalação usando o [nvm](https://github.com/nvm-sh/nvm).

O arquivo que possui o uso das libs do JWT em si, é o `src/services/token.js`

## Rodando o projeto

Para rodar o projeto é necessário rodar um banco Postgres, sugiro o uso do docker. Pode ser usado o seguinte comando:

`docker run --name db-jwt-example -p 5432:5432 -e POSTGRES_PASSWORD=password -d postgres`

Caso queira rodar em outro local, lembre-se de editar a url no arquivo `config/database.js`.

O próximo passo é instalar as depêndencias:

`npm install`

Depois é necessário rodar a migration para criar as tabelas no banco:

`npm run sequelize:migrate`

E então pode-se rodar com nodemon:

`npm run dev`

Para facilitar os testes dos endpoints, pode ser usado o arquivo `JWT.postman_collection.json`

## Comandos para criação de chaves privada e pública

```
openssl genrsa -out private-key.pem 2048
openssl rsa -in private-key.pem -pubout -out public-key.pem
```

Caso queira usar chaves previamente geradas, copie o arquivo `.env.example` para o arquivo `.env`. Mas lembre-se: **Não** use essas chaves em produção, **apenas** para teste.
