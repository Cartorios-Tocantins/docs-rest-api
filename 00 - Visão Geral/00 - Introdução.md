---
title: Introdução
---

A Cartórios Tocantins disponibiliza uma API de comunicação web, no padrão REST, implementando os padrões de Pedidos Eletrônicos Estruturados para Registro - PEER Simplificado. Essa especificação é desenvolvida pela [Registro de Imóveis do Brasil](https://www.registrodeimoveis.org.br/orientacoes). 

As trocas de dados estruturados serão feitas no formato XML e JSON e os envios de arquivo usando a tecnologia de Multipart Form-Data. O controle de alterações (i.e., *Changelog*) da documentação poderá ser acompanhado por meio de repositório público no [Github](https://github.com/anoregto/docs-rest-api). Sugestões de melhorias ou dúvidas podem ser tiradas por lá por meio da ferramenta de *Issues*, além dos canais tradicionais de atendimento da Cartórios Tocantins.

O endereço para comsumo da API da Cartórios Tocantins é `{{API_URL}}`. As versões estáveis da API serão agrupadas em diretórios ao fim do endereço de acordo com as *Tags* disponibilizadas no Github.

Para consumir as APIs de comunicação direta com os cartórios, deve ser substituída a URL `{{CARTORIO_URL}}` pela respectiva URL do cartório.

No menu lateral esquerdo se encontram os métodos da API. Ao selecionar um método, a sua descrição e parâmetros serão exibidos na coluna central. À diretia, exemplos de códigos para chamada dos métodos e respostas esperadas são apresentados.