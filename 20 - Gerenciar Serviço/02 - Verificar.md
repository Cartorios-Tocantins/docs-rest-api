---
method: GET
url: "{{API_URL}}servico/{hash}"
---

##### Verificar HASH de serviço

O presente método descrever como validar o hash de acompanhamento do serviço.

| **Parâmetros de URL**                    |
|------------------------------------------|
| **hash** `string` *Hash a ser validado.* |


```request:curl
curl -X GET "{{API_URL}}servico/E63cd...." 
    -H "accept: */*" 
    -H "Authorization: Bearer eyJ0e...." 
    -H "X-CSRF-TOKEN: "
```

```response:200
{
  "status": 1,
  "nome_fantasia": "Empresa Teste",
  "cnpj": "00000000000000"
}
```