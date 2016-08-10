# Global

`:help keyword` open help for keyword<br>
`:o file` open file<br>
`:saveas file` save file as<br>
`:close` close current pane

# カーソル移動

`h` 左に移動<br>
`j` 下に移動<br>
`k` 上に移動<br>
`l` 右に移動<br>
`w` 単語の先頭へジャンプ（区切り文字まで）<br>
`W` 単語の先頭へジャンプ（区切り文字を含めない）<br>
`e` 単語の最後にジャンプ（区切り文字まで）<br>
`E` 単語の最後にジャンプ（区切り文字を含めない）<br>
`b` 単語の先頭へ戻る（区切り文字まで）<br>
`B` 単語の先頭へ戻る（区切り文字を含めない）<br>
`0` (ゼロ)先頭に移動<br>
`^` 行の最初の文字へ移動<br>
`$` 行の終わりへ移動<br>
`g_` jump to the last non-blank character of the line<br>
`gg` go to the first line of the document<br>
`G` 最終行へ移動（番号を付けるとその行へ移動- 5Gは 5行目へ）<br>
`5G` 5行目に移動<br>
`fx` jump to next occurrence of character x<br>
`tx` jump to before next occurrence of character x<br>
`}` jump to next paragraph (or function/block, when editing code)<br>
`{` jump to previous paragraph (or function/block, when editing code)<br>
`Ctrl + b` move back one full screen<br>
`Ctrl + f` move forward one full screen<br>
`Ctrl + d` move forward 1/2 a screen<br>
`Ctrl + u` move back 1/2 a screen<br>
Tip これらのコマンドの前に番号を付けるとその回数分繰り返します。例えば、4j は 4行下に移動します。<br>

#挿入モード

テキストを追加/挿入  
`i` カーソル位置で挿入モードを開始<br>
`I` 行の先頭で挿入モードを開始<br>
`a` カーソル位置の直後で挿入モードを開始<br>
`A` 行の末尾で挿入モードを開始<br>
`o` 現在の行の下に空白行を追加して挿入モードを開始<br>
`O` 現在の行の上に空白行を追加して挿入モードを開始<br>
`ea` 単語の末尾で挿入モードを開始<br>
`Esc` 挿入モードを終了

# 編集

`r` 単一の文字を置き換える（挿入モードを使用しません）<br>
`J` 現在の行と次の行を連結する<br>
`cc` 現在の行を削除して挿入モードを開始<br>
`cw` カーソル位置の単語を削除して挿入モードを開始<br>
`c$` カーソル位置から行末までを削除して挿入モードを開始<br>
`s` カーソル位置の文字を削除して挿入モードを開始<br>
`S` 現在の行を削除して挿入モードを開始（ccと同じ）<br>
`xp` カーソル位置と次の文字を入れ替える（技術的にはカットしてペースト）<br>
`u` 元に戻す(アンドゥ)<br>
`Ctrl + r` やり直し(リドゥ)<br>
`.` 最後に使ったコマンドを行う

# テキストの選択（ビジュアルモード）

`v` ビジュアルモード開始。移動すると選択してその後にコマンドを実行できる（例えばY-ヤンク）<br>
`V` 行単位のビジュアルモードを開始<br>
`o` 選択範囲の反対側に移動する<br>
`Ctrl + v` 矩形ビジュアルモードを開始<br>
`O` ブロックの他のコーナーに移動する<br>
`aw` 単語をマーク<br>
`ab` () ブロックを選択(括弧ごと)<br>
`aB` {}ブロックを選択(括弧ごと)<br>
`ib` () ブロックを選択(括弧を除く)<br>
`iB` {}ブロックを選択(括弧を除く)<br>
`Esc` ビジュアルモード終了

# ビジュアルモードでのコマンド

`>` 選択範囲を右シフト<br>
`<` 選択範囲を左シフト<br>
`y` 選択範囲をヤンク（コピー）<br>
`d` 選択範囲を削除する<br>
`~` 大文字と小文字を入れ替える

# Registers

`:reg` show registers content<br>
`"xy` yank into register x<br>
`"0p` paste contents of register x<br>
Tip Registers are being stored in ~/.viminfo, and will be loaded again on next restart of vim.<br>
Tip Register 0 contains always the value of the last yank command.

# Marks

`:marks` list of marks<br>
`ma` set current position for mark A<br>
"`a" jump to position of mark A 
"y`a" yank text to position of mark A

# Macros

`qa` record macro a<br>
`qq` stop recording macro<br>
`@@` rerun last run macro

# カット＆ペースト

`yy` 現在の行をヤンク（コピー）<br>
`2yy` 2行をヤンク<br>
`yw` カーソル位置の単語をヤンク<br>
`y$` 現在行の行末までヤンク<br>
`p` カーソル位置の後にペースト<br>
`P` カーソル位置の前にペースト<br>
`dd` 現在の行をカット(コピーして削除)<br>
`2dd` 2行をカット<br>
`dw` カーソル位置の単語をカット<br>
`D` カーソル位置から行末までカット<br>
`d$` カーソル位置から行末までカット(Dと同じ)<br>
`x` 現在の文字をカットする

# 終了

`:w` 終了せずに保存<br>
`:w !sudo tee %` write out the current file using sudo<br>
`:wq or :x or ZZ` 保存して終了<br>
`:q` 保存せずに終了（変更点がある場合は終了できない）<br>
`:q! or ZQ` 保存せずに終了(変更点がある場合は破棄される)

# 検索/置換

`/pattern - /文字列` 文字列を検索<br>
`?pattern - ?文字列` 文字列を逆方向に検索<br>
`\vpattern` 'very magic' pattern: non-alphanumeric characters are interpreted as special regex symbols (no escaping needed)<br>
`n` 同じ方向に再検索<br>
`N` 逆方向に再検索<br>
`:%s/old/new/g` ファイル全体でoldをnewに置き換える<br>
`:%s/old/new/gc` ファイル全体でoldをnewに置き換える(確認あり)<br>
`:noh` remove highlighting of search matches

# Search in multiple files

`:vimgrep /pattern/ {file}` search for pattern in multiple files<br>
e.g. :vimgrep /foo/ _*/_<br>
`:cn` jump to the next match<br>
`:cp` jump to the previous match<br>
`:copen` open a window containing the list of matches

# 複数のファイルでの作業

`:e filename` 新しいバッファでファイルを編集<br>
`:bnext or :bn` 次のバッファに移動<br>
`:bprev or :bp` 前のバッファへ移動<br>
`:bd` バッファを削除（ファイルを閉じる）<br>
`:ls` list all open buffers<br>
`:sp filename` 新しいバッファおよび分割ウィンドウでファイルを編集<br>
`:vsp filename` 新しいバッファおよび垂直分割ウィンドウでファイルを開きます<br>
`Ctrl + ws` ウィンドウを分割<br>
`Ctrl + ww` ウィンドウを切り替える<br>
`Ctrl + wq` ウィンドウを終了します<br>
`Ctrl + wv` ウィンドウを垂直に分割<br>
`Ctrl + wh` 右のウィンドウに移動<br>
`Ctrl + wl` 左のウィンドウに移動<br>
`Ctrl + wj` move cursor to the window below (horizontal split)<br>
`Ctrl + wk` - move cursor to the window above (horizontal split)
