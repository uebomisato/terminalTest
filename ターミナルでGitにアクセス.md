# ターミナルからGitにプッシュしてみる

▼参考サイト

- 【GitHub超初心者入門】この前初めてGitHubを使い始めたエンジニア見習いが書くGitHubの使い方と実践～とりあえず一緒に動かしてみようぜ！～
    https://qiita.com/nnahito/items/565f8755e70c51532459

- GitHub 初心者の最初のプッシュ
    https://qiita.com/folivora/items/763d06b26bafd573a456

- 【GitHub】terminalを使った導入からpushまで【Mac】
    https://qiita.com/sub_nira/items/b57d5bf3d69b3cac3364

## 手順

1. Terminalで作業するディレクトリまで移動

```
Terminal (例)

$ cd /Users/misato/Desktop/PrivatePractice/Terminal_Test
```

2. gitのユーザ設定
初回のみ。2回目以降は必要なし。

```
$ git config --global user.email [Githubに登録したemail-adress]
```

3. gitの初期化
初回のみ。2回目以降は必要なし。
これで、Git管理したいフォルダに``.git``が作成される。

```
$ git init
```

4. 変更ファイルをadd
addとは、変更したファイルのcommitするための準備。
.(ドッド)と打つと、**自動的にすべての変更されたファイルをaddの対象にできる。**

```
$ git add .
```

5. 変更ファイルをcommit

```
$ git commit -m "ここにコメント書くよー！"
```

6. リモートリポジトリの登録
初回のみ。2回目以降は必要なし。

```
Terminal (例)

$ git remote add origin https://github.com/uebomisato/terminalTest.git
```

7. 変更点をpush

```
$ git push origin master
```

今回、``git push -u origin``で行なった。

- `git push -u` オプションの意味について
    > git push -u origin master とすると次回から git push だけで勝手に origin master で push してくれる。

- エラーで出てきた``git push --set-upstream origin master``について
    ```
    $ git push
    fatal: The current branch master has no upstream branch.
    To push the current branch and set the remote as upstream, use

    git push --set-upstream origin master
    ```
    upstream branchがないのでgit push --set-upstream origin (ブランチ)でセットしてくださいね。というもの。
※ 今回はマスターブランチにいたので（ブランチ）がmasterになっている。

-> ``git push --set-upstream origin master``を入力後、エンターでOK.