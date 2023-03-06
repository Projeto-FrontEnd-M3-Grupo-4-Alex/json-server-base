# Documentação Media-Chat

## Endpoints

### Cadastro

POST /register <br/>

{
"email": "madRabbit@email.com",
"password": "Crazyrabbit123\*",
"name": "Mad Rabbit",
"url_profile": "https://3.bp.blogspot.com/-6FQMCX_m3R8/UaMT7n1glfI/AAAAAAAABZs/zEz49Sy99X4/s1600/bunny-man.jpg"
}

### Login

POST /login <br/>

{
"email": "madRabbit@email.com",
"password": "Crazyrabbit123\*"
}

## Rotas que necessitam de autenticação

Rotas que necessitam do token para acessar funcionalidades da aplicação.
Authorization: `Bearer ${token}`

### Autologin

GET /users/userId <br/>

{
"email": "madRabbit@email.com",
"password": "$2a$10$Ei8zfZlTjO5wsKgDqlJuHuVsm2cEaRoqy994sy5Ox6enyn5rFVaIS",
"name": "Mad Rabbit",
"url_profile": "https://3.bp.blogspot.com/-6FQMCX_m3R8/UaMT7n1glfI/AAAAAAAABZs/zEz49Sy99X4/s1600/bunny-man.jpg",
"id": 2
}

### Editar Perfil

PATCH /users/userId <br/>

Exemplo de corpo de requisição:

{
"name": "Crazy Rabbit"
}

Exemplo de resposta:

{
"email": "madRabbit@email.com",
"password": "$2a$10$Ei8zfZlTjO5wsKgDqlJuHuVsm2cEaRoqy994sy5Ox6enyn5rFVaIS",
"name": "Crazy Rabbit",
"url_profile": "https://3.bp.blogspot.com/-6FQMCX_m3R8/UaMT7n1glfI/AAAAAAAABZs/zEz49Sy99X4/s1600/bunny-man.jpg",
"id": 2
}

### Deletar Usuário

DELETE /users/userId <br/>

### Pegar todos os usuários
