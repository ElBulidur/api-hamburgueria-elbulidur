<h1 align="center">API HAMBURGUERIA </h1>

Esta API foi feita para simular um carrinho de compras. Contem três Endponts chamados: users, products e carts. Nesta API é permitido fazer cadastro, logar e cadastrar produtos no carrinho (EndPoint /carts). Não é permitido alterar produtos, somene visualiza-los.

<h4 style="font-weight:bold; color:green">  => A API ja vem com um usuário criado:</h4>

usuário: juliocezar.marketing@gmail.com <br />
senha: 123456

<h4 style="font-weight:bold; color:green">=> Endereço base
(base_url) </h4>

https://api-hamburgueria-elbulidur.herokuapp.com

<h4 style="font-weight:bold; color:green">EndPoints:</h4>

Usuários: /users <br />
Produtos: /products <br />
Carrinho: /carts

<h4 style="font-weight:bold; color:green">=> Rotas</h4>

As rotas definem como você vai acessar a API.<br />
As rotas são:

<h4 style="font-weight:bold; color:purple">Produtos</h4>

GET /produtos <=> Busca todos os produtos<br />
GET /produtos/1 <=> Busca um produto

<h4 style="font-weight:bold; color:yellow">Usuários</h4>

POST /register <=> Cadastra um usuário <br />
POST /login <=> Faz o login na API

<h4 style="font-weight:bold; color:greenyellow">Carrinho</h4>

GET /carts <=> Busca todos os produtos no carrinho<br />
POST /carts <=> Adiciona um produto no carrinho<br />
PUT /carts/1 <=> Atualiza dos os dados do produto no carrinho<br />
PATCH /carts/1 <=> Atualiza parte dos dados do produto no carrinho<br />
DELETE /carts/1 <=> Remove um produto do carrinho

<p style="color:green"> As rotas vão ser compostas pelo endereço base (localhost:3000) mais o recurso que você quer acessar com por exemplo “produtos”.
Para executar os requests de exemplo abaixo você pode usar a ferramenta Insomnia ou alguma outra de sua preferencia.
Para ver os resultados na pratica execute os exemplos no seu computador. </p>

====================================================<br />

<h2 style="font-weight:bold; color:purple">=> RECURSOS PARA PRODUTOS </h2>

<p style="color:red"> Exemplo 1: Buscar todos os produtos</p>

:>>>>>>> Dados de envio

```
GET http://localhost:3000/produtos/<br />
Content-Type: application/json
```

<<<<<<<<: Retorno

```
“products”: [
{
“id”: 1,
“name”: “Hamburguer”,
“category”: “Sanduíches”,
“price”: 14,
“img”: “https://i.ibb.co/fpVHnZL/hamburguer.png“,
“userId”: 1
},
{
“id”: 2,
“name”: “X-Burguer”,
“category”: “Sanduíches”,
“price”: 16,
“img”: “https://i.ibb.co/djbw6LV/x-burgue.png“,
“userId”: 1
},
{
“id”: 3,
“name”: “Big Kenzie”,
“category”: “Sanduíches”,
“price”: 18,
“img”: “https://i.ibb.co/FYBKCwn/big-kenzie.png“,
“userId”: 1
},
{
“id”: 4,
“name”: “Combo Kenzie”,
“category”: “Combos”,
“price”: 26,
“img”: “https://cantinatiobento.com.br/wp-content/uploads/2020/12/CHEESEBURGERCOCA-1.png“,
“userId”: 1
},
{
“id”: 5,
“name”: “Fanta Guaraná”,
“category”: “Bebidas”,
“price”: 5,
“img”: “https://i.ibb.co/cCjqmPM/fanta-guarana.png“,
“userId”: 1
},
{
“id”: 6,
“name”: “Coca”,
“category”: “Bebidas”,
“price”: 4.99,
“img”: “https://i.ibb.co/fxCGP7k/coca-cola.png“,
“userId”: 1
},
{
“id”: 7,
“name”: “McShake Ovomaltine”,
“category”: “Sobremesas”,
“price”: 10,
“img”: “https://i.ibb.co/QNb3DJJ/milkshake-ovomaltine.png“,
“userId”: 1
},
{
“id”: 8,
“name”: “McShake Ovomaltine”,
“category”: “Sobremesas”,
“price”: 10,
“img”: “http://s2.glbimg.com/ICoREYf5qoOiFkGmxnCVJBlEqf0=/620x500/s2.glbimg.com/t2SngMVdFNPzWZxsABxUkGYopLw=/s.glbimg.com/jo/g1/f/original/2016/09/13/milk.jpg“,
“userId”: 1
}
]
```

<p style="color:red">Exemplo 2: Buscar apenas um produtos</p>

:>>>>>>> Dados de envio

```
GET http://localhost:3000/produtos/1<br />
Content-Type: application/json
```

<<<<<<<<: Retorno

```
{
"id": 1,
"name": "Hamburguer",
"category": "Sanduíches",
"price": 14,
"img": "https://i.ibb.co/fpVHnZL/hamburguer.png",
"userId": 1
}
```

============================================================

<h2 style="font-weight:bold; color:yellow"> => RECURSOS PARA USUÁRIOS</h2>

Recursos para usuários:

<p style="color:red"> Exemplo 1: Criar um usuário</p>

:>>>>>>> Dados de envio

```
POST http://localhost:3000/register
Content-Type: application/json

{
    "email":"juliocezar.marketing@gmail.com",
    "password":"123456",
    "name":"Julio Pereira",
    "avatarUrl":"https://cdn.pixabay.com/photo/2013/07/13/10/07/man-156584_960_720.png"
}
```

<<<<<<<<: Retorno

```
{
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Imp1bGlvY2V6YXIubWFya2V0aW5nQGdtYWlsLmNvbSIsImlhdCI6MTY0MzM5NTIzOCwiZXhwIjoxNjQzMzk4ODM4LCJzdWIi
{
    "email":"juliocezar.marketing@gmail.com",
    "password":"123456",
    "name":"Julio Pereira",
    "avatarUrl":"https://cdn.pixabay.com/photo/2013/07/13/10/07/man-156584_960_720.png"
}
```

<p style="color:red">Exemplo 2: Realizar Login></p>

:>>>>>>> Dados de envio

```
POST http://localhost:3000/login
Content-Type: application/json

{
    "email":"juliocezar.marketing@gmail.com",
    "password":"123456",
}
```

<<<<<<<<: Retorno

```
{
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Imp1bGlvY2V6YXIubWFya2V0aW5nQGdtYWlsLmNvbSIsImlhdCI6MTY0MzM2OTg1MywiZXhwIjoxNjQzMzczNDUzLCJzdWIiOiIxIn0.s-5LpiclsKHkKhR_YfXihzOwbGvJ5U0KkP56GNAHPtA",
    "user": {
    "email": "juliocezar.marketing@gmail.com",
    "name": "Julio Pereira",
    "avatarUrl": "",
    "id": 1
}
```

<span style="color:greenyellow">Status: 200 OK</span>

=======================================================

<h2 style="font-weight:bold; color:greenyellow"> => RECURSOS PARA CARRINHO </h2>

Recursos para o carrinho de compras:

<p style="color:red">Exemplo 1: Cadastrando um produto no carrinho</p>

:>>>>>>> Dados de envio

```
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
```

<<<<<<<<: Retorno

```
{
    "id": 1,
    "name": "Hamburguer",
    "category": "Sanduíches",
    "price": 14,
    "urlImg": "https://i.ibb.co/fpVHnZL/hamburguer.png",
    "qtd": 1,
    "userId": 1
}
```

<p style="color:red">Exemplo 2: Buscar todos os produtos no carrinho</p>

:>>>>>>> Dados de envio

```
GET http://localhost:3000/carts
Content-Type: application/json
Bearer Token
```

<<<<<<<<: Retorno

```
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
```

<p style="color:red">Exemplo 3: Buscar apenas um produto no carrinho</p>

:>>>>>>> Dados de envio

```
GET http://localhost:3000/carts/1
Content-Type: application/json
Bearer Token
```

<<<<<<<<: Retorno

```
{
    "id": 1,
    "name": "Hamburguer",
    "category": "Sanduíches",
    "price": 14,
    "urlImg": "https://i.ibb.co/fpVHnZL/hamburguer.png",
    "qtd": 1,
    "userId": 1
}
```

<p style="color:red">Exemplo 4: Alterar um produto</p>

:>>>>>>> Dados de envio

```
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
```

<<<<<<<<: Retorno

```
{
    "id": 1,
    "name": "Novo nome",
    "category": "Nova Categoria",
    "price": 20,
    "urlImg": "https://i.ibb.co/fpVHnZL/novaimagem.png",
    "qtd": 5,
    "userId": 1
}
```

<p style="color:red">Exemplo 5: Alterar apenas uma propriedade do produto no carrinho</p>

:>>>>>>> Dados de envio

```
PATCH http://localhost:3000/carts/1
Content-Type: application/json
Bearer Token

{
    "name": "Hambúrguer de frango artezanal"
}
```

<<<<<<<<: Retorno

```
{
    "id": 1,
    "name": "Hambúrguer de frango artezanal"
    "category": "Nova Categoria",
    "price": 20,
    "urlImg": "https://i.ibb.co/fpVHnZL/novaimagem.png",
    "qtd": 5,
    "userId": 1
}
```

<p style="color:red">Exemplo 6: Excluir um produto do carrinho</p>

:>>>>>>> Dados de envio

```
DELETE http://localhost:3000/carts/1
Content-Type: application/json
Bearer Token
```

<<<<<<<<: Retorno

<span style="color:greenyellow">Status: 200 OK</sspan>

<h2 style="font-weight:bold; color:orange">Filtros</h2>

Para executar filtros é bem simples, você só precisa usar o nome das propriedades do objeto que você quer pesquisar.
No exemplo abaixo estou pesquisando por produtos que o nome é “X-Búrguer”

:>>>>>>> Dados de envio

```
GET http://localhost:3000/produtos?nome=X-Búrguer
Content-Type: application/json
Bearer Token
```

<<<<<<<<: Retorno

```
[
{
    "id": 2,
    "nome": "X-Búrguer",
    "descricao": "Pão, bife de hambúrguer 90g, 1 fatia de queijo, salada e batata.",
    "preco": 10.5,
    "categoria_id": 1
}
]
```
