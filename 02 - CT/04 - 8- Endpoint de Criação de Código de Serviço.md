# Endpoint de Criação de Código de Serviço - 8

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
| POST | `/api/servico` |

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

```json 
{
	"cns" : 126433
}
```

<a name="response"></a>
## Response

> {success.fa-check-circle} Success Response

Code: `200`

Content:

```json 
{
  "message": "Created successfully",
  "hash": "NJA6HXR5Ak"
}
```
