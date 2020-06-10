---
title: Logout
method: GET
url: "{{CARTORIO_URL}}:/api/logout"
---


Logout - 

Faz o logout do usuário.


```request:cURL
curl --location --request GET "{{CARTORIO_URL}}/me" \
  --header "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC8xMjcuMC4wLjE6ODAwMFwvYXBpXC9hdXRlbnRpY2FjYW8iLCJpYXQiOjE1OTEzODYxNDksImV4cCI6MTU5MTM4OTc0OSwibmJmIjoxNTkxMzg2MTQ5LCJqdGkiOiJSU0lzVVJhd1p3bktzbUR0Iiwic3ViIjoiOWI4OWJmNGUtYjJiMi00NWUwLTgyMWQtOWExZjIwOTA1ZDk3IiwicHJ2IjoiZTZkNjA2MDAwM2RkZDZkNzc5NjJjMDNjYjJiYjMyMjI5YmNlYTFjNSJ9.f1R3KbrIG8tFDc1BajkA4ntEKm2xI7Hj2i7_nNEMoUc" \
  --header "Content-Type: application/json" \
  --data ""
```


```response:200
{
  "id": "9b89bf4e-b2b2-45e0-821d-9a1f20905d97",
  "name": "Nome do Usuário",
  "cpf": "123.456.789-12",
  "email": "cartorio1@cartorio.com.br"
}

```


```response:401
{
  "status": "Token is Invalid"
}

```













- [URI](#uri)
- [Header](#header)
- [URL Params](#params)
- [Body](#body)
- [Response](#response)

<a name="uri"></a>
## URI

| Method | URI | 
| : |   :-   |
| GET | `/api/logout` |

<a name="header"></a>
## Header

```markup 
Content-Type : application/json
Authorization : Bearer _token_do_jwt
```

<a name="params"></a>
## URL Params

```markup 
none
```

<a name="body"></a>
## Body

```markup 
none
```

<a name="response"></a>
## Response

> {success.fa-check-circle} Success Response

Code: `200`

Content:

```json 
{
    "Mensagem": "Deslogado com sucesso!"
}
```