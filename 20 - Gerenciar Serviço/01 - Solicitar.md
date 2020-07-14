---
method: POST
url: "{{API_URL}}servico"
---

##### Solicitar HASH de serviço

O presente método descrever como solicitar o hash de acompanhamento do serviço. Por meio desse hash é possível realizar a comunicação com o cartório.

```request:curl
curl -X POST "{{API_URL}}servico/" 
    -H "accept: */*" 
    -H "Authorization: Bearer eyJ0e...." 
    -H "Content-Type: application/json" 
    -H "X-CSRF-TOKEN: " 
    -d "{\"cns\":\"222222\"}"
```

```response:200
{
  "hash": "LfLT52...."
}
```