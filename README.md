## Endpoints

    URL_BASE: https://json-capstone.herokuapp.com/

### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

body{<br/>
"email": "",<br/>
"password": 12345678,<br/>
"name": "Kenzinho",<br/>
"age": 38,<br/>
}<br/>

response {<br/>
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.<br/>eyJlbWFpbCI6Implcmx5c3NvbkBtYWlsLmNvbSIsImlhdCI6MTYzNjQ2NzAzOCwiZXhwIjoxNjM2NDcwNjM4LCJzdWIiOiIyIn0.xtbIKXcdo9ScyW2t8jq5m8R2o7LubqNwad9NcTCPoCQ",
"user": {
"email": "example@mail.com",<br/>
"name": "Kenzinho",<br/>
"age": 38,<br/>
"id": 1<br/>
}<br/>
}<br/>

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.

### Login

POST /login <br/>
POST /signin<br/>

body{<br/>
"email": "example@mail.com",<br/>
"password": 12345678,<br/>
}<br/>
response{<br/>
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Implcmx5c3NvbkBtYWlsLmNvbSIsImlhdCI6MTYzNjQ3NzUxMywiZXhwIjoxNjM2NDgxMTEzLCJzdWIiOiIyIn0.b_L-9X6krHfACvVAJK7TPFjodX4OHXs_zVV5yhLP3FY",
"user": {
"email": "example@mail.com",<br/>
"name": "Kenzinho",<br/>
"age": 38,<br/>
"id": 1,<br/>
"store": false<br/>
}<br/>
}

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

### PRECISA ESTAR LOGADO

### Buscar produtos

GET/ products <br/>
<br/>
Response <br/>
{<br/>
"name": "Produto teste 1",<br/>
"description": "uma descrição",<br/>
"Price": 10,<br/>
"userId": 1<br/>
}<br/>

### adcionar feedbak ao produtos

POST/comments<br/>

body{<br/>

    "description": "muito bom o produto",
    "productId": 1

}<br/>
Response {<br/>
"description": "muito bom o produto",
"productId": 1,
"id": 1
}<br/>

###BUSCAR FEEDBACK DE UM CERTO PRODUTO

productID = 1 <--- aqui seria o id do produto "ex. acima seria o 'id=1' "

GET`/products/${productID}?\_embed=comments`

reponse {
"id": 1,
"name": "Produto teste",
"description": "uma descrição",
"Price": 10,
"userId": 2,
"comments": [
{
"id": 1,
"description": "muito bom o produto",
"productId": 1
}
]
}

### adcionar feedbak ao Vendedor

POST/comments<br/>

body{<br/>

    "description": "muito bom o vendedor",
    "userId": 1

}
response{
"description": "Otimo vendedor",
"userId": 2,
"id": 1
}
###BUSCAR FEEDBACK DE UM CERTO VENDEDOR

vendedorID = 1 <--- aqui seria o id do produto "ex. acima seria o 'id=1' "

GET`/products/${userId}?\_embed=comments` <br/>

reponse {
"email": "example@mail.com",
"password": "$2a$10$p5dLxl7jW7IwqEDb6QcKreTlmM4avlsspknRjlb7s9GbVPBbOmsv.",
"name": "example",
"age": 28,
"id": 2,
"store": true,
"comments": [
{
"id": 1,
"description": "feedback para o vendedor",
"userId": 2
}
]
}
