---
method: POST
url: "{{API_URL}}pagamento/{hash}"
---

##### Efetuar pagamento de solicitação de serviço

O presente método descrever como efetuar o pagamento de uma solicitação de serviço.

```request:curl
curl -X POST "{{API_URL}}pagamento/E63cd...." 
    -H "accept: */*" 
    -H "Authorization: Bearer eyJ0e...." 
    -H "X-CSRF-TOKEN: " 
    -d ""
```

```response:200
{
  "sucesso": true,
  "id": "27181b05.....",
  "url": "http://pagamentos.cartoriostocantins.com.br/pagamento/27181b05....."
}
```