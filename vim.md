# vim memo

## vim, gvim共通
- バッファ操作
```
:ls
"(→enterを押さずに:を押すと、:lsの結果を見ながらコマンドが打てる)
:b 7
:b hoge.txt
:bnext
```
- 無名バッファの作り方
```
" 新たに無名バッファを開く
:enew
" ウィンドウを分割して、そこに無名バッファを開く
:split +enew
:vsplit +enew
" 新しいタブを作り、そこで無名バッファを開く
:tabnew
```

- vimを閉じずにファイルを閉じる
```
:bd
```

- カーソル移動系
  - 対のカッコへ移動
```
%
```
  - 直前の位置へ移動
```
ctrl-o
```

- nerdtreeへの移動
```
ctrl-w t
```

- netrwでディレクトリを開く
```
:E
```
- 特定の文字まで削除、変更
```
df<char>
cf<car>
```

- 折り畳み
```
zf # visualモード選択範囲
zo
zO
```

- mark
```
m <キー>
`(or)' <キー>
:marks
:delmark <キー>
```

- vimgrep
:cd, :lcdで移動してからvimgrepをかける
https://blog.onk164.net/archives/517.html

## gvim
- ユーザーホームに.vimrc, .gvimrc, .vimを配置
- ユーザーホームの\*rcから.vim内の\*rcを読み込む
```
"~/.vimrc
source ~/.vim/.vimrc
"~/.gvimrc
source ~/.vim/.gvimrc
```
- .bashrc_wslを.bashrcから読み込む
- wsl内のファイルをgvimで編集するには、wsl内からgvimを実行する
