# json-server-api-animes

Api Fake com Animes e seus respectivos personagens. <br/>
URL: "https://json-server-animes-api.herokuapp.com/"


## Endpoints

A API tem Endpoints para se cadastrar/login, visualizar animes e personagens.

### Cadastro

POST /register <br/>
Exemplo: <br/>

{"email": "Zabuza@shinobi.com", <br/>
"password": "123456", <br/>
"name": "Zabuza Momochi", <br/>
"age": "47" <br/>
}

Esse endpoint é necessario para criar um user. <br/>

Resposta- STATUS 201 <br/>
Exemplo: <br/>
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Iktvbm9oYW1hcnVAc2hpbm9iaS5jb20iLCJpYXQiOjE2NDE2MDA5NjgsImV4cCI6MTY0MTYwNDU2OCwic3ViIjoiMyJ9.Ry-BPT69do4H0OCki2OTtZFpLTxzxThz1eS99Z5e6Kc",
  "user": { <br/>
    "email": "Konohamaru@shinobi.com", <br/>
    "name": "Konohamaru", <br/>
    "age": "47", <br/>
    "id": 3 <br/>
  } <br/>
}

### Login

POST /login <br/>
Exemplo: <br/>
{
  "email": "Zabuza@shinobi.com", <br/>
  "password": "123456" <br/>
}

Nesse endpoint iremos fazer o login, que da acesso ao Token do usuario, necessario para algumas requisições.

Resposta- STATS 200 <br/>
Exemplo: <br/>
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6InphYnV6YUBzaGlub2JpLmNvbSIsImlhdCI6MTY0MTYwMTE2OSwiZXhwIjoxNjQxNjA0NzY5LCJzdWIiOiI0In0.BJea6Rf81y3Ka0aMBVQan4_5JOzt9rDkXGDrRbADYhA",
  "user": { <br/>
    "email": "zabuza@shinobi.com", <br/>
    "name": "Zabuza", <br/>
    "age": "68", <br/>
    "id": 4 <br/>
  }
}

### Animes

GET /animes <br/>
Exemplo: <br/>
{}

Não é preciso fazer um corpo para requisição.

Resposta- STATUS 200 <br/>
Exemplo: <br/>

[
  {
    "title": "Naruto", <br/>
    "genre": "shounen", <br/>
    "userId": "2", <br/>
    "id": 1 <br/>
  },
  {
    "title": "One Piece", <br/>
    "genre": "shounen", <br/>
    "userId": "2", <br/>
    "id": 2 <br/>
  },
  {
    "title": "Boruto", <br/>
    "genre": "shounen", <br/>
    "userId": "2", <br/>
    "id": 3 <br/>
  },
  {
    "title": "Tokyo Ghoul", <br/>
    "genre": "shounen", <br/>
    "userId": "2", <br/>
    "id": 4 <br/>
  }
  ]




### Characters

GET /characters <br/>
Exemplo: <br/>
{}, <br/>
{headers: {Authentication: Bearer ${Token} } } <br/>

Não é preciso fazer um corpo para requisição, apenas utilizar o token obtido no Endpoint de login.


Resposta- STATUS 200 <br/>
Exemplo: <br/>


[
  {
    "name": "Zabuza", <br/>
    "anime": "Naruto", <br/>
    "id": 1 <br/>
  },
  {
    "name": "Naruto", <br/>
    "anime": "Naruto",<br/>
    "id": 2<br/>
  },
  {
    "name": "Luffy",<br/>
    "anime": "One Piece",<br/>
    "id": 3<br/>
  },
  {
    "name": "Zoro",<br/>
    "anime": "One Piece",<br/>
    "id": 4<br/>
  },
  {
    "name": "Kaneki",<br/>
    "anime": "Tokyo Ghoul",<br/>
    "id": 5<br/>
  },
  {
    "name": "Jason",<br/>
    "anime": "Tokyo Ghoul",<br/>
    "id": 6<br/>
  }
]


POST /characters <br/>
Exemplo: <br/>
{
    "name": "Kaidou", <br/>
    "anime": "One Piece" <br/>
  
  }, <br/>
{headers: {Authentication: Bearer ${Token} } } <br/>

É necessario utilizar esse formato de requisição, assim como o token de usuario.

Resposta- STATUS 201 <br/>
Exemplo: <br/>


{
  "name": "Kaidou", <br/>
  "anime": "One Piece", <br/>
  "id": 8 <br/>
}


###@Shiotsuki-2022

