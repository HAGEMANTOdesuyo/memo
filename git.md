# git memo
## 基本情報確認系
- ステータス
```
git status
```

- ログ
```
git log
```

## ブランチ操作
- ローカルブランチ一覧
```
git branch
```

- ローカル+リモートブランチ一覧
```
git branch -a
```

- ブランチ作成
```
git branch <branchname>
```

- ブランチ切り替え
```
git checkout <branchname>
```

- ブランチ作成&切り替え
```
git checkout -b <branchname>
```

- ローカルブランチ削除(要確認)
```
git branch -d <branchname>
```

- リモートブランチをダウンロードして切り替え
```
git checkout -t <remote branchname>
```

## 取り消し系
- 直前のコミットを取り消す
```
git reset --soft HEAD
```
- addの取り消し
```
# すべてのファイル
git rm --cached -r .

# 特定のファイル
git rm --cached -r <file name>
```

## push関係
- commitしたファイルをリモートブランチにpushする
```
git push origin HEAD
or
git push origin <branchname>
```

- fetch, merge, pullの違い
  - git fetch...リモートの「master」ブランチ→ローカルの「origin/master」ブランチ
  - git merge...ローカルの「origin/master」ブランチ→ローカルの「master」ブランチ
  - git pull...git fetch, git mergeを同時に行うコマンド

## ファイル操作
- ファイル名変更、ファイル削除
```
git mv <filename1> <filename2>
git rm <filename>
```

## 設定
- 認証情報をキャッシュする
```
git config --global credential.helper cache
```

