---
title: Erros
---

A Cartórios Tocantins utiliza os códigos de estado HTTP para responder às requisições e identificar erros. Os códigos 2xx indicam sucesso, os 4xx algum erro causado pela aplicação consumidora e os 5xx algum erro interno da API. Mais detalhes dos códigos podem ser encontrados no [Wikipédia](https://pt.wikipedia.org/wiki/Lista_de_c%C3%B3digos_de_estado_HTTP). 

Os erros mais comuns são mostrados nos exemplos abaixo.

```response:400
{
    "mensagem": "Dados inválidos na requisição."
}
```

```response:401
{
    "mensagem": "Acesso não autorizado."
}
```

```response:404
{
    "mensagem": "Não encontrado."
}
```

```response:500
{
    "mensagem": "Ocorreu um erro no servidor."
}
```