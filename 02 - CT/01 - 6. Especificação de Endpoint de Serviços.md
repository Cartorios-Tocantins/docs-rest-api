# Especificação de Endpoint de Serviços - 6

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
| GET | `/api/servicos` |

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
    "current_page": 1,
    "data": [
        {
            "id": "00bcdc33-78c4-4107-99ba-03ccf0f483c5",
            "type": "EXTRA_NOTARIAL_REGISTRAL",
            "title": "Serviço 25O0",
            "slug": "servico-25o0",
            "description": null,
            "amount": "2.00",
            "amount_funcivil": "2.00",
            "amount_funjuris": "1.00",
            "amount_fse": "1.00",
            "office": {
                "id": "4b4eeb43-cd70-483c-b8a0-033e6bd210b8",
                "cns": "126433",
                "title": "1º TABELIONATO DE NOTAS"
            }
        },
        {
            "id": "20c5fdcb-35d4-4a7e-8fed-65da4e7a801d",
            "type": "NOTARIAL_REGISTRAL",
            "title": "Serviço SWMr",
            "slug": "servico-swmr",
            "description": null,
            "amount": "3.00",
            "amount_funcivil": "1.00",
            "amount_funjuris": "1.00",
            "amount_fse": "2.00",
            "office": {
                "id": "13c130ac-9f9c-4d18-98cf-a6b46b572e93",
                "cns": "127035",
                "title": "CARTÓRIO DE REGISTRO CIVIL DE PESSOAS JURÍDICAS, TÍTULOS E DOCUMENTOS E TABELIONATO DE PROTESTOS DA COMARCA DE PALMAS-TO"
            }
        },
        {
            "id": "709cee94-5ad6-4592-b69d-e19c94c6bcbb",
            "type": "NOTARIAL_REGISTRAL",
            "title": "Serviço JORr",
            "slug": "servico-jorr",
            "description": null,
            "amount": "2.00",
            "amount_funcivil": "1.00",
            "amount_funjuris": "1.00",
            "amount_fse": "1.00",
            "office": {
                "id": "553f349e-7ea8-4b17-88fc-4fe6387feeb7",
                "cns": "126706",
                "title": "Cartorio de Registro Civil"
            }
        },
        {
            "id": "7d151f74-013b-4a21-89d3-6b1193aa3330",
            "type": "NOTARIAL_REGISTRAL",
            "title": "Serviço sFuA",
            "slug": "servico-sfua",
            "description": null,
            "amount": "3.00",
            "amount_funcivil": "2.00",
            "amount_funjuris": "1.00",
            "amount_fse": "1.00",
            "office": {
                "id": "1d0ad1d1-43f7-4e1b-a1f8-8dc9ffd41e01",
                "cns": "126987",
                "title": "CARTÓRIO DE REGISTRO CIVIL DAS PESSOAS NATURAIS E TABELIONATO DE NOTAS"
            }
        },
        {
            "id": "ae4c3190-dfc9-44dd-9b7e-d601bbcd146a",
            "type": "NOTARIAL_REGISTRAL",
            "title": "Serviço 4cWx",
            "slug": "servico-4cwx",
            "description": null,
            "amount": "2.00",
            "amount_funcivil": "2.00",
            "amount_funjuris": "2.00",
            "amount_fse": "1.00",
            "office": {
                "id": "57f5b46c-677a-41e3-b548-26174ee3a7d4",
                "cns": "126466",
                "title": "2. TABELIONATO DE NOTAS DE PALMAS"
            }
        },
        {
            "id": "edad1c39-510a-4a07-821a-ba0e33a16c8a",
            "type": "NOTARIAL_REGISTRAL",
            "title": "Serviço oHB5",
            "slug": "servico-ohb5",
            "description": null,
            "amount": "2.00",
            "amount_funcivil": "2.00",
            "amount_funjuris": "1.00",
            "amount_fse": "2.00",
            "office": {
                "id": "0fa18048-7883-4228-a8c5-3d599178d133",
                "cns": "127613",
                "title": "CARTORIO DE REGISTRO DE IMOVEIS DA COMARCA DE PALMAS-TO"
            }
        }
    ],
    "first_page_url": "http://127.0.0.1:8000/api/servicos?page=1",
    "from": 1,
    "last_page": 1,
    "last_page_url": "http://127.0.0.1:8000/api/servicos?page=1",
    "next_page_url": null,
    "path": "http://127.0.0.1:8000/api/servicos",
    "per_page": 10,
    "prev_page_url": null,
    "to": 6,
    "total": 6
}
```
