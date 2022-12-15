# Gitコマンド一覧

<br>&emsp;コマンドプロンプトまたはGitBash上でGitコマンドを実行することにより、リポジトリをはじめGitの各機能を簡単に利用できる。なお、実行には[Git for Windows](https://gitforwindows.org/)をインストールする必要がある。

## 1. Gitの初期設定（GitHubアカウントの設定とは別）

- `git --version`　Gitのバージョン確認
- `git config --global user.name 任意のユーザ名`　ユーザ名を設定
- `git config --global user.email 任意のメールアドレス`　メールアドレスを設定
- `git config --list`　ユーザ名とメールアドレスを確認

## 2. ローカルリポジトリの作成

- `git init`　実施したディレクトリをGitリポジトリとする

## 3. ローカルリポジトリでAddする

- `git add ファイル名.拡張子`　 ファイルをステージングエリアに追加
    <dl>
      <dt>ステージングエリア(インデックスエリア)</dt>
      <dd>Gitにコミットする前にファイルを選択して置いておくところ。置かれたファイルがコミット対象となる。</dd>
    </dl>
- `git add ディレクトリ名`　ディレクトリをステージングエリアに追加
- `git add -A`　ワークツリー内の変更内容を全てステージングエリアに追加
- `git status`　ステージングエリアのファイルを確認する
- `git reset HEAD`　ステージされているファイルをすべて解除
- `git reset HEAD ファイルパス`　ファイルパスのファイルのみステージを解除

## 4. ローカルリポジトリでCommitする

- `git commit -m "メッセージ"`　ステージングエリアのファイルをメッセージ付きでコミットする
- `git commit -a -m "メッセージ"`　新規ファイルを除く、変更されたファイルを全てステージし、メッセージ付でコミットする
- `git commit -F- << EOM`　複数行メッセージを追加し、コミットする　GitBashからのみ実行可能
- `git reset --hard ORIG_HEAD`　直前のコミット後の状態に戻す
- `git reset --hard コミットID`　ワークツリーを含めた全てをコミットIDのコミット後の状態に戻す
- `git log`　最近のコミットを上から順番に表示

## 5. リモートリポジトリ（GitHub）にPushする

- `git remote add origin https://github.com/ユーザ名/リモートリポジトリ名.git`　ローカルリポジトリとリモートリポジトリを紐づけする
- `git push origin ブランチ名`　リモートリポジトリの指定したブランチにコミット内容をプッシュする
  <br>＊originはリモートリポジトリのこと

## 6. リポジトリをCloneする

- `git clone https://github.com/ユーザ名/リモートリポジトリ名.git`　リモートリポジトリからローカルリポジトリへクローンする

## 7. ブランチを作成する

- `git branch ブランチ名`　ローカルリポジトリブランチを作成する
- `git checkout ブランチ名`　作業するブランチを指定する
- `git branch`　ローカルリポジトリに存在するブランチを確認する

## 8. リモートリポジトリからローカルリポジトリへPullする

- `git pull origin ブランチ名`　リモートリポジトリの指定したブランチからプルする
- `git pull`　リモートリポジトリのデフォルトブランチからプルする

## 9. リモートリポジトリをFetchする

- `git fetch origin ブランチ名`　指定したブランチをフェッチする
  <br>＊プルは内部で「フェッチ ＋ マージ」をしているので、プルをしていれば必須ではない。リモートリポジトリの最新の変更内容のみ取得したいときに有用。

## 10. ブランチをMergeする

- `git merge ブランチ名`　指定したブランチをマージする
  <br>＊プルをしていれば必須ではない。マージのみを行いたいときに有用。

---

## 参考サイト

[1]. [【超入門】初心者のためのGitとGitHubの使い方](https://tech-blog.rakus.co.jp/entry/20200529/git#2-5-%E3%82%B3%E3%83%BC%E3%83%89%E3%83%AC%E3%83%93%E3%83%A5%E3%83%BC%E3%83%9E%E3%83%BC%E3%82%B8)

[2]. [【Git入門】commitした後にgit pushしてみよう【わかりやすく解説】](https://codelikes.com/git-commit-push/?amp=1)

[3]. [基本的なGitコマンドまとめ](https://qiita.com/2m1tsu3/items/6d49374230afab251337)