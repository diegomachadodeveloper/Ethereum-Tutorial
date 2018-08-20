# Ethereum-Tutorial
Um simples tutorial de como interagir com Ethereum

Instala o Ethereum mas não execute

Iniciar um core a partir de um arquivo genesis
geth.exe init genesis.json --datadir data-private

Executar Geth (Servidor)
geth --datadir data-private\
Ou
geth --datadir ./data-private/ --rpc --rpcapi "web3,admin"

Conectar direto no nó (Attach) (Cliente)

Private Network
geth.exe attach ipc:\\.\pipe\geth.ipc

MAC
geth attach ipc:/Users/SEUNOME/Library/Ethereum/geth.ipc

Servidor Externo
geth attach http://99.999.99.999:8545

Criar carteira
personal.newAccount("senha")

Outra carteira
personal.newAccount("senha")

Listar Carteiras
personal.listAccounts

Obter Saldo
web3.fromWei(eth.getBalance(eth.accounts[0]), "ether")
Ou
web3.fromWei(web3.eth.getBalance('0x355754b5cbc21685d42241594b2c06a2ef5f****'),'ether').toString(10)

Desbloquear Carteira
personal.unlockAccount(eth.accounts[0], "senha", 100000)

Enviar Ether
eth.sendTransaction({from:eth.accounts[0],to:eth.accounts[1], value:web3.toWei(7,"ether")})

Enviar Token e interagir com o contrato
loadScript('./token.js')
token.transfer(eth.accounts[1],5000, {from: eth.accounts[0], gas: 900000});

Iniciar Mineração
miner.start()

Finalizar Mineração
miner.stop()

Socket
Versão Completa
.\geth --datadir data-private\ --mine --nodiscover --nat any --identity data-private --networkid 777 --port 30301 --verbosity 5 --ipcpath \\.\pipe\geth.ipc --rpc --rpcaddr 0.0.0.0 --rpcport 8545 --rpccorsdomain '*' --rpcapi personal,admin,db,eth,net,web3,miner,shh,txpool,debug --ws --wsaddr 0.0.0.0 --wsport 8546 --wsorigins '*' --wsapi personal,admin,db,eth,net,web3,miner,shh,txpool,debug --maxpeers 25 --etherbase 0 --gasprice 0 --targetgaslimit 9999999

IDE Solidity
http://remix.ethereum.org

Princípios Blockchain
Ledger Distribuido
Criptografia
Consenso
SmartContract
