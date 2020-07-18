---
method: GET
url: "{{API_URL}}pagamento/{hash}"
---

##### Efetuar pagamento de solicitação de serviço

O presente método descrever como efetuar o pagamento de uma solicitação de serviço.

```request:curl
curl -X GET "https://servicos.cartoriostocantins.com.br/api/pagamento/E63cd...." 
    -H "accept: */*" -H "Authorization: Bearer eyJ0e...." 
    -H "X-CSRF-TOKEN: "
```

```response:200
{
  "sucesso": true,
  "status": "pendente",
  "vencimento": "2020-07-15",
  "url_pagamento": "http://pagamentos.cartoriostocantins.com.br/pagamento/27181b05....",
  "total": 135.50,
  "created_at": "2020-07-14T14:48:29-03:00",
  "updated_at": "2020-07-14T14:48:29-03:00",
  "logs": [
    {
      "id": "99DF2....",
      "description": "Evento enviado para URL de notificação",
      "notes": "O seguinte evento foi enviado para a URL: invoice.created > http://pagamentos.cartoriostocantins.com.br/api/pagamento-retorno/f82cd1c7....",
      "created_at": "14/07, 14:48"
    },
    {
      "id": "077F83....",
      "description": "Fatura criada com sucesso!",
      "notes": "Fatura criada!",
      "created_at": "14/07, 14:48"
    }
  ]
}
```