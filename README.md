***CLIQUE NA PASTA ZIP PARA VISUALIZAR TUDO***

**A principal implementação está na pasta contracts, no arquivo DonateCrypto.sol**

O código faz parte de uma aplicação feita no Remix IDE (https://remix.ethereum.org/). Este contrato DonateCrypto é uma aplicação inteligente e direta de crowdfunding descentralizado (doações em cripto) usando Solidity. Abaixo vai um comentário mais completo sobre o que ele faz e pontos positivos:

## ✅ O que o contrato faz?

Ele permite que qualquer pessoa:

* Crie uma campanha de doação, informando título, descrição, link de vídeo e imagem.
* Receba doações de outros usuários para essa campanha.
* Saque os fundos (menos uma taxa) se for o autor da campanha.

##  Estrutura do Contrato:

###  Struct Campaign

Contém:

* autor
* título, descrição
* vídeo e imagem (útil para exibir no front-end)
* saldo arrecadado
* status da campanha (ativa ou encerrada)

###  addCampaign(...)

* Cria uma nova campanha.
* Usa um contador `nextId` como chave do mapeamento `campaigns`.

###  donate(id)

* Permite doar para uma campanha ativa.
* Valor mínimo é qualquer valor > 0 wei.

###  withdraw(id)

* Só o autor da campanha pode sacar.
* Deduz uma taxa fixa (`fee`).
* Marca a campanha como encerrada.

##  Pontos positivos

* ✅ **Simplicidade:** fácil de entender, ideal para MVP e testes com Remix.
* ✅ **Regras básicas de segurança** como validação de autor e estado da campanha.
* ✅ **Uso de calldata em strings** => economiza gas.
