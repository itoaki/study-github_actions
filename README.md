# study-github_actions

![Hello, World!](https://github.com/itoaki/study-github_actions/workflows/Hello,%20World!/badge.svg)
![Countenuous Integration](https://github.com/itoaki/study-github_actions/workflows/Countenuous%20Integration/badge.svg)
![Test](https://github.com/itoaki/study-github_actions/workflows/Test/badge.svg)

Github Actionsの勉強リポジトリです。

# 設定してあるAction

## hello.yml
master以外にpushされた時に、`echo "Hello, World"`を表示します。

## security.yml
毎年、1月1日の9時に`npm audit`を実行します。(cron)

## ci.yml
pushされた時に、mochaによるテスト実行とeslintによるチェックを実行する。

## test.yml
外向けに作成したaction.ymlを内部でも使用するテスト

## (root)action.yml
他のリポジトリから使用するためのactions定義
index2.jsを実行する。（中身はHello world）

使用したいときは、ymlファイルに下記のように設定する。
'''
jobs:
  hello:
    # ジョブ名
    name: hello world
    # これはデフォルトのまま
    runs-on: ubuntu-latest
    steps:
      - name: hello
        uses: itoaki/study-github_actions@v1.0.0
'''
