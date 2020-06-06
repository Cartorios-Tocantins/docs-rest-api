---
method: POST
url: "{{CARTORIO_URL}}:cns/bancos/contratos"
---

##### Contratos Eletrônicos

O presente método descrever a solicitação de Contrato Eletrônico Estruturado para Registro dos bancos, atendendo os seguintes negócios:

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

```request:Python
import requests

url = "{{CARTORIO_URL}}bancos/contratos"
headers = {
    'Authorization': 'Bearer: {JWT Token Here}'
    'Content-Type': 'application/xml'
}


xml = """
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
"""

response = requests.post(url, data=xml, headers=headers)
print(response.text.encode('utf8'))
```

```response:200
{
    "mensagem": "Solicitação efetuada com sucesso."
}
```

| **Parâmetros**                                                                                                                                                                                                                                             |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **CONTRATOS** `list` *Lista de Contratos.*                                                                                                                                                                                                          |
| **CONTRATOS.VERSAO** `string` *Campo para identificação do modelo XML – PARA BANCOS VALOR “3.1.0”.*                                                                                                                                                 |
| **CONTRATOS.CONTRATO** `object` *Um contrato com seus respectivos dados.*                                                                                                                                                                           |
| **CONTRATOS.CONTRATO.CNS** `int` *Número do CNS*                                                                                                                                                                                                    |
| **CONTRATOS.CONTRATO.EMPREENDIMENTO** `object` *Empreendimento – esse campo será utilizado pela Registro de Imóveis do Brasil, para gerar o BOLETO separado por empreendimento.*                                                                                            |
| **CONTRATOS.CONTRATO.EMPREENDIMENTO.CODIGO** `int` *Código do empreendimento – usado para agrupamento para geração do boleto*                                                                                                                       |
| **CONTRATOS.CONTRATO.EMPREENDIMENTO.NOME** `string` *Nome do empreendimento*                                                                                                                                                                        |
| **CONTRATOS.CONTRATO.NATUREZA** `int` *Campo para identificação da natureza do título. Pode assumir os valores: <br>1 - instrumento particular com força de escritura pública <br>2 - cédula de crédito imobiliário <br>3 - cédula de crédito bancário* |
| **CONTRATOS.CONTRATO.DATAINSTRUMENTO** `date` *Data do instrumento no formato `YYYY-MM-DD`*                                                                                                                                                         |
| **CONTRATOS.CONTRATO.NUMCONTRATO** `string` *Número do contrato com no máximo 30 caracteres.*                                                                                                                                                       |
| **CONTRATOS.CONTRATO.REMETENTE** `object` *Remetente do contrato.*                                                                                                                                                                                  |
| **CONTRATOS.CONTRATO.REMETENTE.NOME** `string` *Nome do remetente com no máximo 500 carácteres.*                                                                                                                                                    |
| **CONTRATOS.CONTRATO.REMETENTE.CPFCNPJ** `string` *CPF ou CNPJ do remetente, nos formatos `XXX.XXX.XXX-XX` ou `XX.XXX.XXX/XXXX-XX`.*                                                                                                                |
| **CONTRATOS.CONTRATO.REMETENTE.ENDERECO** `object` *Endereço da parte*                                                                                                                                                                              |
| **CONTRATOS.CONTRATO.REMETENTE.ENDERECO.ENDERECOPARTE.ENDERECO** `object` *Classe ENDERECOPARTE*                                                                                                                                                    |
| **CONTRATOS.CONTRATO.REMETENTE.ENDERECO.ENDERECOPARTE.ENDERECO.TIPOLOGRADOURO** `string` *Tipo logradouro do endereço do apresentante - Tamanho máximo: 20 caracteres.*                                                                             |
| **CONTRATOS.CONTRATO.REMETENTE.ENDERECO.ENDERECOPARTE.ENDERECO.LOGRADOURO** `string` *Logradouro do endereço do apresentante - Tamanho máximo 500 caracteres.*                                                                                      |
| **CONTRATOS.CONTRATO.REMETENTE.ENDERECO.ENDERECOPARTE.ENDERECO.NUMERO** `string` *Número do endereço do apresentante - Tamanho máximo 10 caracteres.*                                                                                               |
| **CONTRATOS.CONTRATO.REMETENTE.ENDERECO.ENDERECOPARTE.ENDERECO.UNIDADE** `sting` *Unidade do endereço do apresentante  - Tamanho máximo 10 caracteres.*                                                                                             |
| **CONTRATOS.CONTRATO.REMETENTE.ENDERECO.ENDERECOPARTE.ENDERECO.BAIRRO** `string` *Bairro do endereço do apresentante - Tamanho máximo 100 caracteres*                                                                                               |
| **CONTRATOS.CONTRATO.REMETENTE.ENDERECO.ENDERECOPARTE.ENDERECO.CIDADE** `string` *Cidade do endereço do apresentante - Tamanho máximo 100 caracteres.*                                                                                              |
| **CONTRATOS.CONTRATO.REMETENTE.ENDERECO.ENDERECOPARTE.ENDERECO.UF** `string` *UF do endereço do apresentante - Tamanho máximo 2 caracteres.*                                                                                                        |
| **CONTRATOS.CONTRATO.REMETENTE.ENDERECO.ENDERECOPARTE.ENDERECO.CEP** `int` *CEP do apresetante - Tamanho máximo 8 dígitos.*                                                                                                                         |
| **CONTRATOS.CONTRATO.REMETENTE.CONTATO** `objetc` *Contato do remetente*                                                                                                                                                                            |
| **CONTRATOS.CONTRATO.REMETENTE.CONTATO.EMAIL** `string` *Email do Contato*                                                                                                                                                                          |
| **CONTRATOS.CONTRATO.REMETENTE.CONTATO.TELEFONE** `object` *Telefone do Contato*                                                                                                                                                                    |
| **CONTRATOS.CONTRATO.REMETENTE.CONTATO.TELEFONE.DDD** `int` *DDD do contato - 3 caracteres.*                                                                                                                                                        |
| **CONTRATOS.CONTRATO.REMETENTE.CONTATO.TELEFONE.NUMERO** `string` *Número do Contato - 20 caracteres.*                                                                                                                                              |
| **CONTRATOS.CONTRATO.REMETENTE.REPRESENTANTE** `objetc` *Representante do remetente - REPRESENTANTECOMPACTO*                                                                                                                                        |
| **CONTRATOS.CONTRATO.REMETENTE.REPRESENTANTE.REPRESENTANTECOMPACTO.REPRESENTANTE** `list` *Lsta de representante*                                                                                                                                   |
| **CONTRATOS.CONTRATO.REMETENTE.REPRESENTANTE.REPRESENTANTECOMPACTO.REPRESENTANTE.NOME** `string` *Nome do representante - Tamanho máximo 500 carácteres.*                                                                                           |
| **CONTRATOS.CONTRATO.REMETENTE.REPRESENTANTE.REPRESENTANTECOMPACTO.REPRESENTANTE.CPF** `string` *CPF do representante - no formato 'XXX.XXX.XXX-XX'  - Tamanho máximo 14 caracteres*                                                                |
| **CONTRATOS.CONTRATO.APRESENTANTE** `object` *Apresetante do título.*                                                                                                                                                                               |
| **CONTRATOS.CONTRATO.APRESENTANTE.NOME** `string` *Nome do apresentante - Tamanho máximo 500 carácteres.*                                                                                                                                           |
| **CONTRATOS.CONTRATO.APRESENTANTE.CPFCNPJ** `string` *CPF ou CNPJ do apresentante, nos formatos `XXX.XXX.XXX-XX` ou `XX.XXX.XXX/XXXX-XX` - Tamanho máximo 20 caracteres.*                                                                           |
| **CONTRATOS.CONTRATO.APRESENTANTE.ENDERECO** `list` *Endereço da parte*                                                                                                                                                                             |
| **CONTRATOS.CONTRATO.APRESENTANTE.ENDERECO.ENDERECOPARTE** `object` *Classe ENDERECOPARTE*                                                                                                                                                          |
| **CONTRATOS.CONTRATO.APRESENTANTE.ENDERECO.ENDERECOPARTE.ENDERECO.TIPOLOGRADOURO** `string` *Tipo logradouro do endereço do apresentante - Tamanho máximo: 20 caracteres.*                                                                          |
| **CONTRATOS.CONTRATO.APRESENTANTE.ENDERECO.ENDERECOPARTE.ENDERECO.LOGRADOURO** `string` *Logradouro do endereço do apresentante - Tamanho máximo 500 caracteres.*                                                                                   |
| **CONTRATOS.CONTRATO.APRESENTANTE.ENDERECO.ENDERECOPARTE.ENDERECO.NUMERO** `string` *Número do endereço do apresentante - Tamanho máximo 10 caracteres.*                                                                                            |
| **CONTRATOS.CONTRATO.APRESENTANTE.ENDERECO.ENDERECOPARTE.ENDERECO.UNIDADE** `sting` *Unidade do endereço do apresentante  - Tamanho máximo 10 caracteres.*                                                                                          |
| **CONTRATOS.CONTRATO.APRESENTANTE.ENDERECO.ENDERECOPARTE.ENDERECO.BAIRRO** `string` *Bairro do endereço do apresentante - Tamanho máximo 100 caracteres*                                                                                            |
| **CONTRATOS.CONTRATO.APRESENTANTE.ENDERECO.ENDERECOPARTE.ENDERECO.CIDADE** `string` *Cidade do endereço do apresentante - Tamanho máximo 100 caracteres.*                                                                                           |
| **CONTRATOS.CONTRATO.APRESENTANTE.ENDERECO.ENDERECOPARTE.ENDERECO.UF** `string` *UF do endereço do apresentante - Tamanho máximo 2 caracteres.*                                                                                                     |
| **CONTRATOS.CONTRATO.APRESENTANTE.ENDERECO.ENDERECOPARTE.ENDERECO.CEP** `int` *CEP do apresetante - Tamanho máximo 8 dígitos.*                                                                                                                      |
| **CONTRATOS.CONTRATO.APRESENTANTE.CONTATO** `objetc` *Contato do apresentante*                                                                                                                                                                      |
| **CONTRATOS.CONTRATO.REMETENTE.CONTATO.EMAIL** `string` *Email do Contato*                                                                                                                                                                          |
| **CONTRATOS.CONTRATO.REMETENTE.CONTATO.TELEFONE** `object` *Telefone do Contato*                                                                                                                                                                    |
| **CONTRATOS.CONTRATO.REMETENTE.CONTATO.TELEFONE.DDD** `int` *DDD do contato - 3 caracteres.*                                                                                                                                                        |
| **CONTRATOS.CONTRATO.REMETENTE.CONTATO.TELEFONE.NUMERO** `string` *Número do Contato - 20 caracteres.*                                                                                                                                              |
| **CONTRATOS.CONTRATO.NEGOCIOS** `list` *Lista de Negócios*                                                                                                                                                                                          |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO** `object` *Classe Negócio*                                                                                                                                                                                   |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.SEQUENCIAL** `int` *Sequência do negócio, para ordenar os atos e para poder vincular as partes do negócio*                                                                                                    |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.TIPOATO** `int` *Campo para identificação do tipo do ato à ser praticado - Tamanho máximo 200. Pode assumir os valores: <br>1 - Venda e Compra <br>2 - Hipoteca <br>3 - Alienação Fiduciária <br>4 - Portabilidade <br>5 - Compra e Venda Alienação <br>6 - Compra e Venda Alienação CCI <br>7 - Compra e Venda Alienação CCB <br>8  - Convenio de Limite de Crédito com Alienação Fiduciária <br>9 - compromisso de venda e compra <br>10 - Doação <br>18 - Aditamento de cédula* |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.VALORTRANSMISSAO** `string` *Valor do negócio – Valor da venda, valor da alienação, valor da cédula.  Monetário, ex.: 10518.65*                                                                               |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.VALORVENAL** `string` *Valor da venal do negócio. Monetário, ex.: 10518.65.*                                                                                                                                  |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.VALORFINANCIAMENTO** `string` *Valor do financiamento do negócio.  Monetário, ex.: 10518.65*                                                                                                                  |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.VALORAVALIACAO** `string` *Valor da avaliação do imóvel. Monetário, ex.: 10518.65*                                                                                                                            |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.VALORLEILAO** `string` *Valor para fins de leilão. Monetário, ex.: 10518.65*                                                                                                                                  |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.RECURSOSPROPRIOS** `string` *Valor dos recursos próprios.  Monetário, ex.: 10518.65*                                                                                                                          |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.FINANCIAMENTOFAR** `string` *Valor dos recursos financiados / subsídios concedidos. Monetário, ex.: 10518.65*                                                                                                 |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.SUBSIDIOS** `string` *Valor dos subsídios. Monetário, ex.: 10518.65*                                                                                                                                          |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.FGTS** `string` *Recursos utilizados da conta vinculada do trabalhador. Monetário, ex.: 10518.65*                                                                                                             |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.OUTROSRECURSOS** `string` *Outros recursos não descritos em campos específicos que completem o VALORTRANSMISSAO. Monetário, ex.: 10518.65*                                                                    |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.PRIMEIRAAQUISICAO** `int` *Marcar se a instituição financeira apresenta requerimento de desconto em virtude de primeira aquisição. Ex.: 0/1 <br>1 - Verdadeiro <br>2 - Falso* |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.OBSERVACOESGERAIS** `text` *Observação relacionada ao negócio*                                                                                                                                                |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS** `list` *Lista de imóveis vinculados ao ato*                                                                                                                                                         |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL** `object` *Classe Imovel*                                                                                                                                                                     |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.CNS** `int` *CNS – Código nacional de serventias*                                                                                                                                              |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.LOCALIZACAO** `lint` *Lista do tipo de localização do imóvel. Serão aceitos os valores: <br>1 - Urbano <br>2 - Rural* |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.NUMEROREGISTRO** `int` *Número de registro - Tamanho máximo 10 caracteres*                                                                                                                     |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.IPTU** `string` *Número do IPTU - Tamanho máximo 20 caracteres*                                                                                                                                |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.CCIR** `string` *Número do CCIR - Tamanho máximo 20 caracteres*                                                                                                                                |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.NIRF** `string` *Número do NIRF- Tamanho máximo 20 caracteres*                                                                                                                                 |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.LIVRO** `lint` *Lista do tipo tipo de livro referente ao número do registro . Serão aceitos os valores: <br>1 - Lv.2-Registro Geral (matrícula) <br>2 - Lv.3-Transcrição das Transmissões* |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.TIPOIMOVEL** `lint` *Lista do tipo tipo de Imóvel. Serão aceitos os valores: <br>1 - Apartamento; 2 - Área de Terra; 3 - Área de terras; 4 - Armazém; 5 - Bangalô; 6 - Barracão; 7 - Casa de moradia; 8 - Chácara; 9 - Chalé; 10 - Cômodo comercial; 11 - Conjunto; 12 - Depósito; 13 - Edícula; 14 - Fazenda; 15 - Galpão; 16 - Garagem; 17 - Gleba de terra; 18 - Kitchenette; 19 - Loja; 20 - Prédio; 21 - Prédio comercial; 22 - Prédio p/ indústria; 23 - Prédio residencial; 24 - Quinhão de terra; 25 - Rua particular; 26 - Sala; 27 - Saão; 28 - Sítio; 29 - Sobreloja; 30 - Terreno; 31 - Unid. res.autônoma; 32 - Unidade Autônoma; 33 - Unidade residencial* |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.ENDERECO** `object` *Endereço do Imóvel*                                                                                                                                                       |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.ENDERECO.ENDERECOIMOVEL.ENDERECO** `object` *Class enderecoimovel*                                                                                                                             |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.ENDERECO.ENDERECOIMOVEL.ENDERECO.TIPOLOGRADOURO** `string` *Tipo logradouro do endereço do imóvel. Tamanho máximo 30 caracteres.*                                                              |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.ENDERECO.ENDERECOIMOVEL.ENDERECO.LOGRADOURO** `string` *Logradouro do endereço do imóvel. Tamanho máximo 255 caracteres.*                                                                      |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.ENDERECO.ENDERECOIMOVEL.ENDERECO.NUMERO** `string` *Número do endereço do imóvel. Tamanho máximo 10 caracteres.*                                                                               |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.ENDERECO.ENDERECOIMOVEL.ENDERECO.UNIDADE** `string` *Unidade do endereço do imóvel . Tamanho máximo 10 caracteres.*                                                                            |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.ENDERECO.ENDERECOIMOVEL.ENDERECO.BAIRRO** `string` *Bairro do endereço do imóvel. Tamanho máximo 100 caracteres.*                                                                              |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.ENDERECO.ENDERECOIMOVEL.ENDERECO.CIDADE** `string` *Cidade do endereço do imóvel. Tamanho máximo 100 caracteres.*                                                                              |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.ENDERECO.ENDERECOIMOVEL.ENDERECO.UF** `string` *UF do endereço do imóvel. Tamanho máximo 2 caracteres.*                                                                                        |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.ENDERECO.ENDERECOIMOVEL.ENDERECO.LOTE** `string` *Lote do endereço do imóvel. Tamanho máximo 10 caracteres.*                                                                                   |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.ENDERECO.ENDERECOIMOVEL.ENDERECO.QUADRA** `string` *Quadra do endereço do imóvel. Tamanho máximo 10 caracteres.*                                                                               |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.ENDERECO.ENDERECOIMOVEL.ENDERECO.TORRE** `string` *Torre do endereço do imóvel. Tamanho máximo 20 caracteres.*                                                                                 |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.ENDERECO.ENDERECOIMOVEL.ENDERECO.COMPLEMENTO** `string` *Complemento do endereço do imóvel. Tamanho máximo 100 caracteres.*                                                                    |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.ENDERECO.ENDERECOIMOVEL.ENDERECO.TORRE** `string` *Torre do endereço do imóvel. Tamanho máximo 20 caracteres.*                                                                                 |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.IMOVEIS.IMOVEL.ENDERECO.ENDERECOIMOVEL.ENDERECO.EDIFICACAO** `lint` *Lista do tipo tipo de Imóvel. Serão aceitos os valores: <br>0 - Não se aplica <br>1 - Construído <br>2 - Em construção* |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.PARTES** `list` *Lista de partes vinculados ao ato*                                                                                                                                                           |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.PARTES.PARTE** `object` *Classe Parte*                                                                                                                                                                        |
| **CONTRATOS.CONTRATO.NEGOCIOS.NEGOCIO.PARTES.PARTE.QUALIFICACAO** `int` *Lista do tipo tipo de qualificação da parte. Serão aceitos os valores: <br>1 - Adquirente <br>2 - Avalista <br>3 - Credor <br>4 - Depositário <br>5 - Devedor <br>6 - Incorporado <br>7 - Incorporador <br>8 - Interessado <br>9 - Interveniente <br>10 - Proprietário <br>11 - Requerente <br>12 - Transmitente <br>13 - Anuente <br>14 - Representante Credor* |
| **CONTRATOS.CONTRATO.FINANCIAMENTO** `object` *Dados do financiamento*                                                                                                                                                                              |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO** `object` *Class FINANCIAMENTO*                                                                                                                                                                   |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.VALORFINANCIAMENTO** `string` *Valor do Financiamento.  Monetário, ex.: 10518.65*                                                                                                                  |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.VALORAVALIACAO** `string` *Valor da avaliação.  Monetário, ex.: 10518.65*                                                                                                                          |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.VALORLEILAO** `string` *Valor do leilão  Monetário, ex.: 10518.65*                                                                                                                                 |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.PRAZOCARENCIA** `int` *Prazo de carência para expedição da intimação (art.26, § 2,L.9514/97)*                                                                                                      |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.ENQUADRAMENTOFINANCIAMENTO** `int` *Tipo de enquadramento. Lista controlada, tamanho 100. <br>1 - SFH taxa tabelada <br>2 - SFH taxa de mercado <br>3 - PMCMV <br>4 - SFI <br>5  - Outro* |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.SISTEMAAMORTIZACAO** `int` *Sistema de amortização. Lista controlada, tamanho 100. <br>1 - SAC <br>2 - SACRE <br>3 - PRICE <br>4 - Outro <br>5 - Complementar em informações gerais* |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.ORIGEMRECURSOS** `int` *Origem dos recursos. Lista controlada, tamanho 30. <br>1 - Não utiliza <br>2 - FAR <br>3 - FGTS <br>4 - FGTS/UNIÃO <br>5 - SBPE <br>6 - Privados* |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.JUROSANUALNOMINAL** `float` *Juros anual nominal*                                                                                                                                                  |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.JUROSANUALEFETIVO** `float` *Juros anual efetivo*                                                                                                                                                  |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.JUROSMENSALNOMINAL** `float` *Juros mensal efetivo*                                                                                                                                                |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.JUROSMENSALEFETIVO** `float` *Juros mensal efetivo*                                                                                                                                                |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.PRAZOAMORTIZACAO** `int` *Prazo de amortização*                                                                                                                                                    |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.VALORPRIMEIRAPARCELA** `string` *Valor de primeira parcela.  Monetário, ex.: 10518.65.*                                                                                                            |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.DATAPRIMEIRAPARCELA** `date` *Data primeira parcela. Formato de Data, ex.: YYYY-MM-DD.*                                                                                                            |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.DESTFINANCIAMENTO** `string` *Destino do financiamento. Tamanho máximo: 50 carateres.*                                                                                                             |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.FORMADEPAGAMENTO** `string` *Forma de pagamento. Tipo descrito no pdf: Text, no formato: <![CDATA[ texto ]]>.*                                                                                     |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.VALORTOTALCREDITO** `string` *Valor total de crédito.   Monetário, ex.: 10518.65.*                                                                                                                 |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.TAXAMAXIMAJUROS** `float` *Taxa máxima de juros*                                                                                                                                                   |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.TAXAMINIMAJUROS** `float` *Taxa mínima de juros*                                                                                                                                                   |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.PRAZODEVIGENCIA** `int` *Prazo de amortização*                                                                                                                                                     |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.VENCIMENTOANTECIPADO** `string` *Vencimento antecipado.  Monetário, ex.: 10518.65.*                                                                                                                |
| **CONTRATOS.CONTRATO.FINANCIAMENTO.FINANCIAMENTO.INFORMACAOGERAIS** `string` *Informações gerais. Tamanho 500 caracteres.*                                                                                                                          |
| **CONTRATOS.CONTRATO.CEDULA** `object` *Dados da cédula*                                                                                                                                                                                            |
| **CONTRATOS.CONTRATO.CEDULA.CEDULA** `object` *Class  CEDULA*                                                                                                                                                                                       |
| **CONTRATOS.CONTRATO.CEDULA.CEDULA.TIPOCEDULA** `string` *Tipo da cédula. Tamanho máximo 50 caracteres*                                                                                                                                             |
| **CONTRATOS.CONTRATO.CEDULA.CEDULA.TIPO** `int` *Tipo. Pode assumir os valores: <br>1 - Integral <br>2 - Fracionária* |
| **CONTRATOS.CONTRATO.CEDULA.CEDULA.NUMERO** `string` *Número da cédula. Tamanho máximo: 20 caracteres.*                                                                                                                                             |
| **CONTRATOS.CONTRATO.CEDULA.CEDULA.FRACAO** `float` *Fração da cédula*                                                                                                                                                                              |
| **CONTRATOS.CONTRATO.CEDULA.CEDULA.SERIE** `string` *Série da cédula. Tamanho máximo: 20 caracteres.*                                                                                                                                               |
| **CONTRATOS.CONTRATO.CEDULA.CEDULA.ESPECIE** `int` *Espécie da cédula. Pode assumir os valores: <br>1 - Cartular <br>2 - Escritural* |
| **CONTRATOS.CONTRATO.CEDULA.CEDULA.CUSTODIANTE_EMISSOR** `string` *Custo diante emissor. Tamanho máximo: 50 caracteres.*                                                                                                                            |
| **CONTRATOS.CONTRATO.CEDULA.CEDULA.DATA** `date` *Data da cédula.  Formato de Data, ex.: YYYY-MM-DD*                                                                                                                                                |
| **CONTRATOS.CONTRATO.PARTESNEGOCIO** `list` *Lista de PARTE*                                                                                                                                                                                        |
| **CONTRATOS.CONTRATO.PARTESNEGOCIO.PARTENEGOCIO.PARTE** `object` *Classe PARTE*                                                                                                                                                                     |
| **CONTRATOS.CONTRATO.PARTESNEGOCIO.PARTENEGOCIO.PARTE.QUALIFICACAO** `string` *Qualificações das partes do contrato – Descrever todas as qualificações que a parte será no processo separados por “,”. Ex. (1, 3). Tamanho máximo: 500 caracteres.* |
| **CONTRATOS.CONTRATO.PARTESNEGOCIO.PARTENEGOCIO.PARTE.NOME** `string` *Nome da parte. Tamanho máximo: 500 caracteres.*                                                                                                                              |
| **CONTRATOS.CONTRATO.PARTESNEGOCIO.PARTENEGOCIO.PARTE.CPFCNPJ** `string` *CPF / CNPJ da parte, nos formatos `XXX.XXX.XXX-XX` ou `XX.XXX.XXX/XXXX-XX` - Tamanho máximo 20 caracteres.*                                                               |
| **CONTRATOS.CONTRATO.PARTESNEGOCIO.PARTENEGOCIO.PARTE.GENERO** `int` *Gênero. Pode assumir os valores: <br>1 - Masculino <br>2 - Feminino* |
| **CONTRATOS.CONTRATO.PARTESNEGOCIO.PARTENEGOCIO.PARTE.MENORDEIDADE** `int` *Se a parte é menor de idade. Tipo Booleano, pode assumir os valores: 0 - Falso e/ou 1 - Verdadeiro. <br>0 - Não <br>1 - Sim* |
| **CONTRATOS.CONTRATO.PARTESNEGOCIO.PARTENEGOCIO.PARTE.DATANASCIMENTO** `date` *Data de nascimento. Formato de Data, ex.: YYYY-MM-DD.*                                                                                                               |
| **CONTRATOS.CONTRATO.PARTESNEGOCIO.PARTENEGOCIO.PARTE.DOCUMENTO** `string` *Documento da parte. Tamanho máximo: 30 caracteres.*                                                                                                                     |
| **CONTRATOS.CONTRATO.PARTESNEGOCIO.PARTE.ORGAOEMISSOR** `string` *Órgão emissor do documento. Tamanho máximo: 20 caracteres.*                                                                                                                       |
| **CONTRATOS.CONTRATO.PARTESNEGOCIO.PARTENEGOCIO.PARTE.NACIONALIDADE** `string` *Nacionalidade. Tamanho máximo: 50 caracteres.*                                                                                                                      |
| **CONTRATOS.CONTRATO.PARTESNEGOCIO.PARTENEGOCIO.PARTE.CAPACIDADECIVIL** `int` *Capacidade civil. Pode assumir os valores: <br>1 - Capaz <br>2 - Relativamente capaz <br>3 - Incapaz*                                                                |
| **CONTRATOS.CONTRATO.PARTESNEGOCIO.PARTENEGOCIO.PARTE.ESTADOCIVIL** `int` *Estado Civil. Pode assumir os valores: <br>1 - Casada <br>2 - Casado <br>3 - Divorciada <br>4 - Divorciado <br>5 - Espólio <br>6 - Separada <br>7 - Separada judicialmente <br>8 - Separado <br>9 - Separado judicialmente <br>10 - Solteira <br>11 - Solteira, maior <br>12 - Solteira, menor impúbere <br>13 - Solteira, menor púbere <br>14 - Solteiro <br>15 - Solteiro, maior <br>16 - Solteiro, menor impúbere <br>17 - Solteiro, menor púbere <br>18 - Viúva <br>19 - Viúvo <br>20 - Menor emancipado <br>21 - Outros* |
| **CONTRATOS.CONTRATO.PARTESNEGOCIO.PARTENEGOCIO.PARTE.REGIMEBENS** `int` *Regime de bens. Pode assumir os valores: <br>1 - Comunhão de bens <br>2 - Comunhão de bens vigente na Venezuela <br>3 - Comunhão parcial de bens <br>4 - Comunhão parcial de bens às Leis da Noruega <br>5 -  Comunhão parcial de bens, à Lei Suiça <br>6 - Comunhão parcial de bens, antes da vigência da Lei 6.515/77 <br>7 - Comunhão parcial de bens, na vigência da Lei 6.515/77 <br>8 - Comunhão universal de bens <br>9 - Comunhão universal de bens, antes da vigência da Lei 6.515/77 <br>10 - Comunhão universal de bens, às Leis de Ângola <br>11 - Comunhão universal de bens, às Leis italianas <br>12 - Comunhão universal de bens, na vigência da Lei 6.515/77 <br>13 - Conforme a lei vigente em Israel <br>14 - Leis da Alemanha <br>15 - Leis da Argentina <br>16 - Leis da Austrália <br>17 - Leis da Bolívia <br>18 - Leis da China <br>19 - Leis da Colômbia <br>20 - Leis da Costa do Marfim <br>21 - Leis da Costa Rica <br>22 - Leis da Dinamarca <br>23 - Leis da Espanha <br>24 - Leis da Finlândia <br>25 - Leis da França <br>26 - Leis da Guatemala <br>27 - Leis da Holanda <br>28 - Leis da Inglaterra <br>29 - Leis da Itália <br>30 - Leis da Jordania <br>31 - Leis da Jordânia <br>32 - Leis da Polonia <br>33 - Leis da República da Coréia <br>34 - Leis da Suíça <br>35 - Leis de Angola <br>36 - Leis de Cuba <br>37 - Leis de Moscou <br>38 - Leis de Taiwan <br>39 - Leis do Canadá <br>40 - Leis do Japão <br>41 - Leis do Líbano <br>42 - Leis do Paraguai <br>43 - Leis do Uruguai <br>44 - Leis dos Estados Unidos <br>45 - Leis Egípcias <br>46 - Leis Portuguesas <br>47 - Participação final nos aquestos <br>48 - Regime de bens conforme as Leis americanas <br>49 - Regime vigente no Chile <br>50 - Separação de bens <br>51 - Separação de bens conforme as Leis da Áustria <br>52 - Separação de bens, antes da vigência da Lei 6.515/77 <br>53 - Separação de bens, na vigência da Lei 6.515/77 <br>54 - Separação obrigatória de bens <br>55 - Separação parcial, antes da vigência da Lei 6.515/77 <br>56 - Separação parcial, na vigência da Lei 6.515/77 <br>57 - Separação total de bens, na vigência da Lei 6.515/77* |
| **CONTRATOS.CONTRATO.PARTESNEGOCIO.PARTENEGOCIO.PARTE.DATACASAMENTO** `date` *Data de casamento. Formato de Data, ex.: YYYY-MM-DD.*                                                                                                                 |
| **CONTRATOS.CONTRATO.PARTESNEGOCIO.PARTENEGOCIO.PARTE.NUMEROPACTO** `string` *Número do pacto. Tamanho máximo: 20 caracteres.*                                                                                                                      |
| **CONTRATOS.CONTRATO.PARTESNEGOCIO.PARTENEGOCIO.PARTE.DATAPACTO** `date` *Data de pacto. Formato de Data, ex.: YYYY-MM-DD.*                                                                                                                         |
| **CONTRATOS.CONTRATO.REPRESENTANTE** `object` *Representante do contrato.*                                                                                                                                                                          |
| **CONTRATOS.CONTRATO.REPRESENTANTE.REPRESENTANTECOMPACTO.REPRESENTANTE** `object` *Classe REPRESENTANTECOMPACTO*                                                                                                                                    |
| **CONTRATOS.CONTRATO.REPRESENTANTE.REPRESENTANTECOMPACTO.REPRESENTANTE.NOME** `string` *Nome do representante. Tamanho máximo: 500 caracteres.*                                                                                                     |
| **CONTRATOS.CONTRATO.REPRESENTANTE.REPRESENTANTECOMPACTO.REPRESENTANTE.CPF** `string` *CPF do representante, no formato `XXX.XXX.XXX-XX` - Tamanho máximo 14 caracteres.*                                                                           |
| **CONTRATOS.CONTRATO.IMPOSTOS** `object` *Impostos ex. IMPOSTOTRANSMISSAO, DAJES*                                                                                                                                                                   |
| **CONTRATOS.CONTRATO.IMPOSTOS.IMPOSTOS** `object` *Classe IMPOSTOS*                                                                                                                                                                                 |
| **CONTRATOS.CONTRATO.IMPOSTOS.IMPOSTOS.IMPOSTOTRANSMISSAO** `objetc` *Dados do ITBI / ITCMD*                                                                                                                                                        |
| **CONTRATOS.CONTRATO.IMPOSTOS.IMPOSTOS.IMPOSTOTRANSMISSAO.ISENCAO** `int` *Se tem ou não isenção. Tipo Booleano, pode assumir os valores: 0 - Falso e/ou 1 - Verdadeiro.*                                                                           |
| **CONTRATOS.CONTRATO.IMPOSTOS.IMPOSTOS.IMPOSTOTRANSMISSAO.INSCRICAO** `string` *Número da inscrição. Tamanho máximo: 30 caracteres.*                                                                                                                |
| **CONTRATOS.CONTRATO.IMPOSTOS.IMPOSTOS.IMPOSTOTRANSMISSAO.GUIA** `string` *Número da guia paga / isenta. Tamanho máximo: 30 caracteres.*                                                                                                            |
| **CONTRATOS.CONTRATO.IMPOSTOS.IMPOSTOS.IMPOSTOTRANSMISSAO.VALOR** `string` *Valor pago. Monetário, ex.: 10518.65.*                                                                                                                                  |
| **CONTRATOS.CONTRATO.IMPOSTOS.IMPOSTOS.DAJES** `int` *Lista de recolhimentos – Utilizar apenas se existir tal recolhimento onde será registrado. Pode assumir os valores:*                                                                          |
| **CONTRATOS.CONTRATO.IMPOSTOS.IMPOSTOS.DAJES.EMISSOR** `string` *Emissor da DAJE*                                                                                                                                                                   |
| **CONTRATOS.CONTRATO.IMPOSTOS.IMPOSTOS.DAJES.SERIE** `string` *Série da DAJE*                                                                                                                                                                       |
| **CONTRATOS.CONTRATO.IMPOSTOS.IMPOSTOS.DAJES.GUIA** `string` *Número da DAJE*                                                                                                                                                                       |
| **CONTRATOS.CONTRATO.IMPOSTOS.IMPOSTOS.DAJES.VALOR** `string` *Valor da DAJE. Monetário, ex: 12345.67*                                                                                                                                              |
| **CONTRATOS.CONTRATO.CLAUSULASDECLARACOES** `object` *Lista de verificação partes e imóveis*                                                                                                                                                        |
| **CONTRATOS.CONTRATO.CLAUSULASDECLARACOES.VERIFICACAODAPARTES** `int` *Lista de verificações de partes*                                                                                                                                             |
| **CONTRATOS.CONTRATO.CLAUSULASDECLARACOES.VERIFICACAODAPARTES.VERIFICACAODAPARTE** `object` *Class VERIFICACAODAPARTE*                                                                                                                              |
| **CONTRATOS.CONTRATO.CLAUSULASDECLARACOES.VERIFICACAODAPARTES.VERIFICACAODAPARTE.PARTE** `string` *CPF ou CNPJ da parte, nos formatos `XXX.XXX.XXX-XX` ou `XX.XXX.XXX/XXXX-XX` - Tamanho máximo 20 caracteres.*                                     |
| **CONTRATOS.CONTRATO.CLAUSULASDECLARACOES.VERIFICACAODAPARTES.VERIFICACAODAPARTE.DESCREVER** `string` *Descrição da verificação da parte. Campo do tipo texto, não foi definido tamanho máximo.*                                                    |
| **CONTRATOS.CONTRATO.AUTORIZACOES** `object` *Lista de AUTORIZACAO*                                                                                                                                                                                 |
| **CONTRATOS.CONTRATO.AUTORIZACOES.DECLARO** `string` *Descrição do texto de declarações. Campo do tipo texto, não foi definido tamanho máximo.*                                                                                                     |
| **CONTRATOS.CONTRATO.AUTORIZACOES.AUTORIZO** `string` *Descrição da verificação da parte. Campo do tipo texto, não foi definido tamanho máximo.*                                                                                                    |