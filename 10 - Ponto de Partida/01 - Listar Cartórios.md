---
method: GET
url: "{{API_URL}}cartorios"
---

##### Listar Cartórios Habilitados

O presente método descrever como verificar quais cartórios estão habilitdos para prestar serviços on-line.

O método é público e não existem parâmetros, a resposta contém a lista de cartórios habilitados.

```request:curl
curl -X GET "{{API_URL}}cartorios" 
    -H "accept: */*" 
    -H "X-CSRF-TOKEN: "
```

```response:200
[
  {
    "nome": "Cartório Teste",
    "nome_fantasia": "CARTORIO TESTE",
    "endereco": "teste",
    "telefone": "(63) 1234-5678",
    "email": "teste@anoregto.com.br",
    "site": "",
    "cnpj": "00.000.000/0000-00",
    "cns": "22.222-2",
    "url_producao": "http://127.0.0.1:8001/",
    "url_sandbox": "http://127.0.0.1:8001/"
  }
]
```