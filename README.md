# api-json-server-hamburgueria

API HAMBURGUERIA

Esta API foi feita para simular um carrinho de compras. Contem três Endponts chamados: users, products e carts. Nesta API é permitido fazer cadastro, logar e cadastrar produtos no carrinho (EndPoint /carts). Não é permitido alterar produtos, somene visualiza-los.

A API ja vem com um usuário criado:
usuário: juliocezar.marketing@gmail.com
senha: 123456

Endereço base (base_url):

EndPoints:
Usuários: /users
Produtos: /products
Carrinho: /carts

Rotas
As rotas definem como você vai acessar a API.
As rotas são:

Request URL Detalhes

Usuários
POST /register Cadastra um usuário
POST /login Faz o login na API

Produtos
GET /produtos Busca todos os produtos
GET /produtos/1 Busca um produto

Carrinho
GET /carts Busca todos os produtos no carrinho
POST /carts Adiciona um produto no carrinho
PUT /carts/1 Atualiza dos os dados do produto no carrinho
PATCH /carts/1 Atualiza parte dos dados do produto no carrinho
DELETE /carts/1 Remove um produto do carrinh

As rotas vão ser compostas pelo endereço base (localhost:3000) mais o recurso que você quer acessar com por exemplo “produtos”.
Para executar os requests de exemplo abaixo você pode usar a ferramenta Postman (Insomnia) ou alguma outra de sua preferencia.
Para ver os resultados na pratica execute os exemplos no seu computador.

================================================================
=> RECURSOS PARA PRODUTOS

Exemplo 1: Buscar todos os produtos

Dados de envio

GET http://localhost:3000/produtos/
Content-Type: application/json
Retorno

"products": [
{
"id": 1,
"name": "Hamburguer",
"category": "Sanduíches",
"price": 14,
"img": "https://i.ibb.co/fpVHnZL/hamburguer.png",
"userId": 1
},
{
"id": 2,
"name": "X-Burguer",
"category": "Sanduíches",
"price": 16,
"img": "https://i.ibb.co/djbw6LV/x-burgue.png",
"userId": 1
},
{
"id": 3,
"name": "Big Kenzie",
"category": "Sanduíches",
"price": 18,
"img": "https://i.ibb.co/FYBKCwn/big-kenzie.png",
"userId": 1
},
{
"id": 4,
"name": "Fanta Guaraná",
"category": "Bebidas",
"price": 5,
"img": "https://i.ibb.co/cCjqmPM/fanta-guarana.png",
"userId": 1
},
{
"id": 5,
"name": "Coca",
"category": "Bebidas",
"price": 4.99,
"img": "https://i.ibb.co/fxCGP7k/coca-cola.png",
"userId": 1
},
{
"id": 6,
"name": "Fanta",
"category": "Bebidas",
"price": 4.99,
"img": "https://i.ibb.co/QNb3DJJ/milkshake-ovomaltine.png",
"userId": 1
}
]

Exemplo 2: Buscar apenas um produtos

Dados de envio

GET http://localhost:3000/produtos/1
Content-Type: application/json
Retorno

{
"id": 1,
"name": "Hamburguer",
"category": "Sanduíches",
"price": 14,
"img": "https://i.ibb.co/fpVHnZL/hamburguer.png",
"userId": 1
}

============================================================
RECURSOS PARA USUÁRIOS

Recursos para usuários:

Exemplo 1: Criar um usuário

Dados de envio

POST http://localhost:3000/register
Content-Type: application/json

{
"email":"juliocezar.marketing@gmail.com",
"password":"123456",
"name":"Julio Pereira",
"avatarUrl":"https://cdn.pixabay.com/photo/2013/07/13/10/07/man-156584_960_720.png"
}

Retorno

{
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Imp1bGlvY2V6YXIubWFya2V0aW5nQGdtYWlsLmNvbSIsImlhdCI6MTY0MzM5NTIzOCwiZXhwIjoxNjQzMzk4ODM4LCJzdWIi
{
"email":"juliocezar.marketing@gmail.com",
"password":"123456",
"name":"Julio Pereira",
"avatarUrl":"https://cdn.pixabay.com/photo/2013/07/13/10/07/man-156584_960_720.png"
}

Retorno

Exemplo 2: Realizar Login

Dados de envio

POST http://localhost:3000/login
Content-Type: application/json

{
"email":"juliocezar.marketing@gmail.com",
"password":"123456",
}

Retorno

{
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Imp1bGlvY2V6YXIubWFya2V0aW5nQGdtYWlsLmNvbSIsImlhdCI6MTY0MzM2OTg1MywiZXhwIjoxNjQzMzczNDUzLCJzdWIiOiIxIn0.s-5LpiclsKHkKhR_YfXihzOwbGvJ5U0KkP56GNAHPtA",
"user": {
"email": "juliocezar.marketing@gmail.com",
"name": "Julio Pereira",
"avatarUrl": "",
"id": 1
}
}

Status: 200 OK

============================================================
RECURSOS PARA CARRINHO

Recursos para o carrinho de compras:

Exemplo 1: Cadastrando um produto no carrinho

Dados de envio

POST http://localhost:3000/carts
Content-Type: application/json
Bearer Token

{
"id":1,
"name": "Hamburguer",
"category": "Sanduíches",
"price": 14,
"urlImg": "https://i.ibb.co/fpVHnZL/hamburguer.png",
"qtd": 1,
"userId": 1
}

Retorno

{
"id": 1,
"name": "Hamburguer",
"category": "Sanduíches",
"price": 14,
"urlImg": "https://i.ibb.co/fpVHnZL/hamburguer.png",
"qtd": 1,
"userId": 1
}

Exemplo 1: Buscar todos os produtos no carrinho

Dados de envio

GET http://localhost:3000/carts
Content-Type: application/json
Bearer Token

Retorno

[
{
"id": 1,
"name": "Hamburguer",
"category": "Sanduíches",
"price": 14,
"urlImg": "https://i.ibb.co/fpVHnZL/hamburguer.png",
"qtd": 1,
"userId": 1
},{
"id": 2,
"name": "Hamburguer",
"category": "Sanduíches",
"price": 14,
"urlImg": "https://i.ibb.co/fpVHnZL/hamburguer.png",
"qtd": 1,
"userId": 1
}
]

Exemplo 2: Buscar apenas um produto no carrinho

Dados de envio

GET http://localhost:3000/carts/1
Content-Type: application/json
Bearer Token

Retorno

{
"id": 1,
"name": "Hamburguer",
"category": "Sanduíches",
"price": 14,
"urlImg": "https://i.ibb.co/fpVHnZL/hamburguer.png",
"qtd": 1,
"userId": 1
}

Exemplo 4: Alterar um produto

Dados de envio

PUT http://localhost:3000/carts/1
Content-Type: application/json
Bearer Token

{
"id": 1,
"name": "Novo nome",
"category": "Nova Categoria",
"price": 20,
"urlImg": "https://i.ibb.co/fpVHnZL/novaimagem.png",
"qtd": 5,
"userId": 1
}

Retorno

{
"id": 1,
"name": "Novo nome",
"category": "Nova Categoria",
"price": 20,
"urlImg": "https://i.ibb.co/fpVHnZL/novaimagem.png",
"qtd": 5,
"userId": 1
}

Exemplo 5: Alterar apenas uma propriedade do produto no carrinho

Dados de envio

PATCH http://localhost:3000/carts/1
Content-Type: application/json
Bearer Token

{
"name": "Hambúrguer de frango artezanal"
}

Retorno

{
"id": 1,
"name": "Hambúrguer de frango artezanal"
"category": "Nova Categoria",
"price": 20,
"urlImg": "https://i.ibb.co/fpVHnZL/novaimagem.png",
"qtd": 5,
"userId": 1
}

Exemplo 6: Excluir um produto do carrinho

Dados de envio

DELETE http://localhost:3000/carts/1
Content-Type: application/json
Bearer Token

Retorno

Status: 200 OK

3 – Filtros
Para executar filtros é bem simples, você só precisa usar o nome das propriedades do objeto que você quer pesquisar.
No exemplo abaixo estou pesquisando por produtos que o nome é “X-Búrguer”

Dados de envio

GET http://localhost:3000/produtos?nome=X-Búrguer
Content-Type: application/json
Bearer Token

Retorno

[
{
"id": 2,
"nome": "X-Búrguer",
"descricao": "Pão, bife de hambúrguer 90g, 1 fatia de queijo, salada e batata.",
"preco": 10.5,
"categoria_id": 1
}
]
