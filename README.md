# git_CheetSheet
githubコマンドの個人用のチートシート

## 1. 目的
githubのコマンドをよく忘れるので、備忘録。
徐々に付け足し付け足しで書いていく。

## 2. 基礎知識

ローカルは3つのエリアに分かれている。
- リポジトリ(ローカルリポジトリ)
    - ローカル上のリポジトリ。このエリアにcommit後、リモートリポジトリにPushする。
- ステージ
    - ローカルリポジトリにcommitする変更の前準備に利用する。
    このエリアへはgit addコマンドで変更を追加していく。
    git add <ファイル名>で個別にも変更をローカルリポジトリに反映できるので、本当にcommitしたい変更だけを反映できる。
- ワークツリー
    - 作業するディレクトリのこと。
<img width="937" alt="スクリーンショット 2022-12-04 19 19 33" src="https://user-images.githubusercontent.com/103823940/205485474-d0307901-95c4-4c00-82c8-074ae013159e.png">
## 3. 内容
~~~
git init
~~~ 
ワークツリー上でgitファイルを作成したい時に利用するコマンド。
まず、git上でリポジトリを作成してからcloneしてくると既にinitされている状態なので、その場合は実行不要。

~~~
git clone <URL>
~~~
git上に既に存在するリポジトリからcloneしてくるときのコマンド

指定するURLは画像の通り
<img width="1297" alt="スクリーンショット 2022-12-04 19 33 40" src="https://user-images.githubusercontent.com/103823940/205485909-60a9284d-ad9d-4907-b0e4-62ecc3211c24.png">

~~~
git add <ファイル名>
git add <ディレクリ名>
git add . //全部
~~~
ステージに変更を反映するコマンド。commiteする前に必要。
~~~
git commit
git commit -m "<メッセージ>" //エディタを立ち上げなくてもOK
git commit -v //変更したファイルも確認できる
~~~
コミットメッセージはわかりやすく書くことが大切。
- 簡潔に書く時は変更内容要点と理由を一行で書く
- 正式に書く時は変更内容の要約を書いて、一行空けて変更理由を書く。
~~~
git status
~~~
現在の変更状況を確認できるコマンド

ワークツリー⇄ステージとステージ⇄ローカルリポジトリの変更差分を確認できる。
<img width="767" alt="スクリーンショット 2022-12-04 20 51 01" src="https://user-images.githubusercontent.com/103823940/205488780-c297f8a3-f42c-4273-b604-d267379fdb7f.png">
~~~
git log
~~~
commitした履歴を確認できる。
<img width="769" alt="スクリーンショット 2022-12-04 20 55 19" src="https://user-images.githubusercontent.com/103823940/205488993-3c9f25c0-6207-4b17-b4d3-867655812ca9.png">
~~~
git remote add origin <URL>
~~~
originというショートカットでURLのリモートリポジトリを登録する。
cloneしてくると元々のリモートリポジトリの内容をoriginに割り当られている。
<img width="768" alt="スクリーンショット 2022-12-04 20 59 49" src="https://user-images.githubusercontent.com/103823940/205489359-497b9d49-5733-4861-949a-2ba2bcc72174.png">
~~~
git push origin master //通常
git push -u origin master(main) //-u は次回以降ユーザ名とトークンの入力を省略できる
git push //-u で初回実行した場合
~~~
pushを行う際はトークンの入力が求められるので、事前にgitのsettings.Developer settingsに遷移してトークンを発行しておくようにしよう。

