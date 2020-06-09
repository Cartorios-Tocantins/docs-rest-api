# Me - Retorna Dados do Usuário - 

---

- [URI](#uri)
- [Header](#header)
- [URL Params](#params)
- [Body](#body)
- [Response](#response)

<a name="uri"></a>
## URI

| Method | URI | 
| : |   :-   |
| GET | `/api/me` |

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
  "id": "bdfc2b36-93ee-4565-96f6-d5ce1a14e526",
  "name": "Fulano da Silva",
  "cpf": "000.000.000-00",
  "email": "email@gmail.com",
  "cargo": "Cargo",
  "lotacao": "Lotação"
}
```