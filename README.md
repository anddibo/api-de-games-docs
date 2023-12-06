# API de Games h1
Esta API é utilizada para TAL e TAL...
## Endpoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados.
#### Parâmetros
Nenhum
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber a listagem de todos os games.

Exemplo de resposta:
```
[
        {
            id: 23,
            title: "Call of duty MW",
            year: 2019,
            price: 60
        },
        {
            id: 65,
            title: "Sea of thieves",
            year: 2018,
            price: 40
        },
        {
            id: 2,
            title: "Minecraft",
            year: 2012,
            price: 20
        }
    ]
```
##### Falha na autenticação! 401
Caso essa resposta aconteça significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Token inválido, Token expirado.

Exemplo de resposta:
```
{
    "err": "Token inválido!"
}
```

### POST /auth
Esse endpoint é responsável por fazer o processo de login.
#### Parâmetros
email: e-mail do usuário cadastrado no sistema.

password: senha do usuário cadastrado no sistema, com aquele determinado e-mail.

Exemplo:
```
{
    "email": "victordevtb@guiadoprogramador.com",
    "password": "nodejs<3"
}
```
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber o token JWT para conseguir acessar endpoints protegidos na API.

Exemplo de resposta:
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJ2aWN0b3JkZXZ0YkBndWlhZG9wcm9ncmFtYWRvci5jb20iLCJpYXQiOjE3MDE4MjM0ODksImV4cCI6MTcwMTk5NjI4OX0.5Z3pYs3DWX_fRWPvNURwd72BqWuVC4u73thC3rE_U_k"
}
```
##### Falha na autenticação! 401
Caso essa resposta aconteça significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: senha ou e-mail incorretos.

Exemplo de resposta:
```
{
    "err": "Credenciais inválidas!"
}
```
