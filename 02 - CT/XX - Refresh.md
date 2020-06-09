# Refresh - 

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
| GET | `/api/refresh` |

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
  "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC94cHRvLmxvY2FsaG9zdFwvYXBpXC9hdXRlbnRpY2FjYW8iLCJpYXQiOjE1OTA0NjI4NjEsImV4cCI6MTU5MDQ2NjQ2MSwibmJmIjoxNTkwNDYyODYxLCJqdGkiOiJkUFVMMVhMa1NUTmpkZ3J3Iiwic3ViIjoiYmRmYzJiMzYtOTNlZS00NTY1LTk2ZjYtZDVjZTFhMTRlNTI2IiwicHJ2IjoiYzAxMGM4OGUxMWY0MWM0Njc5YTNmMzVlMmQwYWQ3YTVlOWFiOWNkMCJ9.biV65aaiUeOnY21z-nV4577xF7F4oyRkaDgl-I59QvA",
  "token_type": "bearer",
  "expires_in": 3600
}
```