# git の機能やコマンドについて

## git  を用いてできること
  > - プロジェクトに対して行われたすべての変更について、変更が行われた日時や変更者の確認
  > - プロジェクト全体または個々のファイルの過去のバージョンを取得
  > - ブランチを用いることでメインブランチに影響を与えることなく実験的に変更を行うこと
  > - ブランチ上の変更をマージを用いてメインブランチに反映させること

****
****

## git の基本的なコマンド
  - ### git config
      - 設定周りの確認・変更
  - ### git init "project-name"
    - gitの初期化・設定開始
  - ### git status
    - ワークツリーのステータスを表示
  - ### git diff
    - まだステージされていないファイルの差分を表示
  - ### git add
    - ステージングエリアに追加
  - ### git commit -m "descriptive message"
    - コミットの実行

## git の修正に関するコマンド
  - ### git commit --amend --no-edit
    - コミットの修正
  - ### git checkout
    - 削除されたファイルを復旧や過去コミットの復元など（元に戻す変更が staging area/index 内にある場合）
  - ### git reset
    - コミットのリセット
  - ### git revert
    - 「コミットの変更を打ち消す」コミット
  - ### git rm
    - ファイルとindex情報の削除

## git のリモートに関するコマンド
  - ### git clone
    - レポジトリをコピー
  - ### git pull
    - リモートリポジトリの同期
  - ### git push
    - 変更をアップロードする
  - ### git request-pull
    - プルリクエスト：変更依頼
  - ### git remote
    - リモートレポジトリの設定

## git の branch に関するコマンド
  - ### git branch "branch-name"
    - 新規ブランチの作成
  - ### git checkout "branch-name"
    - 指定されたブランチに切り替え作業ディレクトリを更新
  - ### git merge "branch-name"
    - 指定されたブランチの履歴を現在のブランチに統合

****
****

## git flowについて

git flowでは、'main'ブランチと'develop'ブランチとを作成し、'develop'ブランチ上で開発する

 - ### 'main'ブランチ
   - このブランチで開発は行いません。main ブランチの最新版がプロダクトとしてユーザにリリースされます。
 - ### 'develop'ブランチ
   - main から develop へブランチを切ります。develop で開発を行い、main はリリース時にコミットされます。main の commit にはリリースごとにタグを打ちます
 - ### 'feature'ブランチ
   - develop から feature へブランチを切ります。複数人で develop で開発するときに使います。1 機能ごとに develop からブランチを切り、1機能の開発が終われば develop へ merge します。
 - ### 'release'ブランチ
   - develop から main へ merge するための準備をするブランチです。main へ commit することで実際にプロダクトとして使われるようになります。
 - ### 'hotfix'ブランチ
   - main から hotfix へブランチを切ります。本番環境で発生したバグのうち緊急性の高いものを修正するブランチです。修正が完了したら main と developにマージします。