---
method: GET
url: "{{API_URL}}taxas/{hash}"
---

##### Visualizar tarifas para orçamento

O presente método descrever como solicitar o hash de acompanhamento do serviço. Por meio desse hash é possível realizar a comunicação com o cartório.

```request:curl
curl -X GET "{{API_URL}}taxas/E63cd.....?valor=123.45" 
    -H "accept: */*" 
    -H "Authorization: Bearer eyJ0e...." 
    -H "X-CSRF-TOKEN: "
```

```response:200
{
  "infraestrutura_pagamento": "2.00",
  "protocolo_eletronico": "100.00"
}
```