---
title: Endpoint Solicitação de Serviço
method: POST
url: "{{API_URL}}/api/{servico-x}/{hash}"
---


Em posse do código de autorização, a empresa entra em contato com o cartório, informando o código. 

*   "servico-25o0" é o nome do serviço(servico-x), portanto ele é o identificador do serviço
que o cliente solicita.
Consulte os serviços prestados em 6- Especificação de Endpoint de Serviços.
Altere o (servico-x) parâmetro,conforme o serviço que desejar.



```request:cURL
curl --location --request POST "{{API_URL}}/api/servico-25o0/tGS7SjsQEH" \
  --header "Content-Type: application/json" \ 
  --header "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC8xMjcuMC4wLjE6ODAwMFwvYXBpXC9hdXRlbnRpY2FjYW8iLCJpYXQiOjE1OTEzNzI2MjksImV4cCI6MTU5MTM3NjIyOSwibmJmIjoxNTkxMzcyNjI5LCJqdGkiOiJjdGJxM3hWODJKWXBkVmJ3Iiwic3ViIjoiNjgyNjI5YWEtZWM1OS00NTg0LWI3NDgtZjQzNWFmOGQzZjE4IiwicHJ2IjoiYzAxMGM4OGUxMWY0MWM0Njc5YTNmMzVlMmQwYWQ3YTVlOWFiOWNkMCJ9.q49pbkhNtk_dBd88r5ygJJl1RtSlYrVHiLAbjeUcs3A"


```


```response:200
{
  "mensagem": "Atualização feita com sucesso"
}
```


```response:401
{
  "mensagem": "Token Inválido"
}
```