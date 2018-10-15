// gethの初期化処理
geth --datadir ~/geth/private_net/ init ~/geth/private_net/genesis.json

// gethの起動
geth --networkid "10" --nodiscover --datadir ~/geth/private_net -rpc --rpcaddr "localhost" --rpcport "8545" --rpccorsdomain "*" --rpcapi "eth,net,web3,personal" --targetgaslimit "20000000" console 2

// アンロックオプション起動
geth --networkid "10" --nodiscover --datadir ~/geth/private_net -rpc --rpcaddr "localhost" --rpcport "8545" --rpccorsdomain "*" --rpcapi "eth,net,web3,personal" --targetgaslimit "20000000" console 2　--unlock 0xd9e7171d87ed9e70345e3378b0317241eb6ba2fc,0x219044c19c7b09715e5b95efbf84a0ed2bc3d2b5, 0x75ad02b4f8fc974068f975cd7804daa5211cd54b --password ~/geth/private_net/password.txt



//ロックの解除
personal.unlockAccount(eth.accounts[e])


// アカウント作成
personal.newAccount("password")

// アカウント確認
eth.accounts
eth.accounts[0]

// コインベースアカウントの確認と変更（報酬を受け取るアカウント）
eth.coinbase
miner.setEtherbase(eth.accounts[1])

// マイニングの開始・停止
miner.start(1)
miner.stop()

// マイニング中かの確認
eth.mining → trueが返ってくればマイニング中

// コインベースの残高確認
eth.getBalance(eth.accounts[0]) //wei単位
web3.fromWei(eth.getBalance(eth.accounts[0]),"ether") //ether単位

// ロックの解除・送金
personal.unlockAccount(eth.accounts[0])
eth.sendTransaction({from:eth.accounts[0], to:eth.accounts[1], value:web3.toWei(3, "ether")})

// トランザクションの確認
eth.getTransaction("0xc7a3e592cb54809e1ef5406003ef57f83c06e44d9e5e2e6523e192b948205345")

// トランザクションレシートの確認
eth.getTransaction("0xc7a3e592cb54809e1ef5406003ef57f83c06e44d9e5e2e6523e192b948205345")