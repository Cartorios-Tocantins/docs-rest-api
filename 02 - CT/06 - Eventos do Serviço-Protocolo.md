---
title: Endpoint de Eventos do Serviço - Protocolo - 8.3
method: PUT
url: "{{API_URL}}/api/{servico-x}/{hash}"
---


Ao receber o código, o cartório faz o serviço interno e passa a enviar eventos à empresa:
No corpo da requisição passar o campo "update" que manda atualizações sobre o status do serviço.

• Quando o protocolo for feito, é enviado um primeiro call-back informando que houve um evento novo (protocolo feito). 



```request:cURL
curl --location --request PUT "{{API_URL}}/api/servico-25o0/tGS7SjsQEH" \
  --header "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC8xMjcuMC4wLjE6ODAwMFwvYXBpXC9hdXRlbnRpY2FjYW8iLCJpYXQiOjE1OTEzNzM1NjYsImV4cCI6MTU5MTM3NzE2NiwibmJmIjoxNTkxMzczNTY2LCJqdGkiOiIxSHF3SjRXaW54UjFOdHF1Iiwic3ViIjoiNjgyNjI5YWEtZWM1OS00NTg0LWI3NDgtZjQzNWFmOGQzZjE4IiwicHJ2IjoiYzAxMGM4OGUxMWY0MWM0Njc5YTNmMzVlMmQwYWQ3YTVlOWFiOWNkMCJ9.I6Jnbww9hy8Nhrc7IyK5Z37dxZGxdpKKRIwq6s5r5yE" \
  --header "Content-Type: application/json" \
  --data "{
  \"update\": \"NOVA ATUALIZAÇÂO 1\"
}"
```


```response:200
{
  "message": "Atualização feita com sucesso"
}

```


```response:401
{
  "status": "Token is Invalid"
}

```


```response:404
{
  "message": "Serviço não existe"
}

```


```response:404
{
  "message": "Token não existe"
}

```
