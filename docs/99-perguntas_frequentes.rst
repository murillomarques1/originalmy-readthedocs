Perguntas frequentes
====================

===========================
O que é Assinatura Digital?
===========================

É uma identidade única e exclusiva do documento, que comprova:

* Autenticidade: Comprova que o documento é ele mesmo
* Integridade: Qualquer alteração faz com que a assinatura não corresponda mais ao documento
* Irretratabilidade ou não-repúdio: Não é possível negar a autenticidade do documento

==============================
O que é o Código da Transação?
==============================

É o endereço onde o certificado digital ficará armazenado dentro do Blockchain. Através do código da transação é possível encontrar o certificado digital.

Dentro da transação é possível encontrar o certificado digital registrado na área de scripts, dentro do script chamado OP_RETURN, por exemplo:

Ex.: OP_RETURN c4569950f2a51432a8fcf93a62bb15a1365e42dbcce7f9b329ea0dfe36dd6ddd4f5249474d59

.. note:: Pode ser que alguns sites não exibam essa informação diretamente, por exemplo: no site blockchain.info é necessário clicar em 'Show scripts & Coinbase'

===============================
O que é um Certificado Digital?
===============================

Um certificado é usado para ligar uma entidade a uma chave pública (como uma assinatura digital).

O nosso certificado digital é composto de duas partes, no seguinte formato: [assinatura digital];[hora legal brasileira];[identificação do emissor]. 

Exemplo (em uma única linha, sem quebra): 
6a3fa2e2c7a6eb66f82116bb75c6953e8eb80e2cc7d2745a9ade8e210d0815c2d641
3b
323031362d30362d30382030303a30343a323020555443
3b
4f5249474d59

* Hora legal: É a Hora Legal Brasileira (HLB), coletada nos servidores NTP (pool.ntp.br) sincronizados com o Observatório Nacional (ON).

* Identificação do Emissor: É a sequência 4f5249474d59 em hexadecimal, que significa ORIGMY.

* Assinatura Digital: É a própria assinatura digital do documento

No certificado digital do exemplo acima:

* 3b: separador de campo em hexadecimal, se convertido mostra o texto ';'

* 323031362d30362d30382030303a30343a323020555443: É hora legal brasileira, em hexadecimal. Se convertido mostra o texto 2016-06-08 00:04:20 UTC

* 4f5249474d59: é identificação do OriginalMy.com, em hexadecimal. Se convertido, mostra o texto ORIGMY
6a3fa2e2c7a6eb66f82116bb75c6953e8eb80e2cc7d2745a9ade8e210d0815c2d641: é a própria assinatura digital do documento

=====================
O que é o Blockchain?
=====================

Blockchain ('cadeia de blocos' em inglês) é um banco de dados distribuído (livro-razão) de contabilidade pública que registra as transações bitcoin em uma rede ponto-a-ponto. 

O sistema blockchain utiliza a sua própria unidade de conta monetária chamado Bitcoin. O sistema não depende da confiança entre os diferentes usuários (nós da rede). Qualquer pessoa pode controlar e monitorar um nó do sistema. 

A rede bitcoin funciona de forma autônoma, sem um banco de dados central ou único administrador central. O blockchain é executado e mantido coletivamente por diversos nós da rede peer-to-peer para registrar as transações, e usa criptografia de código aberto para prover funções básicas de segurança para certificar que bitcoins só podem ser gastos pelo dono e evitar gastos duplos, falsificação e adulteração de bancos de dados. 

Uma solução inovadora que executa contabilidade aberta sem depender de uma autoridade central confiável. - Fonte: https://pt.wikipedia.org/wiki/Bitcoin#Block_chain.2C_a_cadeia_de_blocos

O OriginalMy é agnóstico em relação ao blockchain utilizado. Atualmente efetua registros nos Blockchains públicos das redes Bitcoin, Ethereum, Ethereum Classic, Decred, entre outros.

==========================================
A justiça reconhece este tipo de registro?
==========================================

Depois do registro efetivado, você já possui uma prova legal de autenticidade. Para reforçar a validade jurídica de contratos, as partes envolvidas podem comprovar sua ciência e concordância sobre o conteúdo registrado, garantindo validade jurídica internacional para o seu registro.

Além disso, a justiça brasileira já faz uso de assinaturas digitais e certificados digitais no cotidiano.

Você já possui uma prova legal de autenticidade pois um documento assinado digitalmente e certificado em uma rede pública de maneira irrevogável, com conhecimento e concordância de todas as partes envolvidas sobre o conteúdo registrado,pode ser considerado prova adicional e complementar em casos de disputa.

A rede bitcoin, por exemplo, funciona de forma autônoma, sem um banco de dados central ou único administrador central. O blockchain é executado e mantido coletivamente por diversos nós da rede peer-to-peer para registrar as transações, e usa criptografia de código aberto para prover funções básicas de segurança para certificar que bitcoins só podem ser gastos pelo dono e evitar gastos duplos, falsificação e adulteração de bancos de dados. 

Embora não exista jurisprudência, já existe precedência. Há pelo menos uma liminar deferida em favor das provas, onde a coleta de provas digitais foi feita utilizando a ferramenta de Prova de Autenticidade para Conteúdo Web, com a autenticidade dos documentos gerados sido efetuada em blockchain: Processo n. 1030978-75.2016.8.26.0100

=============================================================================================
Este BitRegistro substitui o registro em cartório ou o registro de marcas e patentes no INPI?
=============================================================================================

Atualmente, este registro ainda não exclui a necessidade de registro nos órgãos oficiais e do governo, mas serve de respaldo e contra-prova em casos de disputa enquanto os meios oficiais não oferecem uma forma rápida e eficiente de validar a autenticidade da informação.

=================================================
Vocês armazenam cópias do meu documento original?
=================================================

Seus documentos e informações NÃO são armazenados nos nossos bancos de dados ou no Blockchain.

Armazenamos somente a assinatura digital (identidade criptográfica) do seu documento, que é uma assinatura única e exclusiva, reconhecida somente a partir do documento original.

Do documento original é possível recriar a assinatura digital, mas a partir da assinatura digital é impossível recriar o documento original.

==========================================================================================
Caso o site OriginalMy.com deixe de existir, é possível confirmar meu certificado digital?
==========================================================================================

Mesmo que este site não esteja disponível, o seu certificado ficará registrado no blockchain para sempre, de maneira irrevogável.É possível checar seu certificado diretamente no blockchain utilizando seu Código de Transação e o documento original.

