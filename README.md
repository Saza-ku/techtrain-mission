# TechTrain MISSION
## 学べること
- APIサーバの開発の仕方
- リレーショナルデータベース(MySQL)の基礎的な使い方
- サーバーサイドアプリケーションへの通信の基礎
- Go言語を利用した開発の基礎

## STEP
**【1st STEPs】**
### STEP1: MISSIONの内容を確認してみよう
```
開発をするAPIの仕様を確認してみましょう。
このMISSIONではスマートフォン向けゲームのAPIの開発を想定しています。
API仕様YAML: [ここにURL]
上記のyamlファイルの内容をSwaggerEditorの画面左半分にコピー&ペーストで入力してみましょう。
SwaggerEditor: https://editor.swagger.io/
画面右半分に表示された内容が今回開発をする内容です。
```

### STEP2: 開発環境を準備してみよう
```
このMISSIONではGo言語とMySQL(データベース)を利用して開発を行います。
それぞれ最新版を自身のPCに導入しましょう。
MySQLは直接PCへインストールでも良いですがdockerを利用するとより手軽です。
```

### STEP3: ユーザ情報を保存するテーブルを設計してみよう
```
API仕様を見ながらMySQLのテーブル定義をしましょう。
今回、ゲームユーザの情報(認証情報と名前)を管理するためにどのようなテーブルが必要か考えてみましょう。
定義が完了したら実際にMySQLにCREATE TABLEしてみましょう。
```

### STEP4: 認証情報の作成 / ユーザ情報の更新・参照APIを実装してみよう
```
STEP3で定義したDBテーブルを利用して実際にAPIを実装してみましょう。
実装対象のAPIは以下の3つです。上から順に作ってみましょう。
・/user/create ユーザアカウント認証情報作成API
・/user/get ユーザ情報取得API
・/user/update ユーザ情報更新API
```

### STEP4.5: メンターと面談しよう
```
STEP4までが完了したら一度メンターと面談をしてみましょう。
テーブルの設計や実装した内容をレビューしてもらえると多くの学びを得られると思います。
プロのエンジニアからアドバイスをもらい、合格をもらえたらぜひ次の2nd STEPsへと進みましょう。
```
---
**【2nd STEPs】**

### STEP5: ガチャに関連するテーブルを設計しよう
```
ガチャに関連するテーブルを設計してみましょう。
具体的には
・キャラクターの不変的な内容(IDや名前など)を定義する情報テーブル
・ユーザの所持キャラクター情報を管理するテーブル
・ガチャの排出内容を定義するテーブル
などが挙げられます。どのように排出確率を定義するかしっかりと考えながら定義をしてみましょう。
```

### STEP6：ガチャ実行APIと所持キャラクター一覧取得APIを実装してみよう
```
上から順に
・/gacha/draw ガチャ実行API
・/character/list ユーザ所持キャラクター一覧取得API
を実装してみましょう。
ガチャ実行は指定した回数分キャラクターの排出抽選を行い、ユーザの所持キャラクター情報に保存をします。
その後ユーザ所持キャラクター一覧取得APIでガチャで獲得したキャラクター情報が取得できるか確認をしてみましょう。
```

### STEP6.5: メンターと面談しよう
```
STEP6が完了したらもう一度メンターと面談をしてみましょう。
再度テーブルの設計やガチャの抽選ロジックに無駄がないかなど特に見てもらうと良いと思います。
プロのエンジニアからアドバイスをもらい、合格をもらえたらぜひ次のBonus STEPsへと進みましょう。
```
---
**【Bonus STEPs】**

以下のSTEPに任意の順番で挑戦をしてみましょう。

### Bonus STEP: ゲームAPIの機能を拡充してみよう
```
ゲーム機能でありそうな機能を考えて追加設計・実装をしてみましょう。
例)
・ランキング機能
キャラクター情報にパワー値などを持たせ、ガチャで排出したキャラクターの最高パワー値でユーザをランキングする
```
### Bonus STEP: 様々なWebフレームワークやライブラリなどを導入してみよう
```
Go言語は標準のnet/httpパッケージでも十分web開発ができますが、
フレームワークを導入することでより便利で高速な開発を行うことができます。
作ったAPIの機能はそのままに、様々なWebフレームワークやライブラリを導入した場合に、
どのような差異があるのか体験をしてみましょう。
```

## MISSIONのヒント
### Swaggerについて
```
・SwaggerはRESTful APIを構築するためのオープンソースフレームワークです。
・本MISSIONではAPI仕様のドキュメントの生成にSwaggerEditor及びSwaggerUIを利用しています。
・実際のチーム開発ではAPI仕様をどのように可視化するのか、またどのようにクライアントエンジニアとコミュニケーションを取るのかは考えるべきテーマです。
```

### MySQLについて
```
・MySQLはリレーショナルデータベースマネジメントシステムのひとつです。
・各STEPの設計とCREATE TABLEができたらmysqlコマンドやMySQLWorkbench等で接続をし実際にクエリを実行してみましょう。
・INSERT, SELECT, UPDATE, DELETEはデータベース操作の基本です。何度も繰り返し記述と実行をしてしっかり書き方を覚えましょう。
・データベース操作はコストが高い処理です。プログラム中では無駄にクエリの発行をしないように意識をしましょう。
```

### ログについて
```
・ログは何かが起こった際の調査の糸口となるとても重要な要素です。最低限エラーログはしっかりと書くことを意識してください。
・ログを出力するときは「誰が」「いつ」「何を」「どういった条件で」行ったのかしっかりと出力しましょう。
・プログラムのログに限らず、その他の色々なプログラム・ミドルウェア・クラウドサービスでも多くのログが出力されています。各ログの用途もしっかりと理解していきましょう。
```