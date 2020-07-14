---
method: POST
title: Registro e Autenticação
url: "{{API_URL}}autenticacao"
---

A autenticação nas APIs da Cartórios Tocantins é realizada no formato JSON Web Token (JWT). Para obter o token e utilizar o método de autenticação abaixo descrito. É necessário obter autorização prévia da Cartórios Tocantins mediante cadastro e aprovação na plataforma online. Essa autorização será garantida juntamente com as informações de acesso para obteção do Token.

```request:Python
import requests

url = "{{API_URL}}autenticacao"
headers = {
    'Content-Type': 'application/json'
}

credenciais = {
    "identificacao": "",
    "passe": ""
}

response = requests.post(url, data=credenciais, headers=headers)
print(response.text.encode('utf8'))
```

```response:200
{
  "token_acesso": "eyJ0eX...."
}
```

```response:401
{
  "erro": "Identificação ou passe inválido."
}
```
