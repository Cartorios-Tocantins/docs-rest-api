---
method: POST
url: "{{CARTORIO_URL}}bancos/titulo"
---

##### Contratos Eletrônicos

O presente método descrever a solicitação de Contrato Eletrônico Estruturado para Registro dos bancos, atendendo os seguintes negócios:

- Compra e venda
- Compra e venda e alienação fiduciária
- Alienação fiduciária
- Alienação fiduciária com CCI ou CCB
- Hipoteca com CCI e CCB
- Convenio de Limite de Crédito com Alienação Fiduciária [LEI Nº 13.476, DE 28 DE AGOSTO DE 2017](http://www.planalto.gov.br/ccivil_03/_Ato2015-2018/2017/Lei/L13476.htm)
- CCI ou CCB

Mais detalhes podem ser encontradas na [Documentação Completa em PDF](static/EspecificacaoTecnica_PEERSimplificado_TN.pdf). Além disso, existem exemplos em [XML](static/ESTRUTURA_TABELIAO.xml) dos dados estruturados e o respectivo arquivo [XSD](static/ESTRUTURA_TABELIAO.xsd).

```request:Python
import requests

url = "{{CARTORIO_URL}}bancos/titulo"
headers = {
    'Authorization': 'Bearer: {JWT Token Here}'
    'Content-Type': 'application/xml'
}

xml = """
<?xml version="1.0" encoding="UTF-8"?>
<TITULO>
    <VERSAO></VERSAO>
    <CNS></CNS>
    <NATUREZA></NATUREZA>
    <DATAINSTRUMENTO></DATAINSTRUMENTO>
    <LIVRO></LIVRO>
    <FOLHA></FOLHA>
    <LOCAL></LOCAL>
    <APRESENTANTE>
        <NOME></NOME>
        <CPFCNPJ></CPFCNPJ>
        <CEP></CEP>
        <TIPOLOGRADOURO></TIPOLOGRADOURO>
        <LOGRADOURO></LOGRADOURO>
        <NUMERO></NUMERO>
        <UNIDADE></UNIDADE>
        <BAIRRO></BAIRRO>
        <CIDADE></CIDADE>
        <UF></UF>
        <CONTATO>
            <EMAIL></EMAIL>
            <DDD></DDD>
            <TELEFONE></TELEFONE>
        </CONTATO>
    </APRESENTANTE>
    <NEGOCIOS>
        <NEGOCIO>
            <SEQUENCIAL></SEQUENCIAL>
            <TIPOATO></TIPOATO>
            <VALORTRANSMISSAO></VALORTRANSMISSAO>
            <VALORVENAL></VALORVENAL>
            <VALORFINANCIAMENTO></VALORFINANCIAMENTO>
            <VALORAVALIACAO></VALORAVALIACAO>
            <VALORLEILAO></VALORLEILAO>
            <RECURSOSPROPRIOS></RECURSOSPROPRIOS>
            <RECURSOSFINANCIADO></RECURSOSFINANCIADO>
            <PRIMEIRAAQUISICAO></PRIMEIRAAQUISICAO>
            <OBSERVACOESGERAIS></OBSERVACOESGERAIS>
            <IMOVEL>
                <CNS></CNS>
                <LOCALIZACAO></LOCALIZACAO>
                <NUMEROREGISTRO></NUMEROREGISTRO>
                <IPTU></IPTU>
                <CCIR></CCIR>
                <NIRF></NIRF>
                <LIVRO></LIVRO>
                <TIPOIMOVEL></TIPOIMOVEL>
                <TIPOLOGRADOURO></TIPOLOGRADOURO>
                <LOGRADOURO></LOGRADOURO>
                <NUMERO></NUMERO>
                <UNIDADE></UNIDADE>
                <BAIRRO></BAIRRO>
                <CIDADE></CIDADE>
                <UF></UF>               
                <LOTE></LOTE>
                <QUADRA></QUADRA>
                <TORRE></TORRE>
                <NOMELOTEAMENTO></NOMELOTEAMENTO>
                <NOMECONDOMINIO></NOMECONDOMINIO>
                <COMPLEMENTO></COMPLEMENTO>
            </IMOVEL>
            <PARTES>
                <PARTE>
                    <CPFCNPJ></CPFCNPJ>
                    <QUALIFICACAO></QUALIFICACAO>
                    <FRACAO/>
                </PARTE>
            </PARTES>
        </NEGOCIO>
    </NEGOCIOS>
    <PARTESNEGOCIO>
        <PARTES>
            <SEQUENCIALNEGOCIO></SEQUENCIALNEGOCIO>
            <NOME></NOME>
            <CPFCNPJ></CPFCNPJ>
            <DOCUMENTO></DOCUMENTO>
            <ORGAOEMISSOR></ORGAOEMISSOR>
            <NACIONALIDADE></NACIONALIDADE>
            <ESTADOCIVIL></ESTADOCIVIL>
            <REGIMEBENS></REGIMEBENS>
            <DTCASAMENTO></DTCASAMENTO>
            <DTNASCIMENTO></DTNASCIMENTO>
            <NRPACTO></NRPACTO>
            <DTPACTO></DTPACTO>
            <LOCALREGISTROPACTO></LOCALREGISTROPACTO>
            <UNIAOESTAVEL></UNIAOESTAVEL>
            <PROFISSAO></PROFISSAO>
            <CEP></CEP>
            <TIPOLOGRADOURO></TIPOLOGRADOURO>
            <LOGRADOURO></LOGRADOURO>
            <NUMERO></NUMERO>
            <UNIDADE></UNIDADE>
            <BAIRRO></BAIRRO>
            <CIDADE></CIDADE>
            <UF></UF>
            <CPFCONJUGE></CPFCONJUGE>
            <EMAIL></EMAIL>
            <FILIACAO1></FILIACAO1>
            <FILIACAO2></FILIACAO2>
        </PARTES>
    </PARTESNEGOCIO>
    <FINANCIAMENTO>
        <DADOS>
            <PRAZOCARENCIA></PRAZOCARENCIA>
            <ENQUADRAMENTOFINANCIAMENTO></ENQUADRAMENTOFINANCIAMENTO>
            <SISTEMAAMORTIZACAO></SISTEMAAMORTIZACAO>
            <ORIGEMRECURSOS></ORIGEMRECURSOS>
            <JUROSANUALNOMINAL></JUROSANUALNOMINAL>
            <JUROSANUALEFETIVO></JUROSANUALEFETIVO>
            <JUROSMENSALNOMINAL></JUROSMENSALNOMINAL>
            <JUROSMENSALEFETIVO></JUROSMENSALEFETIVO>
            <PRAZOAMORTIZACAO></PRAZOAMORTIZACAO>
            <VLPRIMEIRAPARCELA></VLPRIMEIRAPARCELA>
            <DTPRIMEIRAPARCELA></DTPRIMEIRAPARCELA>
            <DESTFINANCIAMENTO></DESTFINANCIAMENTO>
            <FORMADEPAGAMENTO></FORMADEPAGAMENTO>
        </DADOS>
    </FINANCIAMENTO>
    <CEDULA>
        <!-- se tiver cedula -->
        <TIPOCEDULA></TIPOCEDULA>
        <!-- cci ou ccb-->
        <TIPO></TIPO>
        <NUMERO></NUMERO>
        <FRACAO></FRACAO>
        <SERIE></SERIE>
        <ESPECIE></ESPECIE>
        <CUSTODIANTE_EMISSOR></CUSTODIANTE_EMISSOR>
    </CEDULA>   
    <REPRESENTANTES>
        <REPRESENTANTE>
            <INSTRUMENTO>
                <NOME_REPRESENTANTE></NOME_REPRESENTANTE>
                <REPRESENTANTE></REPRESENTANTE>
                <REPRESENTADO></REPRESENTADO>
                <NUMERO></NUMERO>
                <TIPOREGISTRO></TIPOREGISTRO>
                <ORGAO></ORGAO>
                <FORMAREGISTRO></FORMAREGISTRO>
                <NUMEROLIVRO></NUMEROLIVRO>
                <FOLHA></FOLHA>
                <NUMEROREGISTRO></NUMEROREGISTRO>
                <DATAREGISTRO></DATAREGISTRO>
            </INSTRUMENTO>
        </REPRESENTANTE>    
    </REPRESENTANTES>
    <IMPOSTOS>
        <IMPOSTOTRANSMISSAO> 
            <ISENCAO></ISENCAO>
            <INSCRICAO></INSCRICAO>
            <GUIA></GUIA>
            <VALOR></VALOR>
        </IMPOSTOTRANSMISSAO>           
        <DAJES>         
            <DAJE>
                <EMISSOR></EMISSOR>
                <SERIE></SERIE>
                <NUMERO></NUMERO>                       
                <VALOR></VALOR>
            </DAJE>                         
        </DAJES>
    </IMPOSTOS>
    <CLAUSULASDECLARACOES>
        <VERIFICACAODAPARTES>
            <VERIFICACAODAPARTE>
                <PARTE></PARTE>
                <DESCREVER></DESCREVER>
            </VERIFICACAODAPARTE>           
        </VERIFICACAODAPARTES>
        <VERIFICACAODOIMOVEIS>
            <VERIFICACAODOIMOVEL>
                <IMOVEL></IMOVEL>
                <DESCREVER></DESCREVER>
            </VERIFICACAODOIMOVEL>
        </VERIFICACAODOIMOVEIS>
    </CLAUSULASDECLARACOES>
    <AUTORIZACOES>
        <AUTORIZACAO></AUTORIZACAO>
        <DECLARACAO></DECLARACAO>
    </AUTORIZACOES>
</TITULO>
"""
response = requests.post(url, data=xml, headers=headers)
print(response.text.encode('utf8'))
```

```response:200
{
    "mensagem": "Solicitação efetuada com sucesso."
}
```

| **Parâmetros**                                                                                                                                                                                                                                                        |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **TITULO.VERSAO** `int` *Campo para identificação do modelo XML – PARA TABELIÃO  VALOR "2"*                                                                                                                                                                           |
| **TITULO.CNS** `int` *Número do CNS do cartório de notas*                                                                                                                                                                                                             |
| **TITULO.NATUREZA** `int` *Campo para identificação da natureza do título. Pode assumir os valores: <br>4 - Escritura Pública*                                                                                                                                        |
| **TITULO.DATAINSTRUMENTO** `date` *Data do instrumento. No formato `YYYY-MM-DD`.*                                                                                                                                                                                     |
| **TITULO.LIVRO** `string` *Livro do instrumento. Tamanho máximo: 10 caracteres.*                                                                                                                                                                                      |
| **TITULO.FOLHA** `string` *Folha do instrumento. Tamanho máximo: 10 caracteres.*                                                                                                                                                                                      |
| **TITULO.LOCAL** `string` *Local onde foi firmado o instrumento – Cidade / UF. Tamnho máximo: 100 caracteres.*                                                                                                                                                        |
| **TITULO.APRESENTANTE** `objetc` *Apresentante do título*                                                                                                                                                                                                             |
| **TITULO.APRESENTANTE.APRESENTANTE** `objetc` *Class APRESENTANTE*                                                                                                                                                                                                    |
| **TITULO.APRESENTANTE.APRESENTANTE.NOME** `string` *Nome do apresentante. Tamanho máximo: 500 caracteres.*                                                                                                                                                            |
| **TITULO.APRESENTANTE..APRESENTANTE.CPFCNPJ** `string` *CPF ou CNPJ do apresentante, nos formatos `XXX.XXX.XXX-XX` ou `XX.XXX.XXX/XXXX-XX` - Tamanho máximo 20 caracteres.*                                                                                           |
| **TITULO.APRESENTANTE.APRESENTANTE.CEP** `int` *CEP do apresetante - Tamanho máximo 8 dígitos.*                                                                                                                                                                       |
| **TITULO.APRESENTANTE.APRESENTANTE.TIPOLOGRADOURO** `string` *Tipo logradouro do endereço do apresentante - Tamanho máximo: 20 caracteres.*                                                                                                                           |
| **TITULO.APRESENTANTE.APRESENTANTE.LOGRADOURO** `string` *Logradouro do endereço do apresentante - Tamanho máximo 500 caracteres.*                                                                                                                                    |
| **TITULO.APRESENTANTE.APRESENTANTE.NUMERO** `string` *Número do endereço do apresentante - Tamanho máximo 10 caracteres.*                                                                                                                                             |
| **TITULO.APRESENTANTE.APRESENTANTE.UNIDADE** `sting` *Unidade do endereço do apresentante  - Tamanho máximo 10 caracteres.*                                                                                                                                           |
| **TITULO.APRESENTANTE.APRESENTANTE.BAIRRO** `string` *Bairro do endereço do apresentante - Tamanho máximo 100 caracteres*                                                                                                                                             |
| **TITULO.APRESENTANTE.APRESENTANTE.CIDADE** `string` *Cidade do endereço do apresentante - Tamanho máximo 100 caracteres.*                                                                                                                                            |
| **TITULO.APRESENTANTE.APRESENTANTE.UF** `string` *UF do endereço do apresentante - Tamanho máximo 2 caracteres.*                                                                                                                                                      |
| **TITULO.APRESENTANTE.APRESENTANTE.CONTATO** `objetc` *Contato do apresentante*                                                                                                                                                                                       |
| **TITULO.APRESENTANTE.APRESENTANTE.CONTATO.CONTATO** `objetc` *Class CONTATO*                                                                                                                                                                                         |
| **TITULO.APRESENTANTE.APRESENTANTE.CONTATO.CONTATO.EMAIL** `string` *Email do Contato. Tamanho máximo: 100 caracteres.*                                                                                                                                               |
| **TITULO.APRESENTANTE.APRESENTANTE.CONTATO.CONTATO.DDD** `int` *DDD do contato - 3 dígitos.*                                                                                                                                                                          |
| **TITULO.APRESENTANTE.APRESENTANTE.CONTATO.CONTATO.TELEFONE** `int` *Telefone do Contato. Tamanho máximo: 100 caracteres.*                                                                                                                                            |
| **TITULO.NEGOCIOS** `list` *Lista de NEGOCIO*                                                                                                                                                                                                                         |
| **TITULO.NEGOCIOS.NEGOCIO** `object` *Classe Negócio*                                                                                                                                                                                                                 |
| **TITULO.NEGOCIOS.NEGOCIO.SEQUENCIAL** `int` *Sequência do negócio, para ordenar os atos e para poder vincular as partes do negócio.*                                                                                                                                 |
| **TITULO.NEGOCIOS.NEGOCIO.TIPOATO** `int` *Tipo do ato à ser praticado - Tamanho máximo 200. Pode assumir os valores: <br>1 - Venda e Compra <br>2 - Hipoteca <br>3 - Alienação Fiduciária <br>10 - Doação <br>11 - Usufruto <br>12 - Inventário <br>13 - Part. Separação/Divórcio <br>14 - Dação em pagamento <br>15 - Permuta <br>16 - Conferência de bens <br>17 - Bem de família*                                                                                                                                                                                                                                         |
| **TITULO.NEGOCIOS.NEGOCIO.VALORTRANSMISSAO** `string` *Valor da transmissão do negócio. Monetário, ex.: 10518.65*                                                                                                                                                     |
| **TITULO.NEGOCIOS.NEGOCIO.VALORVENAL** `string` *Valor da venal do negócio. Monetário, ex.: 10518.65.*                                                                                                                                                                |
| **TITULO.NEGOCIOS.NEGOCIO.VALORFINANCIAMENTO** `string` *Valor do financiamento do negócio.  Monetário, ex.: 10518.65*                                                                                                                                                |
| **TITULO.NEGOCIOS.NEGOCIO.VALORAVALIACAO** `string` *Valor da avaliação do imóvel. Monetário, ex.: 10518.65*                                                                                                                                                          |
| **TITULO.NEGOCIOS.NEGOCIO.VALORLEILAO** `string` *Valor do leilão. Monetário, ex.: 10518.65*                                                                                                                                                                          |
| **TITULO.NEGOCIOS.NEGOCIO.RECURSOSPROPRIOS** `string` *Valor dos recursos próprios.  Monetário, ex.: 10518.65*                                                                                                                                                        |
| **TITULO.NEGOCIOS.NEGOCIO.RECURSOSFINANCIADO** `string` *Valor dos recursos financiados. Monetário, ex.: 10518.65*                                                                                                                                                    |
| **TITULO.NEGOCIOS.NEGOCIO.PRIMEIRAAQUISICAO** `int` *Se é a primeira aquisição. Tipo Booleano, ex.: 0/1 <br>0 - Falso <br>1 - Verdadeiro*                                                                                                                                                                                                                                              |
| **TITULO.NEGOCIOS.NEGOCIO.PAGOEMESPECIE** `int` *Se foi pago em espécie ou não. Tipo Booleano, ex.: 0/1 <br>0 - Falso <br>1 - Verdadeiro*                                                                                                                                                                                                                                              |
| **TITULO.NEGOCIOS.NEGOCIO.VALORPAGOEMESPECIE** `string` *Se foi pago em espécie especificar o valor . Monetário, ex.: 10518.65*                                                                                                                                       |
| **TITULO.NEGOCIOS.NEGOCIO.OBSERVACOESGERAIS** `string` *Observação relacionada ao negócio. Campo do tipo text, onde não foi especificado o tamanho.*                                                                                                                  |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL** `list` *Lista de imóveis vinculados ao ato*                                                                                                                                                                                        |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL** `object` *Classe Imovel*                                                                                                                                                                                                    |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL.CNS** `int` *CNS – CNS do registro de imóveis*                                                                                                                                                                                |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL.LOCALIZACAO** `lint` *Lista do tipo de localização do imóvel. Serão aceitos os valores: <br>1 - Urbano <br>2 - Rural*                                                                                                                                                                                                                                                   |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL.NUMEROREGISTRO** `int` *Número de registro - Tamanho máximo 10 caracteres*                                                                                                                                                    |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL.IPTU** `string` *Número do IPTU - Tamanho máximo 20 caracteres*                                                                                                                                                               |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL.CCIR** `string` *Número do CCIR - Tamanho máximo 20 caracteres*                                                                                                                                                               |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL.NIRF** `string` *Número do NIRF- Tamanho máximo 20 caracteres*                                                                                                                                                                |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL.LIVRO** `int` *Tipo de livro referente ao número do registro. Serão aceitos os valores: <br>1 - Lv.2-Registro Geral (matrícula) <br>2 - Lv.3-Transcrição das Transmissões*                                                                                                                                                                                                                       |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL.TIPOIMOVEL** `int` *Tipo de Imóvel . Serão aceitos os valores: <br>1 - Apartamento <br>2 - Área de Terra <br>3 - Área de terras <br>4 - Armazém <br>5 - Bangalô <br>6 - Barracão <br>7 - Casa de moradia <br>8 - Chácara <br>9 - Chalé <br>10 - Cômodo comercial <br>11 - Conjunto <br>12 - Depósito <br>13 - Edícula <br>14 - Fazenda <br>15 - Galpão <br>16 - Garagem <br>17 - Gleba de terra <br>18 - Kitchenette <br>19 - Loja <br>20 - Prédio <br>21 - Prédio comercial <br>22 - Prédio p/ indústria <br>23 - Prédio residencial <br>24 - Quinhão de terra <br>25 - Rua particular <br>26 - Sala <br>27 - Saão <br>28 - Sítio <br>29 - Sobreloja <br>30 - Terreno <br>31 - Unid. res.autônoma <br>32 - Unidade Autônoma <br>33 - Unidade residencial*                                                                                                                                                                                                                                    |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL.TIPOLOGRADOURO** `string` *Tipo logradouro do endereço do imóvel - Tamanho máximo: 30 caracteres.*                                                                                                                            |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL.LOGRADOURO** `string` *Logradouro do endereço do imóvel - Tamanho máximo 500 caracteres.*                                                                                                                                     |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL.NUMERO** `string` *Número do endereço do imóvel- Tamanho máximo 10 caracteres.*                                                                                                                                               |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL.UNIDADE** `string` *Unidade do endereço do imóvel- Tamanho máximo 10 caracteres.*                                                                                                                                             |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL.BAIRRO** `string` *Bairro do endereço do imóvel - Tamanho máximo 100 caracteres*                                                                                                                                              |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL.CIDADE** `string` *Cidade do endereço do imóvel - Tamanho máximo 100 caracteres.*                                                                                                                                             |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL.UF** `string` *UF do endereço do imóvel Tamanho máximo 2 caracteres.*                                                                                                                                                         |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL.LOTE** `string` *Lote do endereço do imóvel. Tamanho máximo 10 caracteres.*                                                                                                                                                   |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL.QUADRA** `string` *Quadra do endereço do imóvel. Tamanho máximo 10 caracteres.*                                                                                                                                               |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL.TORRE** `string` *Torre do endereço do imóvel. Tamanho máximo 20 caracteres.*                                                                                                                                                 |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL.NOMELOTEAMENTO** `string` *Loteamento do endereço do imóvel. Tamanho máximo 100 caracteres.*                                                                                                                                  |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL.NOMECONDOMINIO** `string` *Condomínio do endereço do imóvel. Tamanho máximo 100 caracteres.*                                                                                                                                  |
| **TITULO.NEGOCIOS.NEGOCIO.IMOVEL.IMOVEL.COMPLEMENTO** `string` *Complemento do endereço do imóvel. Tamanho máximo 100 caracteres.*                                                                                                                                    |
| **TITULO.NEGOCIOS.NEGOCIO.PARTES** `list` *Lista de partes vinculados ao ato*                                                                                                                                                                                         |
| **TITULO.NEGOCIOS.NEGOCIO.PARTES.PARTE** `object` *Classe PARTE*                                                                                                                                                                                                      |
| **TITULO.NEGOCIOS.NEGOCIO.PARTES.PARTE.QUALIFICACAO** `string` *Qualificação da parte. Tamanho máximo: 30 caracteres.*                                                                                                                                                |
| **TITULO.NEGOCIOS.NEGOCIO.PARTES.PARTE.CPFCNPJ** `string` *CPF / CNPJ da parte, nos formatos `XXX.XXX.XXX-XX` ou `XX.XXX.XXX/XXXX-XX` - Tamanho máximo 20 caracteres.*                                                                                                |
| **TITULO.NEGOCIOS.NEGOCIO.PARTES.PARTE.FRACAO** `float` *Fração da parte. Tipo float, ex.: 3.121314*                                                                                                                                                                  |
| **TITULO.PARTESNEGOCIO** `list` *Lista de PARTES*                                                                                                                                                                                                                     |
| **TITULO.PARTESNEGOCIO.PARTES** `object` *Class PARTES*                                                                                                                                                                                                               |
| **TITULO.PARTESNEGOCIO.PARTES.SEQUENCIALNEGOCIO** `string` *Valor para vincular a TAG SEQUENCIAL do negócio ex. (1 , 2 , 4) Caso a parte participe de mais de um NEGOCIO, nesse campo deverá ser inserido os valores para vínculo.*                                   |
| **TITULO.PARTESNEGOCIO.PARTES.NOME** `string` *Nome da parte. Tamanho máximo: 500 caracteres.*                                                                                                                                                                        |
| **TITULO.PARTESNEGOCIO.PARTES.CPFCNPJ** `string` *CPF / CNPJ da parte, nos formatos `XXX.XXX.XXX-XX` ou `XX.XXX.XXX/XXXX-XX` - Tamanho máximo 20 caracteres.*                                                                                                         |
| **TITULO.PARTESNEGOCIO.PARTES.GENERO** `int` *Gênero da parte. Sendo permitido os seguintes valores: <br>1 - Masculino <br>2 - Feminino*                                                                                                                                                                                                                                                |
| **TITULO.PARTESNEGOCIO.PARTES.DOCUMENTO** `string` *Documento da parte*                                                                                                                                                                                               |
| **TITULO.PARTESNEGOCIO.PARTES.ORGAOEMISSOR** `string` *Órgão emissor do documento. Tamanho máximo: 20 caracteres.*                                                                                                                                                    |
| **TITULO.PARTESNEGOCIO.PARTES.NACIONALIDADE** `string` *Nacionalidade da parte. Tamanho máximo: 30 caracteres.*                                                                                                                                                       |
| **TITULO.PARTESNEGOCIO.PARTES.ESTADOCIVIL** `int` *Estado Civil. Pode assumir os valores: <br>1 - Casada <br>2 - Casado <br>3 - Divorciada <br>4 - Divorciado <br>5 - Espólio <br>6 - Separada <br>7 - Separada judicialmente <br>8 - Separado <br>9 - Separado judicialmente <br>10 - Solteira <br>11 - Solteira, maior <br>12 - Solteira, menor impúbere <br>13 - Solteira, menor púbere <br>14 - Solteiro <br>15 - Solteiro, maior <br>16 - Solteiro, menor impúbere <br>17 - Solteiro, menor púbere <br>18 - Viúva <br>19 - Viúvo <br>20 - Menor emancipado <br>21 - Outros*                                                                                                                                                                                                                                                 |
| **TITULO.PARTESNEGOCIO.PARTES.REGIMEBENS** `int` *Regime de bens. Pode assumir os valores: <br>1 - Comunhão de bens <br>2 - Comunhão de bens vigente na Venezuela <br>3 - Comunhão parcial de bens <br>4 - Comunhão parcial de bens às Leis da Noruega <br>5 -  Comunhão parcial de bens, à Lei Suiça <br>6 - Comunhão parcial de bens, antes da vigência da Lei 6.515/77 <br>7 - Comunhão parcial de bens, na vigência da Lei 6.515/77 <br>8 - Comunhão universal de bens <br>9 - Comunhão universal de bens, antes da vigência da Lei 6.515/77 <br>10 - Comunhão universal de bens, às Leis de Ângola <br>11 - Comunhão universal de bens, às Leis italianas <br>12 - Comunhão universal de bens, na vigência da Lei 6.515/77 <br>13 - Conforme a lei vigente em Israel <br>14 - Leis da Alemanha <br>15 - Leis da Argentina <br>16 - Leis da Austrália <br>17 - Leis da Bolívia <br>18 - Leis da China <br>19 - Leis da Colômbia <br>20 - Leis da Costa do Marfim <br>21 - Leis da Costa Rica <br>22 - Leis da Dinamarca <br>23 - Leis da Espanha <br>24 - Leis da Finlândia <br>25 - Leis da França <br>26 - Leis da Guatemala <br>27 - Leis da Holanda <br>28 - Leis da Inglaterra <br>29 - Leis da Itália <br>30 - Leis da Jordania <br>31 - Leis da Jordânia <br>32 - Leis da Polonia <br>33 - Leis da República da Coréia <br>34 - Leis da Suíça <br>35 - Leis de Angola <br>36 - Leis de Cuba <br>37 - Leis de Moscou <br>38 - Leis de Taiwan <br>39 - Leis do Canadá <br>40 - Leis do Japão <br>41 - Leis do Líbano <br>42 - Leis do Paraguai <br>43 - Leis do Uruguai <br>44 - Leis dos Estados Unidos <br>45 - Leis Egípcias <br>46 - Leis Portuguesas <br>47 - Participação final nos aquestos <br>48 - Regime de bens conforme as Leis americanas <br>49 - Regime vigente no Chile <br>50 - Separação de bens <br>51 - Separação de bens conforme as Leis da Áustria <br>52 - Separação de bens, antes da vigência da Lei 6.515/77 <br>53 - Separação de bens, na vigência da Lei 6.515/77 <br>54 - Separação obrigatória de bens <br>55 - Separação parcial, antes da vigência da Lei 6.515/77 <br>56 - Separação parcial, na vigência da Lei 6.515/77 <br>57 - Separação total de bens, na vigência da Lei 6.515/77*                                                                                                                                                                                                   |
| **TITULO.PARTESNEGOCIO.PARTES.DTCASAMENTO** `date` *Data de casamento. Formato de Data, ex.: YYYY-MM-DD.*                                                                                                                                                             |
| **TITULO.PARTESNEGOCIO.PARTES.DTNASCIMENTO** `date` *Data de nascimento. Formato de Data, ex.: YYYY-MM-DD.*                                                                                                                                                           |
| **TITULO.PARTESNEGOCIO.PARTES.NRPACTO** `string` *Número do pacto. Tamanho máximo: 20 caracteres.*                                                                                                                                                                    |
| **TITULO.PARTESNEGOCIO.PARTES.DTPACTO** `date` *Data de pacto. Formato de Data, ex.: YYYY-MM-DD.*                                                                                                                                                                     |
| **TITULO.PARTESNEGOCIO.PARTES.LOCALREGISTROPACTO** `string` *Local do registro do pacto. Tamanho máximo: 50 caracteres.*                                                                                                                                              |
| **TITULO.PARTESNEGOCIO.PARTES.UNIAOESTAVEL** `int` *União Estável. Tipo Booleano, ex.: (0) False, (1) Verdadeiro. <br>0 - False <br>1 - True*                                                                                                                                                                                                                                                    |
| **TITULO.PARTESNEGOCIO.PARTES.PROFISSAO** `string` *Profissão da parte. Tamanho máximo: 500 caracteres.*                                                                                                                                                              |
| **TITULO.PARTESNEGOCIO.PARTES.CEP** `int` *CEP do apresentante. Tamanho máximo 8 dígitos.*                                                                                                                                                                            |
| **TITULO.PARTESNEGOCIO.PARTES.TIPOLOGRADOURO** `string` *Tipo logradouro do endereço do apresentante - Tamanho máximo: 20 caracteres.*                                                                                                                                |
| **TITULO.PARTESNEGOCIO.PARTES.LOGRADOURO** `string` *Logradouro do endereço do apresentante - Tamanho máximo 500 caracteres.*                                                                                                                                         |
| **TITULO.PARTESNEGOCIO.PARTES.NUMERO** `string` *Número do endereço do apresentante - Tamanho máximo 10 caracteres.*                                                                                                                                                  |
| **TITULO.PARTESNEGOCIO.PARTES.UNIDADE** `string` *Unidade do endereço do apresentante - Tamanho máximo 10 caracteres.*                                                                                                                                                |
| **TITULO.PARTESNEGOCIO.PARTES.BAIRRO** `string` *Bairro do endereço do apresentante - Tamanho máximo 100 caracteres*                                                                                                                                                  |
| **TITULO.PARTESNEGOCIO.PARTES.CIDADE** `string` *Cidade do endereço do apresentante - Tamanho máximo 100 caracteres.*                                                                                                                                                 |
| **TITULO.PARTESNEGOCIO.PARTES.UF** `string` *UF do endereço do apresentatne Tamanho máximo 2 caracteres.*                                                                                                                                                             |
| **TITULO.PARTESNEGOCIO.PARTES.CPFCONJUGE** `string` *CPF do cônjuge , nos formatos `XXX.XXX.XXX-XX`  - Tamanho máximo 14 caracteres.*                                                                                                                                 |
| **TITULO.PARTESNEGOCIO.PARTES.EMAIL** `string` *Email da parte. Tamanho máximo: 100 caracteres.*                                                                                                                                                                      |
| **TITULO.PARTESNEGOCIO.PARTES.FILIACAO1** `string` *Nome da filiação da parte. Tamanho máximo: 200 caracteres.*                                                                                                                                                       |
| **TITULO.PARTESNEGOCIO.PARTES.FILIACAO2** `string` *Nome da filiação da parte. Tamanho máximo: 200 caracteres.*                                                                                                                                                       |
| **TITULO.FINANCIAMENTO** `object` *Dados do financiamento*                                                                                                                                                                                                            |
| **TITULO.FINANCIAMENTO.FINANCIAMENTO** `object` *Class FINANCIAMENTO*                                                                                                                                                                                                 |
| **TITULO.FINANCIAMENTO.FINANCIAMENTO.PRAZOCARENCIA** `int` *Prazo de carência*                                                                                                                                                                                        |
| **TITULO.FINANCIAMENTO.FINANCIAMENTO.ENQUADRAMENTOFINANCIAMENTO** `int` *Enquadramento do financiamento. Podendo assumir os valores: <br>1 - SFH taxa tabelada <br>2 - SFH taxa de mercado <br>3 - PMCMV <br>4 - SFI <br>5  - Outro*                                                                                                                                                                                                                                                  |
| **TITULO.FINANCIAMENTO.FINANCIAMENTO.SISTEMAAMORTIZACAO** `int` *Sistema de amortização <br>1 - SAC <br>2 - SACRE <br>3 - PRICE <br>4 - Outro <br>5 - Complementar em informações gerais*                                                                                                                                                                                                                      |
| **TITULO.FINANCIAMENTO.FINANCIAMENTO.ORIGEMRECURSOS** `int` *Origem dos recursos <br>1 - Não utiliza <br>2 - FAR <br>3 - FGTS <br>4 - FGTS/UNIÃO <br>5 - SBPE <br>6 - Privados*                                                                                                                                                                                                                                                |
| **TITULO.FINANCIAMENTO.FINANCIAMENTO.JUROSANUALNOMINAL** `float` *Juros anual nominal*                                                                                                                                                                                |
| **TITULO.FINANCIAMENTO.FINANCIAMENTO.JUROSANUALEFETIVO** `float` *Juros anual efetivo*                                                                                                                                                                                |
| **TITULO.FINANCIAMENTO.FINANCIAMENTO.JUROSMENSALNOMINAL** `float` *Juros mensal efetivo*                                                                                                                                                                              |
| **TITULO.FINANCIAMENTO.FINANCIAMENTO.JUROSMENSALEFETIVO** `float` *Juros mensal efetivo*                                                                                                                                                                              |
| **TITULO.FINANCIAMENTO.FINANCIAMENTO.PRAZOAMORTIZACAO** `int` *Prazo de amortização*                                                                                                                                                                                  |
| **TITULO.FINANCIAMENTO.FINANCIAMENTO.VLPRIMEIRAPARCELA** `string` *Valor de primeira parcela.  Monetário, ex.: 10518.65.*                                                                                                                                             |
| **TITULO.FINANCIAMENTO.FINANCIAMENTO.DTPRIMEIRAPARCELA** `date` *Data primeira parcela. Formato de Data, ex.: YYYY-MM-DD.*                                                                                                                                            |
| **TITULO.FINANCIAMENTO.FINANCIAMENTO.DESTFINANCIAMENTO** `string` *Destino do financiamento. Tamanho máximo: 50 carateres.*                                                                                                                                           |
| **TITULO.FINANCIAMENTO.FINANCIAMENTO.FORMADEPAGAMENTO** `string` *Forma de pagamento. Tamanho máximo: 200 caracteres.*                                                                                                                                                |
| **TITULO.CEDULA** `object` *Dados da cédula*                                                                                                                                                                                                                          |
| **TITULO.CEDULA.CEDULA** `object` *Class CEDULA*                                                                                                                                                                                                                      |
| **TITULO.CEDULA.CEDULA.TIPOCEDULA** `string` *Tipo da cédula. Tamanho máximo: 50 caracteres.*                                                                                                                                                                         |
| **TITULO.CEDULA.CEDULA.TIPO** `int` *Tipo. Podendo assumir os valores: <br>1 - Integral <br>2 - Fracionária*                                                                                                                                                                                                                                             |
| **TITULO.CEDULA.CEDULA.NUMERO** `string` *Número da cédula. Tamanho máximo: 20 caracteres.*                                                                                                                                                                           |
| **TITULO.CEDULA.CEDULA.FRACAO** `float` *Fração da cédula*                                                                                                                                                                                                            |
| **TITULO.CEDULA.CEDULA.SERIE** `string` *Série da cédula. Tamanho máximo: 20 caracteres.*                                                                                                                                                                             |
| **TITULO.CEDULA.CEDULA.ESPECIE** `int` *Espécie da cédula. Podendo assumir os valores: <br>1 - Cartular <br>2 - Escritural*                                                                                                                                                                                                                                              |
| **TITULO.CEDULA.CEDULA.CUSTODIANTE_EMISSOR** `string` *Custo diante emissor. Tamanho máximo: 50 caracteres.*                                                                                                                                                          |
| **TITULO.REPRESENTANTES** `object` *Lista de REPRESENTANTE*                                                                                                                                                                                                           |
| **TITULO.REPRESENTANTES.REPRESENTANTE.INSTRUMENTO** `object` *Class  REPRESENTANTE - SUBTAG: INSTRUMENTO*                                                                                                                                                             |
| **TITULO.REPRESENTANTES.REPRESENTANTE.INSTRUMENTO.NOME_REPRESENTANTE** `string` *Nome do representante. Tamanho máximo: 500 caracteres.*                                                                                                                              |
| **TITULO.REPRESENTANTES.REPRESENTANTE.INSTRUMENTO.REPRESENTANTE** `string` *CPF do representante , nos formatos `XXX.XXX.XXX-XX`  - Tamanho máximo 14 caracteres.*                                                                                                    |
| **TITULO.REPRESENTANTES.REPRESENTANTE.INSTRUMENTO.REPRESENTADO** `string` *CNPJ de quem está sendo representado, nos formatos `XX.XXX.XXX/XXXX-XX` - Tamanho máximo 20 caracteres.*                                                                                   |
| **TITULO.REPRESENTANTES.REPRESENTANTE.INSTRUMENTO.NUMERO** `string` *Número do instrumento da representação . Tamanho máximo: 20 caracteres.*                                                                                                                         |
| **TITULO.REPRESENTANTES.REPRESENTANTE.INSTRUMENTO.TIPOREGISTRO** `list` *Tipo de registro <br>1 - Contrato social <br>2 - Estatuto social <br>3 - Ata de assembleia <br>4 - Ata de reunião de sócios <br>5 - Procuração <br>6 - Outro*                                                                                                                                                                                                                                                   |
| **TITULO.REPRESENTANTES.REPRESENTANTE.INSTRUMENTO.ORGAO** `string` *Órgão. Tamanho máximo: 50 caracteres.*                                                                                                                                                            |
| **TITULO.REPRESENTANTES.REPRESENTANTE.INSTRUMENTO.FORMAREGISTRO** `string` *Forma de Registro. Tamanho máximo: 50 caracteres.*                                                                                                                                        |
| **TITULO.REPRESENTANTES.REPRESENTANTE.INSTRUMENTO.NUMEROLIVRO** `string` *Número do livro. Tamanho máximo: 10 caracteres.*                                                                                                                                            |
| **TITULO.REPRESENTANTES.REPRESENTANTE.INSTRUMENTO.FOLHA** `int` *Folha. Tamanho máximo: 10 caracteres.*                                                                                                                                                               |
| **TITULO.REPRESENTANTES.REPRESENTANTE.INSTRUMENTO.NUMEROREGISTRO** `int` *Número do registro.*                                                                                                                                                                        |
| **TITULO.REPRESENTANTES.REPRESENTANTE.INSTRUMENTO.DATAREGISTRO** `date` *Data do registro. Formato de Data, ex.: YYYY-MM-DD.*                                                                                                                                         |
| **TITULO.IMPOSTOS** `object` *Impostos ex. IMPOSTOTRANSMISSAO, DAJES*                                                                                                                                                                                                 |
| **TITULO.IMPOSTOS.IMPOSTOTRANSMISSAO** `object` *Classe IMPOSTOTRANSMISSAO*                                                                                                                                                                                           |
| **TITULO.IMPOSTOS.IMPOSTOTRANSMISSAO.ISENCAO** `int` *Se tem ou não isenção do ITBI, ITCMD . Tipo Booleano, pode assumir os valores: 0 - Falso e/ou 1 - Verdadeiro.*                                                                                                  |
| **TITULO.IMPOSTOS.IMPOSTOTRANSMISSAO.INSCRICAO** `string` *Número da inscrição. Tamanho máximo: 30 caracteres.*                                                                                                                                                       |
| **TITULO.IMPOSTOS.IMPOSTOTRANSMISSAO.GUIA** `string` *Número da guia paga / isenta. Tamanho máximo: 30 caracteres.*                                                                                                                                                   |
| **TITULO.IMPOSTOS.IMPOSTOTRANSMISSAO.VALOR** `string` *Valor pago. Monetário, ex.: 10518.65.*                                                                                                                                                                         |
| **TITULO.IMPOSTOS.DAJES** `objetc` *Class DAJE*                                                                                                                                                                                                                       |
| **TITULO.IMPOSTOS.DAJES.EMISSOR** `string` *Emissor da DAJE. Tamanho máximo: 50 caracteres.*                                                                                                                                                                          |
| **TITULO.IMPOSTOS.DAJES.SERIE** `string` *Série da DAJE. Tamanho máximo: 30 caracteres.*                                                                                                                                                                              |
| **TITULO.IMPOSTOS.DAJES.GUIA** `string` *Número da DAJE. Tamanho máximo: 30 caracteres.*                                                                                                                                                                              |
| **TITULO.IMPOSTOS.DAJES.VALOR** `string` *Valor da DAJE. Monetário, ex: 12345.67*                                                                                                                                                                                     |
| **TITULO.CLAUSULASDECLARACOES** `object` *Lista de verificação partes e imóveis*                                                                                                                                                                                      |
| **TITULO.CLAUSULASDECLARACOES.VERIFICACAODAPARTES** `int` *Lista de verificações de partes*                                                                                                                                                                           |
| **TITULO.CLAUSULASDECLARACOES.VERIFICACAODAPARTES.VERIFICACAODAPARTE** `object` *Class VERIFICACAODAPARTE*                                                                                                                                                            |
| **TITULO.CLAUSULASDECLARACOES.VERIFICACAODAPARTES.VERIFICACAODAPARTE.PARTE** `string` *CPF ou CNPJ da parte, nos formatos `XXX.XXX.XXX-XX` ou `XX.XXX.XXX/XXXX-XX` - Tamanho máximo 20 caracteres.*                                                                   |
| **TITULO.CLAUSULASDECLARACOES.VERIFICACAODAPARTES.VERIFICACAODAPARTE.DESCREVER** `string` *Descrição da verificação da parte. Campo do tipo texto, não foi definido tamanho máximo.*                                                                                  |
| **TITULO.AUTORIZACOES** `object` *Lista de AUTORIZACAO*                                                                                                                                                                                                               |
| **TITULO.AUTORIZACOES.AUTORIZACOES.DECLARO** `string` *Descrição do texto de declarações. Campo do tipo texto, não foi definido tamanho máximo.*                                                                                                                      |
| **TITULO.AUTORIZACOES.AUTORIZACOES.AUTORIZO** `string` *Descrição da verificação da parte. Campo do tipo texto, não foi definido tamanho máximo.*                                                                                                                     |