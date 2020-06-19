---
title: Endpoint de Autenticação
method: POST
url: "{{API_URL}}/api/autenticacao"
---


Após a validação dos cadastros, os usuários poderão utilizar o Endpoint de Autenticação para logar no sistema.

• Via API: A aplicação do cliente deve poder fazer autenticação via API utilizando sua identificação CNS/CNPJ e seu hash de acesso. 


Envio:
Enviar um identificador, que poderá ser o CNS (no caso do Cartório) ou CNPJ (no caso de Empresa)
e passe (senha).


```request:cURL
curl --location --request POST '{{API_URL}}/api/autenticacao' \
--header 'Content-Type: application/json' \
--data-raw '{
	"identificacao": "123456",
	"passe": "123456"
}'
```


```request:Python
import requests

url = "{{CARTORIO_URL}}/autenticacao"

payload = "{\"identificacao\": \"123456\", \"passe\": \"123456\"\n}"
headers = {
  'Content-Type': 'application/json'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))
```


```response:200
{
  "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC94cHRvLmxvY2FsaG9zdFwvYXBpXC9hdXRlbnRpY2FjYW8iLCJpYXQiOjE1OTA0NjI4NjEsImV4cCI6MTU5MDQ2NjQ2MSwibmJmIjoxNTkwNDYyODYxLCJqdGkiOiJkUFVMMVhMa1NUTmpkZ3J3Iiwic3ViIjoiYmRmYzJiMzYtOTNlZS00NTY1LTk2ZjYtZDVjZTFhMTRlNTI2IiwicHJ2IjoiYzAxMGM4OGUxMWY0MWM0Njc5YTNmMzVlMmQwYWQ3YTVlOWFiOWNkMCJ9.biV65aaiUeOnY21z-nV4577xF7F4oyRkaDgl-I59QvA",
  "token_type": "bearer",
  "expires_in": 3600
}
```


```response:401
{
  "error": "Identificação ou Senha Inválidos"
}
```


```response:404
{
  "error": "Informe a identificação(CNPJ ou CNS) e o passe(senha)"
}
```


```response:403
{
  "error": "Cartório ou Empresa não cadastrado em nossa base de dados"
}
```

