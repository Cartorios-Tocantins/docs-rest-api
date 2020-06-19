---
title: Endpoint Busca de Cartório
method: GET
url: "{{API_URL}}/api/cartorios/123456"
---


Via API, o sistema do cliente deve poder consultar a lista de cartórios habilitados e as informações do cartório.Passar o CNS como parâmetro na URL. 

Exemplo: Via API, um sistema de empresa deve poder consultar os cartórios cadastrados e habilitados pelo CT. 


Encontra um cartório pelo seu CNS (só números) e retorna os dados dos cartórios: CNS, Denominação, e Serviços Prestados.


```request:cURL
curl --location --request GET '{{API_URL}}/cartorios/123456' \
--header 'Content-Type: application/json' 
```

```request:Python
import requests

url = "{{API_URL}}/cartorios/123456"

headers = {
  'Content-Type': 'application/json'
}

response = requests.request("GET", url, headers=headers)

print(response.text.encode('utf8'))
```


```response:200
{
  "id": "fa1af393-b577-40e5-a087-4b6b589c4d08",
  "cns": "123456",
  "title": "NOME DO CARTÓRIO",
  "services": []
}
```


```response:401
{
  "error": "Identificação ou Senha inválidos"
}
```