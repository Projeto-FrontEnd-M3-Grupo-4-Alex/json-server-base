# Documentação Media-Chat

## Endpoints

### Cadastro

POST /register <br/>

{
"email": "kenzinho@mail.com",
"password": "$2a$10$YQiiz0ANVwIgpOjYXPxc0O9H2XeX3m8OoY1xk7OGgxTnOJnsZU7FO",
"name": "Kenzinho",
"bio": "Eu sou o kenzinho",
"avatar_url": "url",
}

### Login

POST /login <br/>

{
"email": "kenzinho@mail.com",
"password": "123456"
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

GET /users <br/>

### Atualizar a lista de seguidores do usuário

PATCH /users/userId

{
"followers": [userId]
}

### Realizar uma postagem

POST /posts <br/>

Corpo da requisição

{
"userId": 1,
"thumbnail": "url",
"title": "one piece",
"content": "amo esse piratão",
"tags": "#anime #aventura #piratas",
"where": "crunchyroll",
"likes": [],
"rating": 5
}

Resposta:

{
"userId": 1,
"thumbnail": "url",
"title": "one piece",
"content": "amo esse piratão",
"tags": "#anime #aventura #piratas",
"where": "crunchyroll",
"likes": [],
"rating": 5,
"id": 2
}

### Editar uma postagem

PATCH /posts/postId <br/>

Corpo de requisição

{
"content": "amo esse pirtão gostoso"
}

Resposta

{
"userId": 1,
"thumbnail": "url",
"title": "one piece",
"content": "amo esse pirtão gostoso",
"tags": "#anime #aventura #piratas",
"where": "crunchyroll",
"likes": [],
"rating": 5,
"id": 2
}

### Deletar um post

DELETE /posts/postId <br/>

### Realizar o comentário em um post

POST /comments <br/>

Corpo da requisição

{
"userId": 2,
"postId": 1,
"content": "o sasuke é um gostoso",
"like": []
}

Resposta

{
"userId": 2,
"postId": 1,
"content": "o sasuke é um gostoso",
"like": [],
"id": 5
}

### Editar um comentário

PATCH /comments/commentId <br/>

Corpo da requisição

{
"content": "o sasuke é um lindão"
}

Resposta

{
"userId": 2,
"postId": 1,
"content": "o sasuke é um lindão",
"like": [],
"id": 5
}

### Deletar um comentário

DELETE /comments/commentId <br/>
