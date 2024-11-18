# 概要
Gitの操作練習用リポジトリ

## WSL2にgitインストール
```
sudo apt update
sudo apt install git -y
git --version
```

## 初期設定
```
git config --global user.name "username"
git config --global user.email "mailaddress"
git config --list
```

## ローカルリポジトリ作成
```
mkdir dirname
cd dirname
git init
git remote add remotename URL
```

## 基本操作
local repoとworktreeの差分チェック
```
git diff
```

ファイルをステージへ追加
```
git add filename ※.で全ファイル
```

local repoとstageの差分確認
```
git diff --staged
```

local repoへコミット
```
git commit -m "commit message" 
git commit -v  → コミット内容確認
```

変更ファイル確認
```
git status
```

変更履歴確認
```
git log
 --online：ワンライナー表示
 -p filename：ファイルの変更差分表示
 -n <commit cnt>：表示コミット数制限（直近から遡る）
```

ファイル削除
```
git rm filename
git rm -r dirname
git rm --cached filename → worktreeには残す
```

ファイル移動
```
git mv oldfile newfile
```

リストア
```
git restore filename → worktreeの変更取り消し
git restore --staged filename → stageにあげた変更をworktreeに戻す
```

ブランチ
```
git branch → ブランチ一覧確認
 -a：githubのブランチも表示
git branch branchname → ブランチ作成
```

スイッチ
```
git switch branchname → ブランチ切り替え
 -c：ブランチ新規作成
```

マージ
```
git merge branchname → ブランチマージ
```

push
```
git push remotename branchname
```

pull
```
git pull [remotename branchname] → local repoに反映してworktreeに反映（コンフリクト懸念があればfetchしてmerge）
```

fetch
```
git fetch remotename → local repoに取得
```

clone
```
git clone URL
```