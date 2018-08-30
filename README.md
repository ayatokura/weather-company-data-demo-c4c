# The Weather Company API を活用したデモアプリケーション
The Weather Company APIを活用したWebアプリケーションを、IBM Cloudにデプロイすることができる手順をご紹介します。

## Webアプリケーションの動作環境
一般的なブラウザであれば、表示することができます。

## 事前準備
本アプリケーションを動作させるためには、次のソフトウェアをローカルにインストールしてある環境が必要になります。
1. Git - Gitをインストールしてください
2. Node - アプリケーションランタイム環境。[サイト](https://nodejs.org/en/)からパッケージをダウンロードしてインストールします。
3. IBM Cloud 開発ツール「Cloud Foundry CLI」- [ツール](https://console.bluemix.net/docs/cli/index.html#cli)をダウンロードして、インストールします。
4. コードエディタ。例えば、無料の軽量でマルチ環境(Windows, macOS, Linux)に対応している[Visual Studio Code](https://code.visualstudio.com/)など。

# 手順
## リポジトリのクローン

1. IBM Cloudアカウント作成
IBM Cloudのアカウントをご用意ください。Call for Code Day in Tokyoに参加される方で、まだアカウントをお持ちでない方は[こちら](https://ibm.biz/BdYzDx
)よりアカウント登録してください。

2. weather-company-data-demo-c4c リポジトリをローカルにクローンします。ターミナルで次のコマンドを実行します。  
  ```
  git clone https://github.com/IBM-Bluemix/weather-company-data-demo.git
  ```

3. `cd weather-company-data-demo-c4c` でディレクトリ移動します。

## 依存関係のインストール

4. ターミナルに戻り、npm installを実行します。
  ```
  npm install
  ```

## ローカルでアプリケーションを実行する

5. `manifest.yml` ファイルの `<name>` および `<host>` に任意の文字列を入力し、保存します。
  ```
applications:
- disk_quota: 1024M
  name: weather-company-data-demo
  host: weather-company-data-demo
  command: node app.js
  path: .
  domain: mybluemix.net
  instances: 1
  memory: 512M
  ```
 ここで指定した文字列はWebアプリケーションを公開するためのURLの一部となります。 `<host>.mybluemix.net` 
 
 6. アプリケーションをローカルで実行します。
   ```
  node app
  ```
 
 7. 実行されるとターミナルに次のようなメッセージが表示され、ブラウザで下記URLにアクセスするとWebアプリケーションが表示されます。
   ```
  server starting on http://localhost:6001
   ```
 ## IBM Cloudへアプリケーションをデプロイする
 
 8. ターミナルからIBM Cloudにログインします。
  ```
  $ ibmcloud login
  $ ibmcloud target --cf
  ```
 
 9. IBM Cloudへデプロイします。
   ```
  $ ibmcloud cf push
  ```
  
 10. (オプション)IBM Cloudへデプロイしても、起動させずに手動でWebアプリケーションを稼働させる場合には下記のコマンドを実行します。
 ```
$ ibmcloud login
$ ibmcloud target --cf
$ ibmcloud cf push --no-start
$ ibmcloud cf start [host name]
```

## 本アプリケーションへのアクセス
11. IBM Cloudへのデプロイに成功すると下記URLでWebアプリケーションが公開されます。
`https://<host>.mybluemix.net`

# 完成イメージ
<img src="https://8ingja.bn.files.1drv.com/y4molxlwvbLVOvjR5SLIGSY8tvPP1NHNYfvDoQf5QIHKpPPUAC-v85AYB60lANnbSkMh2VX2Z9KOeJqu8e9o8FX_q5QP3PWJXdQNWi9rj_fdv8q1-gxEV6CP6mqpvIJUc14SE3eaR3qo6knX-S7LtshIdYpi2NXfcuDhkhw9Qv_9zwVbABUkNEEsaB3xIYGUhcsmTv2sGNemMzvcI55RK3WDQ?width=1730&height=1368&cropmode=none" width="600">
