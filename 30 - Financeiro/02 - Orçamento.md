---
method: GET
url: "{{CARTORIO_URL}}orcamento/{hash}"
---

##### Visualizar orçamento de solicitação de serviço

O presente método descrever como visualizar o orçamento de uma solicitação de serviço.

```request:curl
curl -X POST "{{CARTORIO_URL}}orcamento/E63cd...." 
    -H "accept: application/json" 
```

```response:200
{
  "url_retorno": "{{CARTORIO_URL}}/webhook/wjnfdi....",
  "orcamentos": [
    {
      "solicitante": {
        "cpf_cnpj": "12312312387",
        "nome": "Fulano da Silva",
        "ddd": 63,
        "telefone": "123451234",
        "email": "exemplo@cartoriostocantins.com.br",
        "endereco": {
            "cep": "77000000",
            "rua": "Av. JK",
            "numero": "0",
            "bairro": "centro",
            "cidade": "Palmas",
            "uf": "TO",
            "pais": "Brasil",
            "complemento": "Casa"
        }
      },
      "valor_total": "130.50",
      "aliquota_iss": 5,
      "itens": [
        {
          "tipo": "NOTARIAL_REGISTRAL",
          "descricao": "Nome do ato",
          "quantidade": 1,
          "valor_cartorio": 10,
          "valor_funcivil": 3,
          "valor_funjuris": 2.5,
          "valor_fse": 2
        }, {
          "tipo": "NOTARIAL_REGISTRAL",
          "descricao": "Nome do ato",
          "quantidade": 1,
          "valor_cartorio": 5,
          "valor_funcivil": 2,
          "valor_funjuris": 0.5,
          "valor_fse": 0
        }, {
          "tipo": "EXTRA_NOTARIAL_REGISTRAL",
          "descricao": "Xérox",
          "quantidade": 5,
          "valor_cartorio": 0.25
        }, {
          "tipo": "EXTRA_NOTARIAL_REGISTRAL",
          "descricao": "Protocolo Eletrônico",
          "quantidade": 1,
          "valor_cartorio": 100
        }, {
          "tipo": "EXTRA_NOTARIAL_REGISTRAL",
          "descricao": "Operadora de Pagamento",
          "quantidade": 1,
          "valor_cartorio": 4
        }, {
          "tipo": "EXTRA_NOTARIAL_REGISTRAL",
          "descricao": "ISS",
          "quantidade": 1,
          "valor_cartorio": 0.25
        }
      ]
    }
  ]
}
```