---
title: Logout -
method: POST
url: "{{CARTORIO_URL}}:/api/logout"
---


Logout - 

Faz o logout do usuário.


```request:cURL
curl --location --request POST "{{CARTORIO_URL}}/logout" \
  --header "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC8xMjcuMC4wLjE6ODAwMFwvYXBpXC9hdXRlbnRpY2FjYW8iLCJpYXQiOjE1OTEzODYxNDksImV4cCI6MTU5MTM4OTc0OSwibmJmIjoxNTkxMzg2MTQ5LCJqdGkiOiJSU0lzVVJhd1p3bktzbUR0Iiwic3ViIjoiOWI4OWJmNGUtYjJiMi00NWUwLTgyMWQtOWExZjIwOTA1ZDk3IiwicHJ2IjoiZTZkNjA2MDAwM2RkZDZkNzc5NjJjMDNjYjJiYjMyMjI5YmNlYTFjNSJ9.f1R3KbrIG8tFDc1BajkA4ntEKm2xI7Hj2i7_nNEMoUc" \
  --header "Content-Type: application/json" \
  --data ""
```


```response:200
{
    "Mensagem": "Deslogado com sucesso!"
}

```


```response:401
{
  "status": "Token is Invalid"
}

```