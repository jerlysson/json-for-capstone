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
    "productId": 1   <-- aqui determina de onde é o comentario

}<br/>
Response {<br/>
"description": "muito bom o produto",<br/>
"productId": 1,<br/>
"id": 1<br/>
}<br/>

###BUSCAR FEEDBACK DE UM CERTO PRODUTO

productID = 1 <--- aqui seria o id do produto "ex. acima seria o 'id=1' "<br/>

GET`/products/${productID}?\_embed=comments`<br/>

reponse {<br/>
"id": 1,<br/>
"name": "Produto teste",<br/>
"description": "uma descrição",<br/>
"price": 10,<br/>
"userId": 2,<br/>
"comments": [<br/>
{<br/>
"id": 1,<br/>
"description": "muito bom o produto",<br/>
"productId": 1<br/>
}<br/>
]<br/>
}

### adcionar feedbak ao Vendedor

POST/comments<br/>

body{<br/>

    "description": "muito bom o vendedor",
    "userId": 1 <-- aqui determina de onde é o comentario

}
response{<br/>
"description": "feedback para o vendedor",<br/>
"userId": 2,<br/>
"id": 1<br/>
}
<br/>
###BUSCAR FEEDBACK DE UM CERTO VENDEDOR

vendedorID = 1 <--- aqui seria o id do produto "ex. acima seria o 'id=1' "<br/>

GET`/products/${userId}?\_embed=comments` <br/>

reponse {<br/>
"email": "example@mail.com",<br/>
"password": "$2a$10$p5dLxl7jW7IwqEDb6QcKreTlmM4avlsspknRjlb7s9GbVPBbOmsv.",<br/>
"name": "example",<br/>
"age": 28,<br/>
"id": 2,<br/>
"store": true,<br/>
"comments": [<br/>
{<br/>
"id": 1,<br/>
"description": "feedback para o vendedor",<br/>
"userId": 2<br/>
}
]
}
