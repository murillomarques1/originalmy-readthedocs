Blockchains e verificação de registros
======================================

=========================================================
Calcular manualmente a assinatura digital (*hash* SHA256)
=========================================================

O que é um *hash*
-----------------

O *hash*, também conhecido como *checksum* ou **assinatura digital**, é uma informação que resulta do cálculo feito por um algorítmo de criptografia em um arquivo fornecido.

O algorítmo lê todos os *bits* de um arquivo e calcula uma informação única e exclusiva que representa o mesmo arquivo. É como se ele calculasse o DNA do arquivo, onde cada arquivo diferente possui o seu e nunca dois arquivos com conteúdos diferentes possuirão o mesmo DNA.

Isso significa que ao ler o mesmo arquivo novamente, ele irá resultar na mesma assinatura digital. Caso seja calculado uma assinatura digital diferente, significa que o arquivo sofreu alterações.

O algorítmo utilizado pelo OriginalMy para calcular a assinatura digital dos documentos é o SHA256, que é o mesmo algorítmo presente nos certificados e-CPF e e-CNPJ homologados pelo governo.

Como calcular manualmente a assinatura digital
----------------------------------------------

Abra o terminal no seu computador:

- Mac ::
    
  # shasum -a 256 <nome_do_arquivo>
 
- Linux ::

  # sha256sum <nome_do_arquivo>
  
- Windows

  O windows não possui qualquer ferramenta nativa para calcular a assinatura digital de documentos. 
  * Pode ser feita a instalação de uma ferramenta no PowerShell: https://gallery.technet.microsoft.com/PowerShell-File-Checksum-e57dcd67
  * Ou a utilização de alguma ferramenta online, como http://www.conversion-tool.com/sha256
  
O que o OriginalMy faz com essa assinatura digital?
---------------------------------------------------

O OriginalMy efetua a certificação dessa assinatura digital, calculada a partir do documento fornecido pelo usuário, em diversos blockchains, públicos e/ou privados.

No momento em que o blockchain confirma o registro de autenticidade, ele recebe um carimbo de tempo (*timestamp*) que comprova o momento da certificação.

Como os blockchains públicos tem como premissa a imutabilidade e transparência, o registro da assinatura digital nunca mais poderá ser removido ou alterado, servindo de prova de que naquele momento certo documento digital existia. E ainda pode ser consultado livremente 24 horas por dia, 7 dias por semana, gratuitamente.

==================
Bitcoin Blockchain
==================

Sobre
-----

O Blockchain do Bitcoin foi o primeiro blockchain a ser construído (ou descoberto, dependendo do ponto de vista). Quando o OriginalMy foi desenvolvido, ainda não existiam tecnologias blockchain que estivessem funcionando de maneira estável por tanto tempo, com uma equipe de desenvolvimento consistente e ativa.

Por este motivo a plataforma foi inicialmente desenvolvida com base neste blockchain

Como verificar
--------------

* Entre no site Blockchain.info e cole o Código da Transação na caixa de busca (Search).

* Em Scripts, clique em 'Show scripts & coinbase' para exibir o campo 'Output Scripts'.

* Encontre a linha OP_RETURN e confira a assinatura digital do documento.

  Alguns serviços como Coin Secrets ou blockchain.info's list podem ajudar a localizar transações OP_RETURN mais facilmente.

.. note:: A existência dessa transação no Blockchain prova que o documento existiu no momento da transação e foi incluída junto ao bloco


===================
Ethereum Blockchain
===================

Sobre
-----

O registro de autenticidade nos blockchains com tecnologia Ethereum são feitos através de aplicações descentralizadas, desenvolvidas exclusivamente para este fim.

Como verificar
--------------

Endereços: https://github.com/OriginalMy/originalmy-dapp-addresses/blob/master/contract-addresses.js

Funções dos smart-contracts: https://github.com/OriginalMy/originalmy-dapp-addresses

===========================
Ethereum Classic Blockchain
===========================

Sobre
-----

Em 16/Jun/2017 optamos por migrar todos os smart-contracts para Ethereum Classic devido à elevação do preço do Ethereum, tempo de bloco e problemas com transações que desapareciam.

O registro nos blockchains com tecnologia Ethereum Classic são feitos através de aplicações descentralizadas, desenvolvidadas exclusivamente para este fim.

Como verificar
--------------

Endereços: https://github.com/OriginalMy/originalmy-dapp-addresses/blob/master/contract-addresses.js

Funções dos smart-contracts: https://github.com/OriginalMy/originalmy-dapp-addresses

=================
Decred Blockchain
=================

Sobre
-----

O registro de autenticidade em Blockchain Decred é feito através de um método chamado *pool de registros* ou **registro compartilhado**. Este método utiliza uma versão customizada do projeto Drctime, que se baseou no OpenTimestamps para sua construção.

Não são feitos registros de autenticidade individuais nesse blockchain. As assinaturas digitais são acumuladas e depois de certo tempo, elas são agrupadas e somente um registro, que representa todo o bloco, é gravado no blockchain.

Ele funciona da seguinte maneira:

- No espaço de uma hora, o sistema acumula todos as assinaturas digitais registradas
- De hora em hora ele agrupa todos os registros naquele intervalo e calcula uma assinatura digital para o bloco, que  chamada de merkle tree.
- A assinatura digital (merkle tree) do bloco de assinaturas digitais é registrada no blockchain


Como verificar
--------------

* Entre no site https://mainnet.decred.org e cole o Código da Transação na caixa de busca (Search).

* Abaixo de *Details*, clique no sinal +

* Encontre a linha OP_RETURN e confira o merkle tree fornecido.


============
Curiosidades
============

.. note:: O registro e assinatura de contratos acontece somente na rede Ethereum Classic

.. note:: A cada novo cadastro, com email validado, o usuário do OriginalMy ganha um voucher com *registros free*, que acontece somente na rede Decred.

.. note:: O registro na rede Decred faz uso de uma rede centralizada, porém aberta e pública. É centralizada porque precisa agrupar os registros por um certo período de tempo.
