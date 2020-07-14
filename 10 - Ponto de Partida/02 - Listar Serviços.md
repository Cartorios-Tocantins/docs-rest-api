---
method: GET
url: "{{CARTORIO_URL}}servicos"
---

##### Listar Serviços Habilitados

O presente método descrever como verificar quais serviços estão disponíveis para determinado cartório.

O método é público e não existem parâmetros, a resposta contém a lista de serviços habilitados.

```request:Python
import requests

url = "{{CARTORIO_URL}}servicos"

response = requests.get(url)
print(response.text.encode('utf8'))
```

```response:200
[
  {
    "nome": "PEER Simplificado: Bancos",
    "url": "{{CARTORIO_URL}}bancos/contratos"
  }, {
    "nome": "PEER Simplificado: Tabelionato",
    "url": "{{CARTORIO_URL}}bancos/titulo"
  }, {
    "nome": "Cédula de Propriedade Rural",
    "url": "{{CARTORIO_URL}}cpr"
  }
]
```