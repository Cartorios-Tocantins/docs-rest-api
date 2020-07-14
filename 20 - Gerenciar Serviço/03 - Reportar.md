---
method: PATCH
url: "{{API_URL}}servico/{hash}"
---

##### Reportar situação de serviço

O presente método descrever como reportar a situação final do serviço.

| **Parâmetros de URL**                    |
|------------------------------------------|
| **hash** `string` *Hash a ser validado.* |

| **Parâmetros**                                                                                               |
|--------------------------------------------------------------------------------------------------------------|
| **selos** `list` *Lista de selos gerados para execução do serviço.*                                          |
| **selos.selo** `object` *Dados do selo gerado.*                                                              |
| **selos.selo.codigo** `string` *Código do selo gerado.*                                                      |
| **selos.selo.atos** `list` *Lista de atos para cada selo.*                                                   |
| **selos.selo.atos.ato** `object` *Dados de um ato.*                                                          |
| **selos.selo.atos.ato.codigo_gise** `int` *Código do emolumento do selo.*                                    |
| **selos.selo.atos.ato.emolumentos** `string` *Valor dos emolumentos do cartório.*                            |
| **selos.selo.atos.ato.funcivil** `string` *Valor de Funcivil arrecadado paara o ato.*                        |
| **selos.selo.atos.ato.tfj** `string` *Valor de TFJ arrecadado paara o ato.*                                  |
| **selos.selo.atos.ato.fundo_eletronizacao** `string` *Valor de Fundo Eletronização arrecadado paara o ato.*  |
| **selos.selo.atos.ato.iss** `string` *Valor de ISS arrecadado paara o ato.*                                  |


```request:curl
curl -X PATCH "{{API_URL}}servico/E63cd...." 
  -H "accept: */*" 
  -H "Authorization: Bearer eyJ0e...." 
  -H "Content-Type: application/json" 
  -H "X-CSRF-TOKEN: " 
  -d "{\"selos\":[{\"codigo\":\"222222AAA000001-XXX\",\"atos\":[{\"codigo_gise\":\"12345\",\"emolumentos\":\"15.25\",\"funcivil\":\"15.25\",\"tfj\":\"15.25\",\"fundo_eletronizacao\":\"15.25\",\"iss\":\"15.25\"}]}]}"
```

```response:200
{
  "situacao": "sucesso"
}
```