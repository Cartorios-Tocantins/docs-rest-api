---
title: Bancos - Criar
method: POST
url: "{{CARTORIO_URL}}:cns/bancos/contratos-eletronicos"
---

O presente método descrever a criação do Contrato Eletrônico Estruturado para Registro atendendo os seguintes negócios:

- Compra e Venda
- Compra e Venda e Alienação Fiduciária
- Alienação Fiduciária
- Alienação Fiduciária com CCI ou CCB
- Hipotéca com CCI ou CCB
- Convenio de Limite de Crédito com Alienação Fiduciária
- Portabilidade [LEI Nº 13.476, DE 28 DE AGOSTO DE 2017](http://www.planalto.gov.br/ccivil_03/_Ato2015-2018/2017/Lei/L13476.htm)
- CCI ou CCB
- Aditamento de Cédula
- Doação

Mais detalhes podem ser encontradas na [Documentação Completa em PDF](static/EspecificacaoTecnica_PEERSimplificado_Banco.pdf). Além disso, existem exemplos em [XML](static/ESTRUTURA_BANCO.xml) dos dados estruturados e o respectivo arquivo [XSD](static/ESTRUTURA_BANCO.xsd).

| **Parâmetros de URL** |                                            |
|-----------------------|--------------------------------------------|
| cns `int`             | O código CNS do cartório.                  |


| **Parâmetros**                                      |                                                                                                         |
|-----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
|   CONTRATOS `list`                                  | Lista de contratos.                                                                                     |
|   CONTRATOS.VERSAO `string`                         | Campo para identificação do modelo XML – PARA BANCOS VALOR “3.1.0”.                                     |
|   CONTRATOS.CONTRATO `object`                       | Um contrato com seus respectivos dados.                                                                 |
|   CONTRATOS.CONTRATO.CNS `int`                      | Número do CNS                                                                                           |
|   CONTRATOS.CONTRATO.EMPREENDIMENTO `object`        | Empreendimento – esse campo será utilizado pela ARISP, para gerar o BOLETO separado por empreendimento. |
|   CONTRATOS.CONTRATO.EMPREENDIMENTO.CODIGO `int`    | Código do empreendimento – usado para agrupamento para geração do boleto                                |
|   CONTRATOS.CONTRATO.EMPREENDIMENTO.NOME `string`   | Nome do empreendimento                                                                                  |
|   CONTRATOS.CONTRATO.NATUREZA `int`                 | Campo para identificação da natureza do título. Pode assumir os valores:                                |
|                                                     | 1 - instrumento particular com força de escritura pública                                               |
|                                                     | 2 - cédula de crédito imobiliário                                                                       |
|                                                     | 3 - cédula de crédito bancário                                                                          |

```request:cURL
curl --location --request POST \
    --url '{{CARTORIO_URL}}:cns/bancos/contratos-eletronicos' \
    --header 'Content-Type: application/xml' 
```

```request:Python
import requests
url = "{{CARTORIO_URL}}:cns/bancos/contratos-eletronicos"
headers = {
  'Content-Type': 'application/xml'
}
response = requests.request("POST", url, headers=headers)
print(response.text.encode('utf8'))
```

```response:200
```