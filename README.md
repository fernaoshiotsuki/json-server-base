# json-server-api-animes

Api Fake com Animes e seus respectivos personagens. 

## Endpoints

A API tem Endpoints para se cadastrar/login, visualizar animes e personagens.

### Cadastro

POST /register <br/>
Exemplo: <br/>

{"email": "Zabuza@shinobi.com",
"password": "123456",
"name": "Zabuza Momochi",
"age": "47"
}

Esse endpoint é necessario para criar um user.

Resposta- STATS 201 <br/>
Exemplo: <br/>
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Iktvbm9oYW1hcnVAc2hpbm9iaS5jb20iLCJpYXQiOjE2NDE2MDA5NjgsImV4cCI6MTY0MTYwNDU2OCwic3ViIjoiMyJ9.Ry-BPT69do4H0OCki2OTtZFpLTxzxThz1eS99Z5e6Kc",
  "user": {
    "email": "Konohamaru@shinobi.com",
    "name": "Konohamaru",
    "age": "47",
    "id": 3
  }
}

### Login

POST /login <br/>
Exemplo: <br/>
{
  "email": "Zabuza@shinobi.com",
  "password": "123456"
}

Nesse endpoint iremos fazer o login, que da acesso ao Token do usuario, necessario para algumas requisições.

Resposta- STATS 200 <br/>
Exemplo: <br/>
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6InphYnV6YUBzaGlub2JpLmNvbSIsImlhdCI6MTY0MTYwMTE2OSwiZXhwIjoxNjQxNjA0NzY5LCJzdWIiOiI0In0.BJea6Rf81y3Ka0aMBVQan4_5JOzt9rDkXGDrRbADYhA",
  "user": {
    "email": "zabuza@shinobi.com",
    "name": "Zabuza",
    "age": "68",
    "id": 4
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
    "title": "Naruto",
    "genre": "shounen",
    "userId": "2",
    "id": 1
Resposta- STATUS 200 <br/>
Exemplo: <br/>

  },
  {
    "title": "One Piece",
    "genre": "shounen",
    "userId": "2",
    "id": 2
  },
  {
    "title": "Boruto",
    "genre": "shounen",
    "userId": "2",
    "id": 3
  },
  {
    "title": "Tokyo Ghoul",
    "genre": "shounen",
    "userId": "2",
    "id": 4
  }
  ]




### Characters

GET /characters <br/>
Exemplo: <br/>
{},
{headers: {Authentication: Bearer ${Token} } }

Não é preciso fazer um corpo para requisição, apenas utilizar o token obtido no Endpoint de login.


Resposta- STATUS 200 <br/>
Exemplo: <br/>


[
  {
    "name": "Zabuza",
    "anime": "Naruto",
    "id": 1
  },
  {
    "name": "Naruto",
    "anime": "Naruto",
    "id": 2
  },
  {
    "name": "Luffy",
    "anime": "One Piece",
    "id": 3
  },
  {
    "name": "Zoro",
    "anime": "One Piece",
    "id": 4
  },
  {
    "name": "Kaneki",
    "anime": "Tokyo Ghoul",
    "id": 5
  },
  {
    "name": "Jason",
    "anime": "Tokyo Ghoul",
    "id": 6
  }
]


POST /characters <br/>
Exemplo: <br/>
{
    "name": "Kaidou",
    "anime": "One Piece"
  
  },
{headers: {Authentication: Bearer ${Token} } }

É necessario utilizar esse formato de requisição, assim como o token de usuario.

Resposta- STATUS 201 <br/>
Exemplo: <br/>


{
  "name": "Kaidou",
  "anime": "One Piece",
  "id": 8
}


###@Shiotsuki-2022

