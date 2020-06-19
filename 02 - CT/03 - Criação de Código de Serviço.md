---
title: Criação de Código de Serviço
method: POST
url: "{{API_URL}}/api/servico"
---


Via API, um sistema de cliente deve poder gerar um hash de acompanhamento de serviço vinculado ao CNPJ dele e a um CNS de cartório.
Esse código de acompanhamento deve estar vinculado ao CNPJ da empresa e ao CNS de cartório. 

Passe o "cns" no corpo da requisição.


Envio:
Solicita um hash para execução do serviço, através do CNS do Cartório.

```request:cURL
curl --location --request POST "{{API_URL}}/api/servico" \
  --header "Content-Type: application/json" \
  --header "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC8xMjcuMC4wLjE6ODAwMFwvYXBpXC9hdXRlbnRpY2FjYW8iLCJpYXQiOjE1OTEzNjgxMzgsImV4cCI6MTU5MTM3MTczOCwibmJmIjoxNTkxMzY4MTM4LCJqdGkiOiI4NGNkOThmYkNjcjRGaE41Iiwic3ViIjoiNjgyNjI5YWEtZWM1OS00NTg0LWI3NDgtZjQzNWFmOGQzZjE4IiwicHJ2IjoiYzAxMGM4OGUxMWY0MWM0Njc5YTNmMzVlMmQwYWQ3YTVlOWFiOWNkMCJ9.LgvKBsn96gVKPZCh85MJmVyh2KZR1k3dO8gUmqt5oJQ" \
  --data "{
	\"cns\" : \"123456\"
}"
```


```response:200
{
  "mensagem": "Criado com sucesso",
  "hash": "tGS7SjsQEH"
}
```


```response:401
{
  "mensagem": "Token Inválido"
}
```


```response:404
{
  "mensagem": "Cartório não existe"
}
```
