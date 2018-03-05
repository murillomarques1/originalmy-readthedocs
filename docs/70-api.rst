API para integração com sistemas
================================

.. note:: Esta documentação pode ser encontrada online, inclusive com testes na live testnet neste link: https://signcontracts-mobile-api-stag.herokuapp.com/docs/

Documentação de API para registro de documentos e integração com o APP de Assinatura de Contratos em Blockchain OriginalMy.com

Todos os registros de teste acontecem nas Testnets públicas dos blockchains, todas as transações e endereços de wallet podem ser verificados na testnet de cada uma das redes: Bitcoin_ - Ethereum_ - Decred_

O APP Android de exemplo pode ser baixado em https://s3-sa-east-1.amazonaws.com/originalmy-app-staging/originalmy-app-testnet.apk

Contratos podem ser lançados também diretamente na plataforma online: https://originalmy-frontend-staging.herokuapp.com/index utilizando o voucher 23N9-6WCR-SEMV na tela de pagamento

Caso não tenha uma Chave de Acesso para uso da API, solicite através do email: contato@originalmy.com


.. _Bitcoin: https://blocktrail.com/tBTC
.. _Ethereum: https://rinkeby.etherscan.io
.. _Decred: https://testnet.decred.org


=========
Contratos
=========

Checar contratos pendentes de assinatura pelo Usuário
-----------------------------------------------------

Method: GET

Endpoint: http://testnet.originalmy.com/api/v1/check_contracts

Parameters:

+--------+--------+-------------------------------------------------------+
| Campo  | Tipo   | Descrição                                             |
+========+========+=======================================================+
| wallet | String | Chave pública: Ex. n3kCWWf5V5yWTjvQbQuchh4a57Gv7oaGCH |
+--------+--------+-------------------------------------------------------+

Exemplo de retorno:

:: 

  [
    {
      "indice": 0,
      "pin": 1312,
      "tx": "0x3267777798327c65f6d8391a2446f08a6e3945d78c3b329be42630c8666c40f0",
      "wallet_to": "1BQCWzjn4dfvE1gVcCiKkMxRETp3qzQUBu",
      "blockstamp": "2017-07-24 19:24:18",
      "alias": "seg1",
      "digest": "fe843c81998ee01a4eedb1ea9b50289f39bd0da23e25043e2a5622ab57e703d4"
    },
    {
      "indice": 0,
      "pin": 9800,
      "tx": "0x4ae288b763170a698b6d6f35105e75ad3eda08ff6c007124c33b78813435e214",
      "wallet_to": "18A21L8Qw8eUrq7QVvVacguQScYGwyEpHT",
      "blockstamp": "2017-07-24 23:26:21",
      "alias": "seg3",
      "digest": "3f906b2ce58702a18c98da316616d673e5c8e571d340caecc7d0006883741e5f"
    }
  ]
  
Listar todos os contratos para o usuário
----------------------------------------

Method: GET

Endpoint: http://testnet.originalmy.com/api/v1/check_all_contracts

Parameters:

+--------+--------+-------------------------------------------------------+
| Campo  | Tipo   | Descrição                                             |
+========+========+=======================================================+
| wallet | String | Chave pública: Ex. n3kCWWf5V5yWTjvQbQuchh4a57Gv7oaGCH |
+--------+--------+-------------------------------------------------------+

Exemplo de retorno:

:: 

  [
    {
      "blockstamp": "2017-05-20 05:22:27",
      "tx": "0x3a0553a001581a3428b4193689108501d40bc42844d0a6c83e65f25da134f3dd",
      "signed": false,
      "alias": "sexta24",
      "order": 0,
      "digest": "7f3f18d6cc3050df0519cd0deb74314e295d0c032d5861d0b04dea5bd342b149"
    },
    {
      "blockstamp": "2017-05-20 06:04:03",
      "tx": "0xf112549be7a41feaa05bd47e8e859065168d78eb158c0cf99efb01778d48b08a",
      "signed": true,
      "alias": "sexta23",
      "order": 1,
      "digest": "7aa1f26bedc11cf9828ce18b2e221d16114916af080a94402c361ac00d4a8859"
    },
    {
      "blockstamp": "2017-07-24 19:24:18",
      "tx": "0x3267777798327c65f6d8391a2446f08a6e3945d78c3b329be42630c8666c40f0",
      "signed": false,
      "alias": "seg1",
      "order": 0,
      "digest": "fe843c81998ee01a4eedb1ea9b50289f39bd0da23e25043e2a5622ab57e703d4"
    },
    {
      "blockstamp": "2017-05-22 18:53:37",
      "tx": "0xd8b83b6132f14b45ac8686d620a912c70814e4a56bd5614fdc53e3b161f2c6ef",
      "signed": false,
      "alias": "contrato2",
      "order": 0,
      "digest": "a090394ab6ec5b6e908eade569cba86028694c968112cd9b0b8962060b2d1101"
    }
  ]
  
Registro de Contratos
---------------------

Method: GET

Endpoint: http://testnet.originalmy.com/api/v1/company/register-contract

Parameters:

+--------+--------+-------------------------------------------------------------------------------+
| Campo  | Tipo   | Descrição                                                                     |
+========+========+===============================================================================+
| k      | String | Chave de acesso. Exemplo: XXXX-XXXX-XXXXX                                     |
+--------+--------+-------------------------------------------------------------------------------+
| d      | String | Digest SHA256 do PDF do contrato                                              |
|        |        | Exemplo: bc745fc1322b23deeb13c1c9eb18d8aae5de03c6e235ea5e88bad0cb0ed85a16     |
+--------+--------+-------------------------------------------------------------------------------+
| s      | String | Usuários (CPFs separados por vírgula, sem espaço e pontuação)                 |
|        |        | Exemplo: 41344264484,85218453838 ou                                           |
|        |        | [{“signer”: "41344264484", “order”: 1},{“signer”: "85218453838", “order”: 2}] |
+--------+--------+-------------------------------------------------------------------------------+
| a      | String | Alias para o documento, como título ou ID. Limite de 10 caracteres.           |
|        |        | Exemplo: Contrato10                                                           |
+--------+--------+-------------------------------------------------------------------------------+

.. note:: Colocar os CPFs em ordem, separados por vírgula faz com que o documento apareça ao mesmo tempo para todos os signatários. Utilizar o *array* com o order, determinar a hierarquia de assinaturas.

.. note:: o parâmetro *order* deve sempre começar com 1, sendo 1 para o primeiro signatário e *n* para o último.

Exemplo de retorno:

:: 

  {
      "signers": [
          {
              "signer": "41344264484",
              "account": true,
              "order": 1
          },
          {
              "signer": "85218453838",
              "account": false,
              "order": 2
          }
      ],
      "digest": "a090394ab6ec5b6e908eade569cba86028694c968112cd9b0b8962060b2d1102",
      "success": true,
      "quota": 111
  }
  
Verificação do status do contrato
---------------------------------

Method: GET

Endpoint: http://testnet.originalmy.com/api/v1/status

Parameters:

+--------+--------+-------------------------------------------------------------------------------+
| Campo  | Tipo   | Descrição                                                                     |
+========+========+===============================================================================+
| d      | String | Digest SHA256 do PDF do contrato                                              |
|        |        | Exemplo: a090394ab6ec5b6e908eade569cba86028694c968112cd9b0b8962060b2d1101     |
+--------+--------+-------------------------------------------------------------------------------+

Exemplo de retorno:

:: 

  {
      "status": "confirmed",
      "blockstamp": "2017-07-25 17:50:35",
      "transaction": "0x0e68819506081bcbd2c3d1af97be3e7d25906a0e854c56e8830f21e8e1fcfa82",
      "contract": {
          "alias": "ter1",
          "length": 2,
          "signed": false,
          "signers": [
              {
                  "user_id": "41344264484",
                  "signed": false
              },
              {
                  "user_id": "85218453838",
                  "signed": false
              }
          ]
      },
      "success": true,
      "networks": [
        {
            "blockstamp": "2017-07-19 23:09:42",
            "transaction": "0x1e99d2d7a2038f1138b907f954a6fa2f9bd073a1ef22b678aa25e7a6c0ab2c0c",
            "link": "https://rinkeby.etherscan.io/tx/0x1e99d2d7a2038f1138b907f954a6fa2f9bd073a1ef22b678aa25e7a6c0ab2c0c",
            "name": "eth",
            "txstamp": "2017-07-19 23:09:13.881940"
        },
        {
            "blockstamp": "2017-07-20 00:01:14",
            "transaction": "7a6d22a92028ec20826fbea44b3f8556dee5035c9c69ca12db7b0032bc4af105",
            "name": "dcr",
            "link": "https://testnet.decred.org/tx/7a6d22a92028ec20826fbea44b3f8556dee5035c9c69ca12db7b0032bc4af105",
            "merkle": "b985a1f338c5299d1c5bd60e4818c214ce520a1da16e416dc8bca61a2e111451",
            "txstamp": "2017-07-20 00:00:00"
        }
      ],
      "txstamp": "2017-07-25 17:50:10.070350"
  }

========================
Contratos sem KYC
========================

Assinatura de contratos
-----------------------

Method: POST

Endpoint: https://api1.testnet.originalmy.com/company/contract/sign

Headers:

+---------------+--------+------------------------------------------------+
| Campo         | Tipo   | Descrição                                      |
+===============+========+================================================+
| authorization | String | Chave de API (BASE64)                          |
+---------------+--------+------------------------------------------------+

Parameters:

+---------------------+--------+----------------------------------------------------------------------------+
| Campo               | Tipo   | Descrição                                                                  |
+=====================+========+============================================================================+
| contract[block]     | String | Bloco com a assinatura digital gerado com a OriginalMy LibCrypto           |
+---------------------+--------+----------------------------------------------------------------------------+
| contract[walletId]  | String | Chave pública do usuário que está assinando                                |
+---------------------+--------+----------------------------------------------------------------------------+
| contract[digest]    | String | Hash SHA256 do contrato                                                    |
+---------------------+--------+----------------------------------------------------------------------------+
| contract[document]  | String | CPF do usuário que está assinando                                          |
+---------------------+--------+----------------------------------------------------------------------------+
| contract[timestamp] | String | Timestamp do momento da assinatura                                         |
+---------------------+--------+----------------------------------------------------------------------------+
| contract[config]    | Object | Objeto com a dificuldade e o token recebido no request /company/difficulty |
+---------------------+--------+----------------------------------------------------------------------------+

Exemplo de request:

::

  curl --request POST \
    --url 'https://api1.testnet.originalmy.com/company/contract/sign' \
    --header 'Authorization: VEVTVC1FMTIzLTEyMzQ=' \
    --header 'Content-Type: application/json' \
    --data '{
    "contract": {
      "block": "331c4bf614d3817f85a9b01fa1bb3966c4c6c4a05d2407cac78356789f4de02a;42228411370;2018-03-02T19:21:35.600Z;mxVyE3JdBkKKgNPDkymVWtyDH6csYwjLfi;IGQ+YAH68eqvNO2iqjyNML177KjHLAmgH1lnmbUwD01FV3ZmZ/swlvdHVsjageeFuovJg1Yk8K5hSt3hdeq2qlo=;298",
      "walletId": "mxVyE3JdBkKKgNPDkymVWtyDH6csYwjLfi",
      "digest": "331c4bf614d3817f85a9b01fa1bb3966c4c6c4a05d2407cac78356789f4de02a",
      "document": "42228411370",
      "timestamp": "2018-03-02T19:21:35.600Z",
      "config": {
              "key": "difficulty",
              "value": "2",
              "token": "CUlQM51RKtHkDHNuvPeYUboD8nATu1aBKumCgHZITcKuArYlJP79ZKUbGuTDi1wldscyYsjKN65t10R7wYbY9fYETzrruScrKYiabXq9q5qy3lIR9xQ47iLkKOoN4HaSHSBMPnw5nTIlwBhcjDwxGfGDlKHaIJQOMwSkdBb2zO3FPVp8MdLythL9aFzYTVjqD8wJhvmO9zEmJsowPeND5N1KG1KpoSwcoSrs2OSNCJw2ZDviiDvuYxCSmaEspnRo"
          }
    }
  }'

Exemplo de retorno:

:: 

  {
      "status": "success",
      "data": {
          "message": "Contrato assinado com sucesso"
      }
  }

Checagem do status de um contrato
---------------------------------

Method: GET

Endpoint: https://api1.testnet.originalmy.com/company/contract/status/:digest

Headers:

+---------------+--------+------------------------------------------------+
| Campo         | Tipo   | Descrição                                      |
+===============+========+================================================+
| authorization | String | Chave de API (BASE64)                          |
+---------------+--------+------------------------------------------------+

Exemplo de request:

::

  curl --request GET \
  --url 'https://api1.testnet.originalmy.com/company/contract/status/331c4bf614d3817f85a9b01fa1bb3966c4c6c4a05d2407cac78356789f4de02a' \
  --header 'Authorization: VEVTVC1FMTIzLTEyMzQ='

Exemplo de retorno:

:: 

  {
      "status": "success",
      "data": {
          "contract": {
              "status": "confirmed",
              "blockstamp": "2018-03-02 18:32:21",
              "transaction": "0x30efa6e2a0ac079ccb8b6bc902f193af612113b76de09a8f6a125fe9f04f3aaa",
              "contract": {
                  "alias": "TESTE",
                  "length": 2,
                  "signed": false,
                  "signers": [
                      {
                          "user_id": "33492543731",
                          "signed": false
                      },
                      {
                          "user_id": "42228411370",
                          "signed": false
                      }
                  ]
              },
              "success": true,
              "networks": [
                  {
                      "blockstamp": "2018-03-02 18:32:21",
                      "transaction": "0x30efa6e2a0ac079ccb8b6bc902f193af612113b76de09a8f6a125fe9f04f3aaa",
                      "link": "https://rinkeby.etherscan.io/tx/0x30efa6e2a0ac079ccb8b6bc902f193af612113b76de09a8f6a125fe9f04f3aaa",
                      "name": "eth",
                      "txstamp": "2018-03-02 18:32:02.283760"
                  }
              ],
              "txstamp": "2018-03-02 18:32:02.283760"
          }
      }
  }

Criação de um novo contrato
---------------------------

Method: POST

Endpoint: https://api1.testnet.originalmy.com/company/contract/register

Headers:

+---------------+--------+-------------------------------------------------------+
| Campo         | Tipo   | Descrição                                             |
+===============+========+=======================================================+
| authorization | String | Chave de API (BASE64)                                 |
+---------------+--------+-------------------------------------------------------+

Parameters:

+-------------------+----------+-------------------------------------------------+
| Campo             | Tipo     | Descrição                                       |
+===================+==========+=================================================+
| contract[alias]   | String   | Nome do contrato                                |
+-------------------+----------+-------------------------------------------------+
| contract[digest]  | String   | Hash SHA256 do contrato                         |
+-------------------+----------+-------------------------------------------------+
| contract[signers] | String[] | Array com o CPF de todos os signatários         |
+-------------------+----------+-------------------------------------------------+

Exemplo de request:

::

  curl --request POST \
    --url 'https://api1.testnet.originalmy.com/company/contract/register' \
    --header 'Authorization: VEVTVC1FMTIzLTEyMzQ=' \
    --header 'Content-Type: application/json' \
    --data '{
    "contract": {
      "alias": "TESTE",
      "signers": [
        "42228411370",
        "33492543731"
      ],
      "digest": "331c4bf614d3817f85a9b01fa1bb3966c4c6c4a05d2407cac78356789f4de02a"
    }
  }'

Exemplo de retorno:

:: 

  {
    "status": "success",
    "data": {
      "message": "Contrato registrado com sucesso"
    }
  }

Criação do BlockchainID
-----------------------

Method: POST

Endpoint: https://api1.testnet.originalmy.com/company/user/profile

Headers:

+---------------+--------+-------------------------------------------------------+
| Campo         | Tipo   | Descrição                                             |
+===============+========+=======================================================+
| authorization | String | Chave de API (BASE64)                                 |
+---------------+--------+-------------------------------------------------------+

Parameters:

+----------------+--------+-------------------------------------------------------+
| Campo          | Tipo   | Descrição                                             |
+================+========+=======================================================+
| user[walletId] | String | Chave pública da wallet do usuário                    |
+----------------+--------+-------------------------------------------------------+
| user[document] | String | Número do CPF do usuário                              |
+----------------+--------+-------------------------------------------------------+

Exemplo de request:

::

  curl --request POST \
    --url 'https://api1.testnet.originalmy.com/company/user/profile' \
    --header 'Authorization: VEVTVC1FMTIzLTEyMzQ=' \
    --header 'Content-Type: application/json' \
    --data '{
    "user": {
      "walletId": "mxVyE3JdBkKKgNPDkymVWtyDH6csYwjLfi",
      "document": "42228411370"
    }
  }'

Exemplo de retorno:

:: 

  {
    "status": "success",
    "data": {
      "message": "Identidade registrada com sucesso"
    }
  }

Listagem de contratos pendentes de um usuário
---------------------------------------------

Method: POST

Endpoint: https://api1.testnet.originalmy.com/company/contract/user/pending

Headers:

+---------------+--------+-------------------------------------------------------+
| Campo         | Tipo   | Descrição                                             |
+===============+========+=======================================================+
| authorization | String | Chave de API (BASE64)                                 |
+---------------+--------+-------------------------------------------------------+

Parameters:

+----------------+--------+-------------------------------------------------------+
| Campo          | Tipo   | Descrição                                             |
+================+========+=======================================================+
| user[walletId] | String | Chave pública da wallet do usuário                    |
+----------------+--------+-------------------------------------------------------+
| user[document] | String | Número do CPF do usuário                              |
+----------------+--------+-------------------------------------------------------+

Exemplo de request:

::

  curl --request POST \
    --url 'https://api1.testnet.originalmy.com/company/contract/user/pending' \
    --header 'Authorization: VEVTVC1FMTIzLTEyMzQ=' \
    --header 'Content-Type: application/json' \
    --data '{
    "user": {
      "walletId": "mxVyE3JdBkKKgNPDkymVWtyDH6csYwjLfi",
      "document": "42228411370"
    }
  }'

Exemplo de retorno:

:: 

  {
      "status": "success",
      "data": {
          "contracts": [
              {
                  "indice": 0,
                  "pin": 6276,
                  "tx": "0x30efa6e2a0ac079ccb8b6bc902f193af612113b76de09a8f6a125fe9f04f3aaa",
                  "wallet_to": "miXPRuFwB1UxbRcTb24MZeJtsrPXkSJ7i5",
                  "blockstamp": "2018-03-02 18:32:21",
                  "alias": "TESTE",
                  "digest": "331c4bf614d3817f85a9b01fa1bb3966c4c6c4a05d2407cac78356789f4de02a"
              }
          ]
      }
  }

Listagem de todos os contratos de um usuário
--------------------------------------------

Method: POST

Endpoint: https://api1.testnet.originalmy.com/company/contract/user/all

Headers:

+---------------+--------+-------------------------------------------------------+
| Campo         | Tipo   | Descrição                                             |
+===============+========+=======================================================+
| authorization | String | Chave de API (BASE64)                                 |
+---------------+--------+-------------------------------------------------------+

Parameters:

+----------------+--------+-------------------------------------------------------+
| Campo          | Tipo   | Descrição                                             |
+================+========+=======================================================+
| user[walletId] | String | Chave pública da wallet do usuário                    |
+----------------+--------+-------------------------------------------------------+
| user[document] | String | Número do CPF do usuário                              |
+----------------+--------+-------------------------------------------------------+

Exemplo de request:

::

  curl --request POST \
    --url 'https://api1.testnet.originalmy.com/company/contract/user/all' \
    --header 'Authorization: VEVTVC1FMTIzLTEyMzQ=' \
    --header 'Content-Type: application/json' \
    --data '{
    "user": {
      "walletId": "mxVyE3JdBkKKgNPDkymVWtyDH6csYwjLfi",
      "document": "42228411370"
    }
  }'

Exemplo de retorno:

:: 

  {
      "status": "success",
      "data": {
          "contracts": [
              {
                  "blockstamp": "2018-03-02 18:32:21",
                  "tx": "0x30efa6e2a0ac079ccb8b6bc902f193af612113b76de09a8f6a125fe9f04f3aaa",
                  "signed": false,
                  "alias": "TESTE",
                  "order": 1,
                  "digest": "331c4bf614d3817f85a9b01fa1bb3966c4c6c4a05d2407cac78356789f4de02a"
              }
          ]
      }
  }

Nível de dificuldade da plataforma para assinaturas
---------------------------------------------------

Method: GET

Endpoint: https://api1.testnet.originalmy.com/company/difficulty

Headers:

+---------------+--------+-------------------------------------------------------+
| Campo         | Tipo   | Descrição                                             |
+===============+========+=======================================================+
| authorization | String | Chave de API (BASE64)                                 |
+---------------+--------+-------------------------------------------------------+

Exemplo de request:

::

  curl --request GET \
    --url 'https://api1.testnet.originalmy.com/company/difficulty' \
    --header 'Authorization: VEVTVC1FMTIzLTEyMzQ='

Exemplo de retorno:

:: 

  {
      "status": "success",
      "data": {
          "config": {
              "key": "difficulty",
              "value": "2",
              "token": "eoVAcBFTF4h3KDfzA9275PDfnMEQ4O0lp8xpacik8K0oUx1isM7x3U03j5tP1qGC2WCKKtIJXNgHQjNYp4pBv3vfnLSfuP6gYiztfNGIhKgvwpcxqSeLj93Yk77rhZhpmYfgISzjGFMGHs3KVQSKOc4pnWdeWaiAZhUkZMZTjK1ovbU3tHea9ZwV8diybk7qH0prekaaBBovuLabehfMXA5siHpyJaQYAgl6f5hGLg0UQkBh8DfzBGuUIkjhtSod"
          }
      }
  }

==========
Documentos
==========

Registro de documentos
----------------------

Method: GET

Endpoint: http://testnet.originalmy.com/api/v1/company/register

Parameters:

+--------+--------+-------------------------------------------------------------------------------+
| Campo  | Tipo   | Descrição                                                                     |
+========+========+===============================================================================+
| k      | String | Chave de acesso                                                               |
|        |        | Exemplo: XXXX-XXXX-XXXXX                                                      |
+--------+--------+-------------------------------------------------------------------------------+
| d      | String | Digest SHA256 do PDF do documento digital                                     |
|        |        | Exemplo: f00ab5b228a4c31968c472b4dfcc013b5b27de134bb490c1a70327eaf90a8235     |
+--------+--------+-------------------------------------------------------------------------------+

Exemplo de retorno:

:: 

  {
    "digest": "f00ab5b228a4c31968c472b4dfcc013b5b27de134bb490c1a70327eaf90a8234",
    "success": true,
    "quota": 33
  }
  
Verificação do status do registro
---------------------------------

Method: GET

Endpoint: http://testnet.originalmy.com/api/v1/status

Parameters:

+--------+--------+-------------------------------------------------------------------------------+
| Campo  | Tipo   | Descrição                                                                     |
+========+========+===============================================================================+
| d      | String | Digest SHA256 do PDF do documento                                             |
|        |        | Exemplo: a090394ab6ec5b6e908eade569cba86028694c968112cd9b0b8962060b2d1101     |
+--------+--------+-------------------------------------------------------------------------------+

Exemplo de retorno:

:: 

  {
      "status": "confirmed",
      "blockstamp": "2017-07-25 17:50:35",
      "transaction": "0x0e68819506081bcbd2c3d1af97be3e7d25906a0e854c56e8830f21e8e1fcfa82",
      "success": true,
      "networks": [
        {
            "blockstamp": "2017-07-19 23:09:42",
            "transaction": "0x1e99d2d7a2038f1138b907f954a6fa2f9bd073a1ef22b678aa25e7a6c0ab2c0c",
            "link": "https://rinkeby.etherscan.io/tx/0x1e99d2d7a2038f1138b907f954a6fa2f9bd073a1ef22b678aa25e7a6c0ab2c0c",
            "name": "eth",
            "txstamp": "2017-07-19 23:09:13.881940"
        },
        {
            "blockstamp": "2017-07-20 00:01:14",
            "transaction": "7a6d22a92028ec20826fbea44b3f8556dee5035c9c69ca12db7b0032bc4af105",
            "name": "dcr",
            "link": "https://testnet.decred.org/tx/7a6d22a92028ec20826fbea44b3f8556dee5035c9c69ca12db7b0032bc4af105",
            "merkle": "b985a1f338c5299d1c5bd60e4818c214ce520a1da16e416dc8bca61a2e111451",
            "txstamp": "2017-07-20 00:00:00"
        }
      ],
      "txstamp": "2017-07-25 17:50:10.070350"
  }
  
========
Usuarios
========

Pré-cadastro de usuários
------------------------

Method: POST

Endpoint: https://signcontracts-mobile-api-stag.herokuapp.com/users/register

Parameters:

+-------------+--------+------------------------------+
| Campo       | Tipo   | Descrição                    |
+=============+========+==============================+
| user[name]  | String | Nome do usuário              |
| user[email] | String | Email do usuário             |
| user[cpf]   | String | CPF do usuário               |
| key         | String | Chave de acesso              |
+-------------+--------+------------------------------+

Para fazer o request utilizando a linha de comando, use o curl:

::

  curl -X POST -H 'Content-Type: application/json' -d '{"user":{"name":"João da Silva","email":"nome@seusite.com","cpf":"64564467751"},"key":"XXXX-XXXX-XXXXX"}' https://signcontracts-mobile-api-stag.herokuapp.com/users/register

Exemplo de request POST:

:: 

  {
      "user": {
           "name": "João Da Silva",
           "email": "nome@seusite.com",
           "cpf": "64564467751"
      },
      "key": "XXXX-XXXX-XXXXX"
  }

.. note:: Sucesso. A senha gerada para o usuário estar no user_password

Exemplo de retorno:

:: 

  {
       "status": "success",
       "data": {
            "user": {
                 "user_password": 361660
            }
       }
  }
  
Verificar a identidade blockchain atual de um usuário
-----------------------------------------------------

Method: GET

Endpoint: https://signcontracts-mobile-api-stag.herokuapp.com/idRepo/getWallet/:cpf/wallet

Parameters: 

+-------------+--------+---------------------------------+
| Campo       | Tipo   | Descrição                       |
+=============+========+=================================+
| cpf         | String | CPF do usuário. Ex: 34155955792 |
+-------------+--------+---------------------------------+

Exemplo de retorno: 

:: 

  mvBox6yQfEvKjAfP2qAVLksmcC1oe65AyM

Verificar todas as identidades blockchain anteriores
----------------------------------------------------

Method: GET

Endpoint: https://signcontracts-mobile-api-stag.herokuapp.com/idRepo/getWallet/:cpf/wallets

Parameters: 

+-------------+--------+---------------------------------+
| Campo       | Tipo   | Descrição                       |
+=============+========+=================================+
| cpf         | String | CPF do usuário. Ex: 34155955792 |
+-------------+--------+---------------------------------+

Exemplo de retorno:

:: 

  [
  "msveHToGjmrrqjrBvVChAVJk9sAfoorfBB",
  "morHcd3cSULieqwK9zvnvku8PFTgcHhDVZ",
  "mgM8aiB9nBt9EPf4atrzxQzwodCEWTPoXH",
  "miEqv1T1cXjxL61pzaEfF7jF3QxET5ApsY",
  "mhkGbHrbxyLY5ZjUwjtXRpfUrcQKtdtHDD",
  "12WRUyfsQ7V1hAhG9ZJ7xd82EoEq1CKHXr",
  "mhaixA4V3AP2cgiJTKeyuBNihT4pRrTVSo"
  ]
