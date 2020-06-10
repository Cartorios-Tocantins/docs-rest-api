---
title: Me - Retorna os Dados do Usuário Autenticado -
method: POST
url: "{{API_URL}}/api/me"
---


Me - Retorna os Dados do Usuário Autenticado - 

Retorna os dados do usuário através do JWT token.


```request:cURL
curl --location --request GET "{{API_URL}}/me" \
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
