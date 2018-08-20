# Ethereum-Tutorial
Um simples tutorial de como interagir com o Ethereum

Este exemplo trabalha em uma rede privada

Instale o Ethereum mas não execute
https://geth.ethereum.org/downloads/

Iniciar um core a partir de um arquivo genesis
<pre>
geth.exe init genesis.json --datadir data-private
</pre>

Executar Geth (Servidor)
<pre>
geth --datadir data-private\
</pre>
Ou
<pre>
geth --datadir ./data-private/ --rpc --rpcapi "web3,admin"
</pre>

Conectar direto no nó (Attach) (Cliente)

Private Network
<pre>
geth.exe attach ipc:\\.\pipe\geth.ipc
</pre>

MAC
<pre>
geth attach ipc:/Users/SEUNOME/Library/Ethereum/geth.ipc
</pre>

Servidor Externo
<pre>
geth attach http://99.999.99.999:8545
</pre>

Criar carteira
<pre>
personal.newAccount("senha")
</pre>

Outra carteira
<pre>
personal.newAccount("senha")
</pre>

Listar Carteiras
<pre>
personal.listAccounts
</pre>

Obter Saldo
<pre>
web3.fromWei(eth.getBalance(eth.accounts[0]), "ether")
</pre>
Ou
<pre>
web3.fromWei(web3.eth.getBalance('0x355754b5cbc21685d42241594b2c06a2ef5f****'),'ether')
</pre>

Desbloquear Carteira
<pre>
personal.unlockAccount(eth.accounts[0], "senha", 100000)
</pre>

Enviar Ether
<pre>
eth.sendTransaction({from:eth.accounts[0],to:eth.accounts[1], value:web3.toWei(7,"ether")})
</pre>

Enviar Token e interagir com o contrato
<pre>
loadScript('./token.js')
token.transfer(eth.accounts[1],5000, {from: eth.accounts[0], gas: 900000});
</pre>

Iniciar Mineração
<pre>
miner.start()
</pre>

Finalizar Mineração
<pre>
miner.stop()
</pre>

Socket
Versão Completa
<pre>
.\geth --datadir data-private\ --mine --nodiscover --nat any --identity data-private --networkid 777 --port 30301 --verbosity 5 --ipcpath \\.\pipe\geth.ipc --rpc --rpcaddr 0.0.0.0 --rpcport 8545 --rpccorsdomain '*' --rpcapi personal,admin,db,eth,net,web3,miner,shh,txpool,debug --ws --wsaddr 0.0.0.0 --wsport 8546 --wsorigins '*' --wsapi personal,admin,db,eth,net,web3,miner,shh,txpool,debug --maxpeers 25 --etherbase 0 --gasprice 0 --targetgaslimit 9999999
</pre>

IDE Solidity
http://remix.ethereum.org

Princípios Blockchain
Ledger Distribuido
Criptografia
Consenso
SmartContract
