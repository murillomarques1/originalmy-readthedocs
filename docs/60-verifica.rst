Verificando registros no Blockchain
===================================

===================================================
Calcular o *hash* (SHA256) manualmente do documento
===================================================

O que é um *hash*
-----------------

O *hash*, também conhecido como *checksum* ou **registro de autenticidade**, é uma informação que resulta do cálculo feito por um algorítmo de criptografia em um arquivo fornecido.

O algorítmo lê todos os *bits* de um arquivo e calcula uma informação única e exclusiva que representa o mesmo arquivo. É como se ele calculasse o DNA do arquivo, onde cada arquivo diferente possui o seu e nunca dois arquivos com conteúdos diferentes possuirão o mesmo DNA.

Isso significa que ao ler o mesmo arquivo novamente, ele irá resultar no mesmo registro de autenticidade. Caso seja calculado um registro de autenticidade diferente, significa que o arquivo sofreu alterações.

O algorítmo utilizado pelo OriginalMy para calcular o registro de autenticidade dos documentos é o SHA256, que é o mesmo algorítmo presente nos certificados e-CPF e e-CNPJ homologados pelo governo.

Como verificar o registro de autenticidade manualmente
------------------------------------------------------

Abra o terminal no seu computador:

- Mac ::
    
  # shasum -a 256 <nome_do_arquivo>
 
- Linux ::

  # sha256sum <nome_do_arquivo>
  
- Windows

  O windows não possui qualquer ferramenta nativa para calcular o hash de documentos. 
  * Pode ser feita a instalação de uma ferramenta no PowerShell: https://gallery.technet.microsoft.com/PowerShell-File-Checksum-e57dcd67
  * Ou a utilização de alguma ferramenta online, como http://www.conversion-tool.com/sha256


==================
Bitcoin Blockchain
==================

* Entre no site Blockchain.info e cole o Código da Transação na caixa de busca (Search).

* Em Scripts, clique em 'Show scripts & coinbase' para exibir o campo 'Output Scripts'.

* Encontre a linha OP_RETURN e confira a assinatura digital do documento e logo após nosso marcador 0x4f5249474d59 (ORIGMY em ascii).

  Alguns serviços como Coin Secrets ou blockchain.info's list podem ajudar a localizar transações OP_RETURN mais facilmente.

.. note:: A existência dessa transação no Blockchain prova que o documento existiu no momento da transação e foi incluída junto ao bloco


===================
Ethereum Blockchain
===================

===========================
Ethereum Classic Blockchain
===========================

=================
Decred Blockchain
=================
