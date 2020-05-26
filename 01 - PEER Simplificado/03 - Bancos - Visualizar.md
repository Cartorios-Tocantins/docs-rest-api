---
title: Bancos - Visualizar
method: GET
url: "{{CARTORIO_URL}}:cns/bancos/contratos-eletronicos/:num_contrato"
---

O presente método descrever a leitura de um único Contrato Eletrônico Estruturado para Registro.

A resposta recebida é semelhante ao método Listar, porém com um único elemnto `CONTRATO` na lista `CONTRATOS`.

| **Parâmetros de URL** |                                            |
|-----------------------|--------------------------------------------|
| cns `int`             | O código CNS do cartório.                  |
| num_contrato `int`    | O número do contrato a ser recuperado.     |

```request:cURL
curl --location --request GET \
    --url '{{CARTORIO_URL}}:cns/bancos/contratos-eletronicos/:num_contrato' \
    --header 'Content-Type: application/xml' 
```

```request:Python
import requests
url = "{{CARTORIO_URL}}:cns/bancos/contratos-eletronicos/:num_contrato"
headers = {
  'Content-Type': 'application/xml'
}
response = requests.request("GET", url, headers=headers)
print(response.text.encode('utf8'))
```

```response:200
<?xml version="1.0" encoding="UTF-8"?>
<CONTRATOS>
    <VERSAO>3.2.0</VERSAO>  
    <CONTRATO>
        <CNS></CNS>
        <EMPREENDIMENTO> 
            <CODIGO></CODIGO>
            <NOME></NOME> 
        </EMPREENDIMENTO>
        <NATUREZA></NATUREZA>
        <DATAINSTRUMENTO></DATAINSTRUMENTO>
        <NUMCONTRATO></NUMCONTRATO>     
        <REMETENTE>
            <NOME></NOME>
            <CPFCNPJ></CPFCNPJ>
            <ENDERECO>
                <TIPOLOGRADOURO></TIPOLOGRADOURO>
                <LOGRADOURO></LOGRADOURO>
                <NUMERO></NUMERO>
                <UNIDADE></UNIDADE>
                <BAIRRO></BAIRRO>
                <CIDADE></CIDADE>
                <UF></UF>
                <CEP></CEP>
            </ENDERECO> 
            <CONTATO>
                <EMAIL></EMAIL>
                <TELEFONE>
                    <DDD></DDD>
                    <NUMERO></NUMERO>
                </TELEFONE>
            </CONTATO>
            <REPRESENTANTE>
                <NOME></NOME>
                <CPF></CPF>
            </REPRESENTANTE>
        </REMETENTE>
        <APRESENTANTE>
            <NOME></NOME>
            <CPFCNPJ></CPFCNPJ>
            <ENDERECO>
                <TIPOLOGRADOURO></TIPOLOGRADOURO>
                <LOGRADOURO></LOGRADOURO>
                <NUMERO></NUMERO>
                <UNIDADE></UNIDADE>
                <BAIRRO></BAIRRO>
                <CIDADE></CIDADE>
                <UF></UF>
                <CEP></CEP>
            </ENDERECO>
            <CONTATO>
                <EMAIL></EMAIL>
                <TELEFONE>
                    <DDD></DDD>
                    <NUMERO></NUMERO>
                </TELEFONE>
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
                <FINANCIAMENTOFAR></FINANCIAMENTOFAR>
                <SUBSIDIOS></SUBSIDIOS>
                <FGTS></FGTS>
                <OUTROSRECURSOS></OUTROSRECURSOS>
                <PRIMEIRAAQUISICAO></PRIMEIRAAQUISICAO>
                <OBSERVACOESGERAIS></OBSERVACOESGERAIS>
                <IMOVEIS>
                    <IMOVEL>                        
                        <LOCALIZACAO></LOCALIZACAO>
                        <NUMEROREGISTRO></NUMEROREGISTRO>
                        <IPTU></IPTU>
                        <CCIR></CCIR>
                        <NIRF></NIRF>
                        <LIVRO></LIVRO>
                        <TIPOIMOVEL></TIPOIMOVEL>
                        <EDIFICACAO></EDIFICACAO>
                        <ENDERECO>
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
                            <COMPLEMENTO></COMPLEMENTO>
                        </ENDERECO> 
                    </IMOVEL>
                </IMOVEIS>
                <PARTES>
                    <PARTE>
                        <QUALIFICACAO></QUALIFICACAO>
                        <CPFCNPJ></CPFCNPJ>
                        <FRACAO></FRACAO>
                    </PARTE>
                </PARTES>
            </NEGOCIO>          
                
        </NEGOCIOS>
        <FINANCIAMENTO>
            <DADOS>
                <VALORFINANCIAMENTO></VALORFINANCIAMENTO>
                <VALORAVALIACAO></VALORAVALIACAO>
                <VALORLEILAO></VALORLEILAO>
                <PRAZOCARENCIA></PRAZOCARENCIA>
                <ENQUADRAMENTOFINANCIAMENTO></ENQUADRAMENTOFINANCIAMENTO>
                <SISTEMAAMORTIZACAO></SISTEMAAMORTIZACAO>
                <ORIGEMRECURSOS></ORIGEMRECURSOS>
                <JUROSANUALNOMINAL></JUROSANUALNOMINAL>
                <JUROSANUALEFETIVO></JUROSANUALEFETIVO>
                <JUROSMENSALNOMINAL></JUROSMENSALNOMINAL>
                <JUROSMENSALEFETIVO></JUROSMENSALEFETIVO>
                <PRAZOAMORTIZACAO></PRAZOAMORTIZACAO>
                <VALORPRIMEIRAPARCELA></VALORPRIMEIRAPARCELA>
                <DATAPRIMEIRAPARCELA></DATAPRIMEIRAPARCELA>
                <DESTFINANCIAMENTO></DESTFINANCIAMENTO>
                <FORMADEPAGAMENTO></FORMADEPAGAMENTO>
                <VALORTOTALCREDITO></VALORTOTALCREDITO>
                <!-- CAMPOS PARA CONVENIO DE LIMITE DE CRÉDITO COM ALIENAÇÃO FIDUCIÁRIA DE IMÓVEL -->
                <TAXAMAXIMAJUROS></TAXAMAXIMAJUROS>
                <TAXAMINIMAJUROS></TAXAMINIMAJUROS>
                <!-- CAMPOS PARA CONVENIO DE LIMITE DE CRÉDITO COM ALIENAÇÃO FIDUCIÁRIA DE IMÓVEL -->
                <PRAZODEVIGENCIA></PRAZODEVIGENCIA>
                <!-- CAMPOS PARA CONVENIO DE LIMITE DE CRÉDITO COM ALIENAÇÃO FIDUCIÁRIA DE IMÓVEL -->
                <VENCIMENTOANTECIPADO></VENCIMENTOANTECIPADO>
                <!-- CAMPOS PARA CONVENIO DE LIMITE DE CRÉDITO COM ALIENAÇÃO FIDUCIÁRIA DE IMÓVEL -->
                <INFORMACAOGERAIS></INFORMACAOGERAIS>
            </DADOS>
        </FINANCIAMENTO>
        <CEDULA>
            <TIPO></TIPO>
            <!-- CCI OU CCB-->
            <TIPOCEDULA></TIPOCEDULA>
            <!-- INTEGRAL E FRACIONÁRIA -->
            <NUMERO></NUMERO>
            <FRACAO></FRACAO>
            <SERIE></SERIE>
            <ESPECIE></ESPECIE>
            <!--CARTULAR E ESCRITURAL -->
            <CUSTODIANTEEMISSOR></CUSTODIANTEEMISSOR>
            <DATA/>
        </CEDULA>
        <PARTESNEGOCIO>
            <PARTE>
                <QUALIFICACAO></QUALIFICACAO>
                <NOME></NOME>
                <CPFCNPJ></CPFCNPJ>
                <GENERO></GENERO>
                <MENORDEIDADE></MENORDEIDADE>
                <DATANASCIMENTO></DATANASCIMENTO>
                <DOCUMENTO></DOCUMENTO>
                <ORGAOEMISSOR></ORGAOEMISSOR>
                <NACIONALIDADE></NACIONALIDADE>
                <CAPACIDADECIVIL></CAPACIDADECIVIL>
                <ESTADOCIVIL></ESTADOCIVIL>
                <REGIMEBENS></REGIMEBENS>
                <DATACASAMENTO></DATACASAMENTO>
                <NUMEROPACTO></NUMEROPACTO>
                <DATAPACTO></DATAPACTO>
                <LOCALREGISTROPACTO></LOCALREGISTROPACTO>
                <UNIAOESTAVEL></UNIAOESTAVEL>
                <PROFISSAO></PROFISSAO>
                <ENDERECO>
                    <TIPOLOGRADOURO></TIPOLOGRADOURO>
                    <LOGRADOURO></LOGRADOURO>
                    <NUMERO></NUMERO>
                    <UNIDADE></UNIDADE>
                    <BAIRRO></BAIRRO>
                    <CEP></CEP>
                    <CIDADE></CIDADE>
                    <UF></UF>
                </ENDERECO> 
                <CPFCONJUGE></CPFCONJUGE>
                <CONJUGEAUSENTE></CONJUGEAUSENTE>
                <EMAIL></EMAIL>
                <FILIACAO1></FILIACAO1>
                <FILIACAO2></FILIACAO2>
                <REPRESENTANTE></REPRESENTANTE>
            </PARTE>
        </PARTESNEGOCIO>
        <REPRESENTANTE>
            <INSTRUMENTO>
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
            <DECLARO>
                <![CDATA[DECLARO QUE ESTES DADOS CORRESPONDEM FIDEDIGNAMENTE AOS QUE CONSTAM NO 
                RESPECTIVO INSTRUMENTO PARTICULAR COM FORÇA DE ESCRITURA PÚBLICA QUE LHE DEU ORIGEM, 
                FORMALIZADO COM TODAS AS CLÁUSULAS OBRIGATÓRIAS, QUE SE ENCONTRA EM SEU ARQUIVO, 
                E QUE FOI VERIFICADA A IDENTIFICAÇÃO E A REGULARIDADE DA REPRESENTAÇÃO DAS PARTES 
                QUE SUBSCREVERAM O DOCUMENTO ORIGINAL.]]>
            </DECLARO>
            <AUTORIZO>
                <![CDATA[AUTORIZO O OFICIAL DE REGISTRO DE IMÓVEIS A 
                PRATICAR OS ATOS EXCLUSIVAMENTE COM BASE NOS DADOS PRESENTES NESTE DOCUMENTO.]]>
            </AUTORIZO>
            <AUTORIZO>
                <![CDATA[DECLARO QUE HÁ EXISTÊNCIA DE CLAUSULA ASSEGURANDO AO FIDUCIANTE, ENQUANTO ADIMPLENTE, 
                A LIVRE UTILIZAÇÃO DO IMÓVEL OBJETO DA ALIENAÇÃO FIDUCIÁRIA. ]]>
            </AUTORIZO>
            <AUTORIZO>
                <![CDATA[DECLARO QUE CONSTAM CLAUSULAS DISPONDO SOBRE OS PROCEDIMENTOS DO PÚBLICO LEILÃO PARA 
                ALIENAÇÃO DO IMÓVEL, NOS TERMOS DO ARTIGO 27 DA LEI 9.514. ]]>
            </AUTORIZO>
        </AUTORIZACOES>
    </CONTRATO>
</CONTRATOS>
```