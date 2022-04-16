# raisetech-01ringo-development-docs

## 概略

リンゴチームの開発用ドキュメントの保管場所です。
リンゴの個別issueもこちらで管理。

~~今後、アプリ開発に入った場合は、削除するかも（応相談）。~~（4/16山口削除）

## API Blueprint　Dockerコンテナ 概略

API Blueprintの実行環境を含むDockerコンテナです

- aglioを用いたドキュメントの表示環境
- drakovを用いたモックサーバー

上記２つの機能を内包しています。

## インストール手順

1. 任意のディレクトリを作成

2. cd '任意のディレクトリ'

3. ```$ git clone https://github.com/raisetech-for-student/raisetech-01ringo-development-docs.git```
  又は```$ git clone git@github.com:raisetech-for-student/raisetech-01ringo-development-docs.git```

4. ```$ docker-compose up -d```
  コンテナ構築時

5. ```$ docker-compose down```
  コンテナ終了時

## 使用例(aglio)

1. docsディレクトリ配下に表示させたい.apibファイルを配置

2. docker-compose.ymlファイルのファイル指定を変更する
  例）表示させたいファイルがsample.apibの場合、commandを下記で指定する
  ```command: aglio -i sample.apib -s -h 0.0.0.0 -p 8000```
  
3. ```$ open http://localhost:8000/```を実行し、表示を確認

## 使用例(drakov)

1. ```$ docker-compose exec drakov bash```
  ※（2022/04/16現在）Dockerコンテナ外からdrakovが実行できない。原因は調査中

2. コンテナ内でapi-blueprintで定義ずみのURIの動作を確認
  ```# curl http://localhost:8001/greeting```(sample.apibの場合)
