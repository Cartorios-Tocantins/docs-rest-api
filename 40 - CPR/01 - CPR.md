---
method: POST
url: "{{CARTORIO_URL}}cpr/{hash}"
---

##### Solicitar Cédula de Produto Rural

O presente método descreve como solicitar o serviço de emissão de Cédula de Produto Rural para um cartório.

| **Parâmetros de URL**                                             |
|-------------------------------------------------------------------|
| **hash** `string` *Hash de acompanhamento registrado na central.* |

| **Parâmetros**                                                                                                                                    |
|---------------------------------------------------------------------------------------------------------------------------------------------------|
| **cedulas** `list` *Lista de cédulas a serem emitidas.*                                                                                           |
| **cedulas[\*].credor** `object` *Credor da cédula.*                                                                                               |
| **cedulas[\*].credor.nome** `string` *Nome ou Razão Social do credor.*                                                                            |
| **cedulas[\*].credor.cpf_cnpj** `string` *CPF ou CNPJ do credor contendo apenas números.*                                                         |
| **cedulas[\*].codigo_do_contrato** `string` *Código do contrato referente à cédula.*                                                              |
| **cedulas[\*].natureza_do_titulo** `string` *Natureza do título.*                                                                                 |
| **cedulas[\*].data** `string` *Data da cédula no formato `YYYY-MM-DD`.*                                                                           |
| **cedulas[\*].cidade** `string` *Código IBGE do município do imóvel contendo apena números.*                                                      |
| **cedulas[\*].vencimento_final** `string` *Data de vencimento no formato `YYYY-MM-DD`.*                                                           |
| **cedulas[\*].valor_total** `string` *Valor total da cédula no formato `^[0-9]+\.[0-9]{2}$`.*                                                     |
| **cedulas[\*].devedores** `list` *Lista de devedores.*                                                                                            |
| **cedulas[\*].devedores[\*].nome** `string` *Nome ou Razão Social do devedor.*                                                                    |
| **cedulas[\*].devedores[\*].cpf_cnpj** `string` *CPF ou CNPJ do devedor contendo apenas números.*                                                 |
| **cedulas[\*].avalistas** `list` *Lista de avalistas.*                                                                                            |
| **cedulas[\*].avalistas[\*].nome** `string` *Nome ou Razão Social do avalista.*                                                                   |
| **cedulas[\*].avalistas[\*].cpf_cnpj** `string` *CPF ou CNPJ do avalista contendo apenas números.*                                                | 
| **cedulas[\*].garantias** `list` *Lista de garantias da cédula.*                                                                                  |
| **cedulas[\*].garantias[\*].tipo_de_garantia** `int` *Código do tipo de garantia que pode assumir os valores:<br> 4 - Alienação Fiduciária, ....* |
| **cedulas[\*].garantias[\*].grau_da_garantia** `int` *Grau da garantia.*                                                                          |
| **cedulas[\*].garantias[\*].tipo_do_bem** `int` *Código do tipo do bem, que pode assumir os valores: <br> 3 - Imóvel rural, ....*                 |
| **cedulas[\*].garantias[\*].registro** `object` *Dados do registro do bem.*                                                                       |
| **cedulas[\*].garantias[\*].registro.numero** `string` *Número do registro.*                                                                      |
| **cedulas[\*].garantias[\*].registro.cns** `string` *CNS do cartório do registro contendo apenas números.*                                        |
| **cedulas[\*].garantias[\*].registro.data_registro** `string` *Data do registro do bem no formato `YYYY-MM-DD`.*                                  |
| **cedulas[\*].garantias[\*].registro.matricula** `string` *Número de matrícula do bem.*                                                           |
| **cedulas[\*].garantias[\*].visualizacoes** `list` *Documentos a serem vizualizados.*                                                             |
| **cedulas[\*].garantias[\*].visualizacoes[\*].livro_folha** `string` *Número do livro e folha.*                                                   |
| **cedulas[\*].garantias[\*].visualizacoes[\*].arquivo** `string` *Link para o arquivo.*                                                           |
| **cedulas[\*].garantias[\*].status** `string` *Status da garantia.*                                                                               |


**Exemplo de JSON:**

```json
{
    "data_hora": "",
    "total_cedulas": "",
    "cedulas": [{
        "credor": {
            "nome": "Banco do Brasil S A",
            "cpf_cnpj": "00.000.000/0000-00"
        },
        "codigo_do_contrato": "00/00000-0",
        "natureza_do_titulo": "Nota de Crédito Rural",
        "data": "2020-02-10",
        "cidade": "0000",
        "vencimento_final": "2021-01-14",
        "valor_total": "100.000,00",
        "devedor": [{
            "nome": "Fulano da Silva",
            "cpf_cnpj": "12312312387"
        }],
        "avalista": [{
            "nome": "Fulano da Silva",
            "cpf_cnpj": "12312312387"
        }],
        "garantias": [{
            "tipo_de_garantia": 4,
            "grau_da_garantia": 1,
            "tipo_do_bem": 3,
            "registro": {
                "numero": "000000.0.00000",
                "cartorio": {
                    "cns": "222222",
                    "nome": "Cartório de Testes do Tocantins"
                },
                "data_do_registro": "2011-09-29",
                "matricula": "00000.0.0000"
            },
            "visualizacao": [{
                "livro_folha": "A-3",
                "arquivo": "https://....."
            }],
            "status": "Em Vigor"
        }]
    }]
}
```

```request:curl
curl -X POST "{{CARTORIO_URL}}cpr/LfLT52...." 
    -H "accept: */*" 
    -H "Content-Type: application/json" 
    -H "X-CSRF-TOKEN: " 
    -d "{.....}"
```

```response:200
{
  "situacao": "sucesso"
}
```