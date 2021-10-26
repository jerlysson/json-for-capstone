# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, feita para ser usada no desenvolvimento das API's nos Capstones do Q2.

## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.

### Login

POST /login <br/>
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

### Adcionar Descrição

POST /desc

Autorizathion: `Bearer ${token}` <br/>
body:
{
"desc": "hahahhahha", <br/>
"userId": 2,
}

GET /desc

Autorizathion: null <br/>

retorno :<br/>

{
"desc": "ex: descrição marota",<br/>
"userId": 2,<br/>
"id": 1
}

### Adcionar informações ao usuario

POST /userInfor:

Autorizathion: `Bearer ${token}` <br/>
body:<br/>
{
"bio": "esta dando certo",<br/>
"adress": "Maranhão",<br/>
"userId": 2
}

GET /userInfor:

Autorizathion: `Bearer ${token}` <br/>

response:

{
"bio": "esta dando certo", <br/>
"adress": "Maranhão", <br/>
"userId": 2, <br/>
"id": 1
}
