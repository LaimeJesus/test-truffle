req:
geth

archivo genesis
```
{
  "config": {
    "chainId": 1907,
    "homesteadBlock": 0,
    "eip155Block": 0,
    "eip158Block": 0
  },
  "nonce": "0x0000000000220042",
  "timestamp": "0x0",
  "parentHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
  "extraData": "0x00",
  "gasLimit": "0x8000000",
  "difficulty": "0x400",
  "mixhash": "0x0000000000000000000000000000000000000000000000000000000000000000",
  "coinbase": "0x3333333333333333333333333333333333333333",
  "alloc": {
  }
}

```
inicializar la configuracion de la red
```
geth --datadir node init genesis.json
```
inicializar la red privada y dejar minando
```
geth --rpc --rpcport "8545" --rpcaddr "127.0.0.1" --rpccorsdomain "*" --datadir net/ --networkid 98765 --port "30303" --rpcapi "personal,db,eth,net,web3" --mine
```
en otra consola, buscar el archivo geth.ipc, usar el siguiente comando para levantar la consola y luego desbloquear
la cuenta principal de esa red
```
geth attach ipc:path_to_geth.ipc
```
crear una cuenta, con password irrecuperable
```
personal.newAccount("password")
```
desbloquear la cuenta para minar
```
personal.unlockAccount(eth.accounts[0])
```
comenzar a minar
```
miner.start()
```
------------------------
inicializar el proyecto
```
sudo apt-get install ethereum
```
instalar truffle(agregar sudo si necesitas privilegios para la carpeta npm)
```
npm install -g truffle
```
instalar webpack(agregar sudo si necesitas privilegios para la carpeta npm)
```
npm install -g webpack
```
inicializar un proyecto de prueba con truffle, esto generara una estructura para el proyecto con algunos ejemplos.
```
truffle init webpack
```
agregar los contratos a la carpeta contracts/
modificar el archivo 2_deploy_contracts.js para deployar los contratos agregados
modificar truffle.js para usar la red privada

desde el proyecto truffle

security issues
https://blog.zeppelin.solutions/onward-with-ethereum-smart-contract-security-97a827e47702

complete guide
https://medium.com/@ConsenSys/a-101-noob-intro-to-programming-smart-contracts-on-ethereum-695d15c1dab4
