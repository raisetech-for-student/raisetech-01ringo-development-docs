# raisetech-01ringo-development-docs

## 概略

リンゴチームの開発用ドキュメントの保管場所です。
リンゴの個別issueもこちらで管理。

4/16 API Blueprint 環境コンテナの作成

## API Blueprint　Dockerコンテナ 概略

API Blueprintの実行環境を含むDockerコンテナです

- aglioを用いたapi-bluprintの表示環境
- drakovを用いたモックサーバー

上記２つの機能を内包しています。

## インストール手順

1. 任意のディレクトリを作成

2. cd '任意のディレクトリ'

3. ```$ git clone https://github.com/raisetech-for-student/raisetech-01ringo-development-docs.git```

4. ```$ docker-compose up -d```
  コンテナ構築時

5. ```$ docker-compose down```
  コンテナ終了時

## 使用例(aglio)

1. docsディレクトリ配下に表示させたい.apibファイルを配置

2. docker-compose.ymlファイルのファイル指定を変更する   
例）表示させたいファイルがsample.apibの場合、commandを下記で指定する   
```command: aglio -i sample.apib -s -h 0.0.0.0 -p 8000```   
 ![image](https://user-images.githubusercontent.com/83934720/163670026-5463f600-ceef-4e56-ae02-2da3a09ba0e5.png)

  
3. ```$ open http://localhost:8000/```を実行し、表示を確認
 ![image](https://user-images.githubusercontent.com/83934720/163670260-f7ea1eb5-8720-44fd-ba4e-ce048f8659fa.png)


## 使用例(drakov)

~~※（2022/04/16現在）Dockerコンテナ外からdrakovが実行できない。原因は調査中~~   
  ※（2022/04/26現在）不具合解消につきコンテナ外から実行可能な状態となった

1. api-blueprintで定義ずみのURIの動作を確認
  ```# curl -v http://localhost:8001/greeting```(sample.apibの場合)
 ![image](https://user-images.githubusercontent.com/83934720/163670212-11bc1b7c-9f1e-4a4d-aacc-562a8b354ee4.png)
 
 
