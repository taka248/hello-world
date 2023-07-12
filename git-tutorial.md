# git の機能やコマンドについて

## git  を用いてできること
- プロジェクトに対して行われたすべての変更について、変更が行われた日時や変更者の確認
- プロジェクト全体または個々のファイルの過去のバージョンを取得
- ブランチを用いることでメインブランチに影響を与えることなく実験的に変更を行うこと
- ブランチ上の変更をマージを用いてメインブランチに反映させること

## git の基本的なコマンド
- git config  ローカルリポジトリ用のユーザー情報設定
- git init "project-name"  ローカルリポジトリの作成
- git status  コミット可能なすべての新規または変更のあるファイルを一覧で表示
- git diff  まだステージされていないファイルの差分を表示
- git add  バージョン管理のためにファイルのスナップショットを作成
- git commit -m "descriptive message"  ファイルのスナップショットをバージョン履歴内に恒久的に記録

## git の branch に関するコマンド
- git branch "branch-name"  新規ブランチの作成
- git checkout "branch-name"  指定されたブランチに切り替え作業ディレクトリを更新
- git merge "branch-name"  指定されたブランチの履歴を現在のブランチに統合

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