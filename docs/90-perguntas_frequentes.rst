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

Depois do registro efetivado, você já possui uma prova legal de autenticidade. Para reforçar a validade jurídica de contratos, as partes envolvidas podem comprovar sua ciência e concordância sobre o conteúdo certificado, garantindo validade jurídica internacional para o seu registro.

Além disso, a justiça brasileira já faz uso de assinaturas digitais e certificados digitais no cotidiano.

Você já possui uma prova legal de autenticidade pois um documento assinado digitalmente e certificado em uma rede pública de maneira irrevogável, com conhecimento e concordância de todas as partes envolvidas sobre o conteúdo certificado, pode ser considerado prova adicional e complementar em casos de disputa.

A rede bitcoin, por exemplo, funciona de forma autônoma, sem um banco de dados central ou único administrador central. O blockchain é executado e mantido coletivamente por diversos nós da rede peer-to-peer para registrar as transações, e usa criptografia de código aberto para prover funções básicas de segurança para certificar que bitcoins só podem ser gastos pelo dono e evitar gastos duplos, falsificação e adulteração de bancos de dados. 

Embora não exista jurisprudência, já existe precedência. Há pelo menos uma liminar deferida em favor das provas, onde a coleta de provas digitais foi feita utilizando a ferramenta de Prova de Autenticidade para Conteúdo Web, com a autenticidade dos documentos gerados sido efetuada em blockchain: Processo n. 1030978-75.2016.8.26.0100

=============================================================================================
Este BitRegistro substitui o registro em cartório ou o registro de marcas e patentes no INPI?
=============================================================================================

Atualmente, esta certificação ainda não exclui a necessidade de registro nos órgãos oficiais e do governo, mas serve de respaldo e contra-prova em casos de disputa enquanto os meios oficiais não oferecem uma forma rápida e eficiente de validar a autenticidade da informação.

=================================================
Vocês armazenam cópias do meu documento original?
=================================================

Seus documentos e informações neles contidas NÃO são armazenados nos nossos bancos de dados ou no Blockchain.

Armazenamos somente a assinatura digital (identidade criptográfica) do seu documento, que é uma assinatura única e exclusiva, reconhecida somente a partir do documento original.

Do documento original é possível recriar a assinatura digital, mas a partir da assinatura digital é impossível recriar o documento original.

==========================================================================================
Caso o site OriginalMy.com deixe de existir, é possível confirmar meu certificado digital?
==========================================================================================

Mesmo que este site não esteja disponível, o seu certificado ficará registrado no blockchain para sempre, de maneira irrevogável. É possível checar seu certificado diretamente no blockchain utilizando seu Código de Transação e o documento original.

=====================================================================
Registro de Autenticidade e Certificação de Contrato é a mesma coisa?
=====================================================================

Não. O **Registro de Autenticidade** é para arquivos digitais que não necessitam de nenhum signatário, é somente a certificação para comprovar que o documento é autêntico e ter o carimbo de tempo do momento em que foi certificado. A **Certificação de Contrato** é utilizada quando obrigatoriamente pessoas precisam assinar o documento. Tendo um ou mais signatários, sempre deverá ser certificado utilizando a Certificação de Contrato.

===========================================================================================
Adicionei por engano um contrato no Registro de Autenticidade, posso adicionar signatários?
===========================================================================================

Caso ainda não tenha feito o pagamento, é possível submeter o mesmo documento na área para Certificação de Contrato e adicionar os signatários. Se já tiver feito o pagamento, não é possível adicionar nenhum signatário.

================================================================================================================
Certifiquei meu contrato utilizando o Registro de Autenticidade e não consigo adicionar os signatários. E agora?
================================================================================================================

Será necessário enviar um novo documento. Qualquer alteração por menor que seja, modificará a Identidade do documento. Abrir o arquivo e clicar em "Salvar" já é considerada uma modificação. Utilize este arquivo modificado para gerar um novo PDF e fazer a **Certificação de Contrato** com os signatários.

=======================================================================================
Depois de certificar o contrato eu consigo adicionar, remover ou trocar os signatários?
=======================================================================================

Caso ainda não tenha feito o pagamento, é possível adicionar, remover ou trocar os signatários. Caso já tenha pago, não será possível adicionar, remover ou trocar os signatários. A Certificação de Contrato no Blockchain funciona da mesma forma como no mundo físico. Exemplo: Um contrato em papel registrado na Junta Comercial, não pode ter somente a página com os signatários alterada e continuar válido. Qualquer alteração significa modificar o documento inteiro e fazer um **NOVA** certificação. 

====================================================================================
Nem todos os signatários estão com o aplicativo instalado, eu vou conseguir assinar?
====================================================================================

Não. O contrato somente será enviado para o Blockchain depois que todos os signatários estiverem com o aplicativo instalado e com o cadastro validado. No mundo físico, este procedimento é equivalente à qualificação das partes, ou seja, é o momento em que são apresentadas as informações do signatário como: nome completo e número dos documentos. Sem identificar quem são todos os signatários, não é possível fazer a assinatura pois o contrato estará incompleto.

======================================
Como eu saberei se todos já assinaram?
======================================

Há três formas de verificação. Uma é fazer a consulta diretamente pelo aplicativo, no campo: "Assinado por todos" vai aparecer "Sim" ou "Não". A segunda forma é submetendo o documento original sem alterações na plataforma da OriginalMy para verificar as informações disponíveis sobre o registro. A  terceira forma é aguardar o recebimento por e-mail do "Certificado de Assinatura de Documento".

=================================================================================
Recebi um email dizendo que tenho um contrato para assinar, o que isso significa?
=================================================================================

Significa que um contrato foi registrado no blockchain e está aguardando sua assinatura. Para assinar, obrigatoriamente você precisa ter uma cópia do contrato.

=========================================================
Por que preciso preencher o PIN para assinar um contrato?
=========================================================

Este é um mecanismo de segurança para comprovar que no momento da assinatura, você estava em posse do documento original e assim pode ter certeza da versão do documento que está assinando. 

============================================
Onde encontro o PIN para assinar o contrato?
============================================

Existem duas formas para conseguir o PIN para assinatura do contrato. 1- Pelo computador: faça login na OriginalMy e submeta o contrato a ser assinado. Será mostrado o PIN para assinatura e a quantidade de signatários do contrato. 2 - Pelo smartphone: faça download do contrato e selecione "Abrir com" "Assinar Documentos", o PIN será preenchido automaticamente no aplicativo.

==============================================================
Posso usar sempre o mesmo PIN para assinar todos os contratos?
==============================================================

Não. Cada contrato tem um PIN próprio.

====================================================================================
Decidi não assinar o contrato que já foi registrado no blockchain, o que devo fazer?
====================================================================================

Basta não assinar o contrato. Mesmo que ele já tenha sido registrado no blockchain, sem a assinatura dos signatários, o contrato não terá validade.

==================================
Para onde irão minhas informações?
==================================

Ao submeter um documento na plataforma da OriginalMy, é calculada a Identidade do documento e esta identidade é registrada no Blockchain. Hoje utilizamos os blockchains das redes Bitcoin, Ethereum, Ethereum Classic e Decred. Somente o identidade do documento é registrada no blockchain e não temos contato com o conteúdo do documento dos nossos clientes.

=======================================================
O Blockchain garante que o registro nunca será perdido?
=======================================================

Uma vez registrado no blockchain, nunca mais este registro poderá ser modificado ou apagado, então para sempre a identidade do seu documento ficará gravada no blockchain. No caso da descontinuidade do suporte em algum dos blockchains públicos utilizados, nós temos a guarda dos nós com histórico completo das redes para a continuidade do negócio.

====================================================================
Perdi o documento original, a OriginalMy pode me fornecer uma cópia?
====================================================================

Não. A OriginalMy não armazena cópia dos documentos, a responsabilidade sobre a guarda dos documentos é do próprio cliente. 

===============================================================================
Existe alguma forma de consultar os dados do registro sem o documento original?
===============================================================================

Sim. Caso tenha a "Assinatura Digital" do documento, é possível fazer a consulta das informações sobre o registro acessando: https://originalmy.com/bitregistro/(colar a assinatura digital do documento). Exemplo: https://originalmy.com/bitregistro/7f418cb198376fd1314a71fc6bfe6d2ef41246f90c91797a648b5851a9b19129

===========================================================
Onde posso encontrar a Assinatura Digital do meu documento?
===========================================================

Ao submeter o documento na plataforma da OriginalMy, é calculada a Assinatura Digital do documento e aparecerá na tela a mesma Assinatura Digital todas as vezes que o documento sem alterações for submetido na plataforma.

=============================================================================
Posso guardar apenas a Assinatura Digital e não guardar o documento original?
=============================================================================

Não. A Assinatura Digital mostrará apenas os dados referentes ao registro mas não informa nada sobre o conteúdo do documento. Sem o documento original, não é possível identificar ao que se refere o registro.

=======================================================================================================
Para outra pessoa verificar a autenticidade do meu documento, eu preciso fornecer meus dados de acesso?
=======================================================================================================

Não. Seus dados de acesso não devem ser compartilhados em hipótese alguma. A única coisa que pode ser compartilhada é o documento original após o registro. Para outra pessoa fazer a consulta, ela deve criar a própria conta na OriginalMy e depois submeter o seu documento para visualizar todos os dados do registro.

=================================
Como é realizada a autenticidade?
=================================

Qualquer alteração no documento, mudará a Identidade dele, ou seja, a Assinatura Digital calculada será diferente do documento anterior. Somente o documento original sem alterações, gerará a mesma Assinatura Digital e ela será a sua garantia de que o documento é autêntico e não sofreu nenhuma alteração. A autenticidade é garantida através do algoritmo de assinatura digital que é o mesmo homologado pelo ICP-BR.

===================================================
O que garante que eu sou o dono daquela informação?
===================================================

A comprovação de autoria se dá através do nosso método de identificação e emissão de Identidade Blockchain. Além disso, o ideal é que seja feito o registro antes de dar publicidade ao documento, assim, você garante a precedência do seu registro.

===============================================================================================
O que acontece se outra pessoa registrar um documento igual ao meu, dizendo que pertence a ela?
===============================================================================================

O blockchain fornece o timestamp (carimbo de tempo) do momento do registro, publicamente. Mesmo que haja um registro posterior, pode-se facilmente comprovar a precedência, ou seja, qual é o registro mais antigo daquela informação.

===============================================
Posso registrar um imóvel apenas no Blockchain?
===============================================

Não. Para registro de imóveis existe uma legislação específica, não é possível fazer o registro somente em blockchain pois não terá validade jurídica. 

====================================================================================================
Fiz o pagamento em Bitcoin através de uma exchange e meu registro não foi efetuado, o que aconteceu?
====================================================================================================

Quando o pagamento é efetuado através de uma exchange, eles cobram uma taxa de transação. Se o valor selecionado para transferência for exatamente o valor do registro, a taxa será debitada do valor do registro e assim o sistema não consegue identificar o pagamento pois o valor recebido é diferente do esperado. Para que isso não aconteça, é preciso considerar a taxa e solicitar a transferência do valor do registro + taxa.

==================================================================
Qual o tamanho máximo que um arquivo pode ter para ser registrado?
==================================================================

A OriginalMy registra no blockchain somente a Assinatura Digital do documento que sempre terá o mesmo tamanho de 64 caracteres. O que limita o tamanho do arquivo, é a memória do computador que está sendo utilizado para gerar a assinatura digital que é obtida através de cálculos matemáticos. Sendo assim, o que determinará o tamanho máximo do arquivo, é a memória do computador do usuário.

===================================================================
A certificação na OriginalMy substitui o "Reconhecimento de Firma"?
===================================================================

Não. O que pode ser feito é uma verificação se para o documento em questão, existe uma necessidade legal do reconhecimento de firma ou se é solicitado apenas por hábito. 

===================================================================
Como eu crio um documento ideal para ser certificado na OriginalMy?
===================================================================

Você pode criar um documento PDF contendo todas as informações que considerar importantes. Neste documento, escreva tudo que precisa ser descrito, coloque imagens, fotos, gráficos ou qualquer outra informação que considerar relevante. Depois de certificado este documento não poderá ser alterado. Guarde cópias do documento em locais seguros.

====================================================================
As certificações em blockchain já estão sendo aceitos nos tribunais?
====================================================================

Até o momento temos o conhecimento de um caso em que provas foram coletadas utilizando a OriginalMy e o juiz deferiu uma liminar em favor das provas. Isso significa que as provas foram aceitas porém ainda não existe jurisprudência para a utilização do blockchain isoladamente.

======================================================================================
Tenho uma ideia incrível, se eu registrar na OriginalMy estou protegido contra plágio?
======================================================================================

Não. Não existe nenhum mecanismo legal que proteja ideias. Caso a ideia tenha evoluído para um projeto, ele pode ser registrado no OriginalMy para comprovar a autoria e te proteger contra concorrência desleal.

================================================================================
Como utilizo a OriginalMy para proteger minha ideia contra concorrência desleal?
================================================================================

O primeiro passo é descrever a ideia da forma mais detalhada possível num documento PDF e fazer o Registro de Autenticidade deste documento antes de dar publicidade a ideia. Como todo registro em blockchain, este documento terá uma Assinatura Digital. Quando for apresentar a ideia para alguém, o ideal é que todas as partes envolvidas assinem um Acordo de Não Divulgação (NDA) e neste acordo deve constar a Assinatura Digital gerada no Registro de Autenticidade. Assim, caso uma das partes utilize as informações divulgadas, você estará protegido pois a lei garante a proteção nesse tipo de caso. A assinatura do NDA pode ser feita utilizando a ferramenta para Registro de Contratos da OriginalMy.

===================================================
Posso fazer meu testamento utilizando a OriginalMy?
===================================================

Sim. Entre os vários tipos de testamentos, o que pode ser feito é o Testamento Particular (artigos 1876 a 1880 do Código Civil). Este modelo de testamento, dispensa o registro nas instituições tradicionais, mas precisa atender alguns requisitos.

================================================================================
Quais os requisitos para fazer um Testamento Particular utilizando a OriginalMy?
================================================================================

O documento deve ser escrito pelo próprio testador (dono do testamento). A escrita pode ser de próprio punho ou digitado. O documento deverá estar limpo e sem rasuras. Se for digitado, deve ser feito com escrita corrida, ou seja, com espaço entre as palavras mas sem separação de linhas e parágrafos. Este documento deve ser assinado por 4 pessoas, o próprio testador e mais 3 testemunhas de sua escolha. A assinatura do testador deve ser feita na presença das testemunhas. O testador deve ler o testamento para as testemunhas e após a leitura, elas assinam. Após a morte do testador, alguém avisa ao juiz que existe o testamento particular. O juiz perguntará individualmente para cada testemunha se o testamento foi lido para ela, se a pessoa se recorda de detalhes e se reconhece a assinatura. Se pelo menos uma das testemunhas fizer as três confirmações, o testamento é considerado válido. O testamento deve ser registrado utilizando o **Registro de Contrato** e os CPFs para assinatura devem ser do testador e das 3 testemunhas. A ordem das assinaturas deve obedecer o descritivo acima: primeiro o testador assina na frente das testemunhas, faz a leitura do testamento e em seguida todas as testemunhas assinam. 








