# セッションの作成

セッションは、 tmux コマンドを実行するだけで作成されます。<br>
自動的にセッション名として、数字が割り当てられます。

`tmux`<br>
セッション名をつけるには、new-sessionと -s オプションを使います。<br>
dev という名前のセッションを作成するには、下記コマンドを実行します。<br>
`tmux new-session -s dev`<br>
new-session には、省略されたエイリアス(alias) new があります。<br>
`tmux new -s dev`<br>
すでに存在するセッションを指定すると、作成できずに失敗します。<br>
`tmux new -s dev`<br>
`duplicate session: dev`<br>
セッションのデタッチ

セッションのデタッチのtmuxのエスケープ + d を実行します。<br>
`C-b d`<br>
セッションの確認

存在するセッションを確認するには、 list-sessions コマンドを使います。<br>
tmux list-sessions list-sessionには、エイリアス ls もあります。

実行例

```
tmux ls  
0: 2 windows (created Sun Oct 11 00:35:50 2009) [80x23]  
1: 1 windows (created Sun Oct 18 00:49:52 2009) [80x23]  
2: 1 windows (created Sun Oct 25 12:28:47 2009) [80x23]  
dev: 1 windows (created Sun Oct  25 12:29:51 2009) [80x23]
```

# セッションをアタッチする

セッションをアタッチするには、 attach-session コマンドを使用します。<br>
attach-session のエイリアスとして attach もありますが、 より省略した a でアタッチすることが可能です。

`tmux a` セッション名を指定しない場合、最後に作成されたセッションがアタッチされます。

セッション名を指定してセッションをアタッチする場合には、 -t でセッション名を指定します。<br>
セッション 0 をアタッチするには、以下のコマンドを実行します。<br>
`tmux a -t 0`<br>
セッション 1 をアタッチするには、以下のコマンドを実行します。<br>
`tmux a -t 1`<br>
マルチアタッチしているときに、ほかのアタッチをデタッチして、アタッチするには、 -d オプションを指定します。<br>
screen -rd hoge と同じです。<br>
`tmux a -d -t 1`<br>
アタッチしているセッションを調べる<br>
現在、アタッチしているすべてのセッションを調べるには、list-clients(alias: lsc) を使用します。<br>
`tmux lsc`<br>

# セッション名のリネーム

セッション名を変更することが可能です。<br>
この例では、セッション 0 を foo という名前に変更します。<br>
`tmux rename-session -t 0 foo`

or

`tmux rename -t 0 foo`<br>

# セッションの削除

tmux のセッションを削除するには、アタッチしているセッションのすべてのウィンドウを終了させてもよいですが、 tmux コマンドで削除することもできます。

最後のセッションを削除するには、以下のコマンドを実行します。<br>
`tmux kill-session`<br>
セッション名を指定して削除することも可能です。<br>
セッション 0 と 1 があるときに、セッション 0 を削除するには、 -t でセッション名を指定します。<br>
`tmux kill-session -t 0`<br>
すべてのセッションを終了させる

一度にすべてのセッションを削除するには、 tmux server を kill することで、すべてのセッションを終了させることができます。<br>
複数のセッションがある状態で、下記コマンドを実行すると、起動しているセッションがすべて終了します。<br>
`tmux kill-server`
