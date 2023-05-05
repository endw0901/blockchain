https://etherconverter.online

- require statementで、transactionについてくるethが足りてるかチェック & エラーログ

- modifierはannotationのようにfunctionに付与して、_でほかのコード繰り返し、の意味

- 共通処理をannotationのように付与できるもの

## ツール

- remix (ブラウザテスト solidity)

- ganache (local test network)

- new Web3(ganache.provider()); -> test networkに接続

- デフォルトでアカウントも用意してくれる



- infura api(rinkerbyなど。時期によって変わる

- HDWalletProvider

- Mocha

- mochaとganache-cliを使ったローカルテストと、truffle-hdwallet-providerとinfura.ioを使ったデプロイ。

https://qiita.com/s0sasaki/items/1d558f255baa9805d9a9

```
npm init

npm install ganache-cli mocha solc@0.4.17 fs-extra web3

※solc = solidity compiler


npm initでできたpackage.json => scriptsのtest : mocha

npm install @truffle/hdwallet-provider

npm install next-routes --legacy-peer-deps




```

## blockchain on AWS

https://d1.awsstatic.com/events/jp/2018/summit/tokyo/aws/26.pdf



https://dev.classmethod.jp/tags/amazon-managed-blockchain/

### wei
- PGM上では、0.1 ether で自動的にweiにconvertしてくれる
- 100 gweiという書き方もある
- 
- web3.utils.toWei('0.02', 'ether')
- 変換してくれる

### payable
- (function type (public, privateなど)の一つ)

- sendでethをcontractに引数で送れる

https://qiita.com/ryu-yama/items/4c37d5ff0fbc5364e569


### javascript
[campaignAddress] 　配列の最初の要素をとる

javascript snipets


## 開発の注意点
factoryはdeployする(fee自分持ち)、campaignはdeploy済みのものをaddressで特定して使う



gas代自分もちのfactory(campaign製造用)を作ることで、campaignを無数に作られても破綻しないようにする。また、campaignの中身をブラックボックスにして、セキュリティ（コード改ざん防止）になる
