---
method: POST
url: "{{CARTORIO_URL}}:/api/autenticacao"
---


##### Endpint de Autenticação - 7

Após a validação dos cadastros, os usuários poderão utilizar o Endpoint de Autenticação para logar no sistema.

• Via API: A aplicação do cliente deve poder fazer autenticação via API utilizando sua identificação CNS/CNPJ e seu hash de acesso. 

**POST /api/autenticacao**

Envio:
Enviar um identificador, que poderá ser o CNS (no caso do Cartório) ou CNPJ (no caso de Empresa)
e passe (senha).



- [URI](#uri)
- [Header](#header)
- [URL Params](#params)
- [Body](#body)
- [Response](#response)

<a name="uri"></a>
## URI

| Method | URI | 
| : |   :-   |
| POST | `/api/autenticacao` |

<a name="header"></a>
## Header

```markup 
Content-Type : application/json
```

<a name="params"></a>
## URL Params

```markup 
none
```

<a name="body"></a>
## Body

```json 
{
  "identificacao" : "000000",  // CNS ou CNPJ
  "passe": "00000"
}
```

<a name="response"></a>
## Response

> {success.fa-check-circle} Success Response

Code: `200`

Content:

```json 
{
  "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC94cHRvLmxvY2FsaG9zdFwvYXBpXC9hdXRlbnRpY2FjYW8iLCJpYXQiOjE1OTA0NjI4NjEsImV4cCI6MTU5MDQ2NjQ2MSwibmJmIjoxNTkwNDYyODYxLCJqdGkiOiJkUFVMMVhMa1NUTmpkZ3J3Iiwic3ViIjoiYmRmYzJiMzYtOTNlZS00NTY1LTk2ZjYtZDVjZTFhMTRlNTI2IiwicHJ2IjoiYzAxMGM4OGUxMWY0MWM0Njc5YTNmMzVlMmQwYWQ3YTVlOWFiOWNkMCJ9.biV65aaiUeOnY21z-nV4577xF7F4oyRkaDgl-I59QvA",
  "token_type": "bearer",
  "expires_in": 3600
}
```