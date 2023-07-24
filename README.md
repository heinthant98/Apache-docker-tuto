# やったこと
Dockerを使ってApacheサーバを利用してみました。   
下記のリンクを参考してやってみました。   
https://www.youtube.com/watch?v=I66s-6NzkL0

## ステップ１

まずはこのリポジトリをクーロンして、クーロンしたディレクトリの配下に行って下記のようにDockerfileがあるかを確認しましょう。   
<img width="700" src="https://github.com/reytech-co-jp/onigiri/assets/100908505/c286152e-0ea5-4f6f-a147-1c8f20365ec1">

## ステップ２

下記のコマンドを利用してApacheサーバのイメージを作成します。   
<b>注意: 名前の後に`.`を忘れないように</b>
```cmd
docker build -t <イメージ名> .
```

## ステップ３
Apacheサーバのイメージが作成できたかを下記のコマンドを使って確認しましょう。
```cmd
docker images
```

下記のように自分が命名した名前が表示されているなら大丈夫です。

<img width="700" src="https://github.com/reytech-co-jp/onigiri/assets/100908505/0c2b8a08-763e-4eb1-9712-ea61013f692d">

## ステップ４

イメージができたら下記のコマンドでDockerコンテナーを起動しましょう。
```cmd
docker run -d --name <コンテナー名> -p <ポートの番号> <イメージ名>
```

<b>例画像</b>

<img width="700" src="https://github.com/reytech-co-jp/onigiri/assets/100908505/21aad2c0-bd68-419f-8d07-d25c25250ebb">

## ステップ５

そして、Dockerコンテナーが起動しているかを下記のコマンドで確認します。
```cmd
docker ps
```

下記の画像のように自分が命名したイメージとコンテナー名が表示されいるならOKです。

<img width="700" src="https://github.com/reytech-co-jp/onigiri/assets/100908505/b65b660c-4009-4e32-86bb-5221010826d3">

## ステップ６

自分が与えたポート番号を使ってウエブサイトで確認しましょう。

<img width="700" src="https://github.com/reytech-co-jp/onigiri/assets/100908505/982c1615-cbdd-486a-a01b-089334c68e25">

## ステップ７

もし、複数のコンテナーを起動したいときは、下記のコマンドを利用して別のポートと別のコンテナー名を使って起動できます。
```cmd
docker run -d --name <コンテナー名> -p <ポートの番号> <イメージ名>
```

### エラーログ

前作成したコンテナーとコンテナー名やポートの番号が等しい場合は下記ようにエラーログが表示されます。
<img width="700" src="https://github.com/reytech-co-jp/onigiri/assets/100908505/3b3724e7-06f4-4c94-9e5b-ada1283159c3">

## ステップ８

`docker ps`コマンドで起動しているコンテナーをチェックし、下記のコマンドでストップします。
```cmd
docker stop <コンテナー名>
```

## 終了

起動したコンテナーがストップしたかを`docker ps`を利用して確認します。下記のようにイメージやポートの番号などに何も表示されないなら大丈夫です。

<img width="700" src="https://github.com/reytech-co-jp/onigiri/assets/100908505/4f0411e4-164c-4df9-89e4-d54d1e5e170d">

