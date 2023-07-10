# git の機能やコマンドについて

## git の基本的なコマンド
- git config  ローカルリポジトリ用のユーザー情報設定
- git init "project-name"  ローカルリポジトリの作成
- git status  コミット可能なすべての新規または変更のあるファイルを一覧で表示
- git diff  まだステージされていないファイルの差分を表示
- git add       バージョン管理のためにファイルのスナップショットを作成
-git commit -m "descriptive message"  ファイルのスナップショットをバージョン履歴内に恒久的に記録

##git の branch に関するコマンド
- git branch "branch-name"  新規ブランチの作成
- git checkout "branch-name"  指定されたブランチに切り替え作業ディレクトリを更新
- git merge "branch-name"  指定されたブランチの履歴を現在のブランチに統合
