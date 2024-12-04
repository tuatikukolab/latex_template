# LaTeXで論文を書くためのテンプレート

[![Test Docker Image](https://github.com/being24/latex-template-ja/actions/workflows/test.yml/badge.svg)](https://github.com/being24/latex-template-ja/actions/workflows/test.yml)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)

このLaTeX(TeXはテフと読みます．テックスとは読みません)実行環境は，[こちら](https://github.com/being24/latex-template-ja)を参考に，本研究室向けに内容を改良したものです．
LaTeXのテンプレートは，先輩から代々受け継がれているテンプレートをもとに，体裁を整えたものを載せています．

## Release note

* 2024/12/4 README.mdを増強，フォルダの整理
* 2024/10/22 README.mdを増強，トラブルシューティング
* 2024/10/21 各種TeXファイルを作成

## Function

* 個人環境にLaTeX workshopを構築せず、dockerでビルドします
* github上にreleaseします
* 論文のテンプレートを持ちます

## Environment & Preparation

* Windows 10 or later
* macOS 10.14 or later
* Ubuntu 18.04 LTS or later

Docker, VSCode, Gitのインストールが必要です．

### Docker

Dockerを使うことで，面倒な環境構築をなしにLaTeXの実行ができます．[こちら](https://docs.docker.com/desktop/install/windows-install/)からDocker Desktopをインストールしておいてください．環境変数PATHが正しく設定されていることを確認してください．確認するためには，コマンドプロンプトを開いて
```
docker
```
と入力します．コマンドの説明が出てきたらインストールできています．
また，Dockerのアカウント登録を行って(個人メールアドレスでの登録を推奨)，Docker Desktopにログインしてください．

### VSCode

今回はエディタにVSCodeを用います．[こちら](https://code.visualstudio.com/)からインストールしておいてください．

### Git

論文のテンプレートをダウンロードするために，Gitを用います．[こちら](https://git-scm.com/downloads)からインストールしておいてください．環境変数PATHが正しく設定されていることを確認してください．確認するためには，コマンドプロンプトを開いて
```
git
```
と入力します．コマンドの説明が出てきたらインストールできています．
また，Githubのアカウント登録を行って(個人メールアドレスでの登録を推奨)，Githubにログインしてください．

## How to use

ここから，環境構築について説明します．やることは大きく分けて3つです．
* docker imageの入手
* Githubを使ったテンプレートのダウンロード
* VSCodeの設定とファイルのコンパイル方法確認

windowsを例として，[こちら](https://zenn.dev/being/articles/how-to-use-my-latex)の元記事を参考にもう少し詳しく説明します．

### Pull the docker image

まず，Docker Desktopがダウンロードされており，起動＆ログイン済みであることを確認してください．

はじめに，コマンドプロンプトを起動し，以下のコマンドを入力してください．
```
docker pull ghcr.io/being24/latex-docker:latest
```

docker imageのダウンロードが始まります．約5GBほどあるので，時間がかかります．
(また，ハードウェア側で仮想環境を使えない設定にしている場合，上手くpullできないそうです．その場合は，BIOSから仮想環境の設定をenableにしてください．使っているPCによってBIOSの設定画面は異なるので，ネット等で調べてください)

次に，コマンドプロンプトに以下のコマンドを入力してください．
```
docker images
```

レポジトリの欄に`ghcr.io/being24/latex-docker`があれば，成功しています．コマンドプロンプトは起動したままにしておいてください．

### Create new repository

まず，Gitがインストール済みであり，環境変数PATHが正しく通っていることを確認してください．

はじめに，[こちら](https://github.com/tuatikukolab/latex_template)を開きます．

次に，右上にある`Use this templete`から，`Create new repository`を選択します．これにより，論文のテンプレートを丸ごとコピーした自分のリポジトリを作成できます．

設定は下の画像を参考にしてください．Repository nameは例としてBachelor thesis(学士論文)にしていますが，好きな名前を付けてください．

![newrepo](https://github.com/user-attachments/assets/d45612aa-9861-4540-9af5-7a8d935f03eb)

最後に`Create repository`をクリックしてください．今後はこのリポジトリを使ってcloneおよび編集を行います．

### Clone the templete

※Ubuntu(Linux)ではHTTPSを使用したクローンができません．[こちら](https://qiita.com/shizuma/items/2b2f873a0034839e47ce)のサイトを参考にして，SSH接続によるクローンを行ってください．

はじめに，先ほど作成した自分のリポジトリの右上にある`<> Code`をクリックし，表示されているURLをコピーしてください．

![clonerepo](https://github.com/user-attachments/assets/8041c4db-edc1-4ed7-9a3d-623f300ec0f3)

次に，先ほど起動したままにしておいたコマンドプロンプトを使って，LaTeXのテンプレートをダウンロードしたいディレクトリに移動してください．

その後，以下のコマンドを入力してください(<>の部分は適宜書き換えてください．<>は入力する必要ありません)．
```
git clone <ここにGithubからコピーしたURL>
```
リポジトリをPrivateで作製したため，途中でログインを求められます．GithubのIDとパスワードでログインしてください．

done.が出てきたら，成功しています．

また，gitを使うことで複数のコンピュータでの論文執筆が可能になります(めちゃくちゃ使いやすいGoogle Driveのイメージです)．[こちら](manual/how_to_use_git.md)にgitのコマンドの使い方をまとめたので参考にしてください．

### Use the template

Docker Desktopが起動＆ログイン済みであることを確認してください．

はじめに，vscodeを開きFlie->Open Folder...から先ほどダウンロードしたフォルダを開いてください．
このとき，右下に拡張機能のインストール画面やバナーが出てきた場合はいったん全てインストールしてください．
また，もしインストール済みでなければ，左側の「Extensions」アイコンから**LaTeX workshop**および**Remote Development**を検索してインストールしてください．
(LaTeX workshopはふたつあるそうです．James Yuさんが作成した方をインストールしてください．)

次に，左側のEXPLORERからmain.texを選択し，左側のメニューから「TeX」アイコンをクリックし，その後右上の緑色の矢印(カーソルオンすると，Build LaTeX projectと表示される)をクリックしてください．

画面下側の循環矢印とBuildの表示がチェックマークに変われば，コンパイルが成功しています．
EXPLORERからout->main.pdfの順にクリックして，pdfファイルを確認してください．

もし画面下側の循環矢印とBuildの表示が赤色のバツマークになり，右下にエラー内容が表示される場合，Dockerコンテナのなかに入れていないことが考えられます．その場合，F1キーを押し，Dev Containersと入力して出てくる**Open Folder in Container...** をクリックしてフォルダを開いてください．

### When start VSCode again

2回目以降に起動する場合も，はじめにDocker desktopを起動してからVSCodeを起動してください．

## About the template

実際に編集するファイルは，~.texファイルのみです．不必要にファイルを編集するとコンパイルできなくなる恐れがありますので，注意してください．

出力されるpdfファイルは，outフォルダのなかにあります．こちらをダウンロードして先生に提出してください．

図や表をまとめるために，figureフォルダおよびtableフォルダを作成してあります．お好みに応じてご使用ください．

先輩から代々受け継がれているテンプレートをもとに，体裁を整えたものを載せています．1章ではLaTeXの使用経験があまりない学生を対象に初歩的な使用法をまとめています．誤りがあった場合や，新たに加えてほしい内容がありましたら教えていただけると幸いです．  
実際の使用時は，1章に載せた使用法は消してください．

また，コンパイルの際にデフォルトで2点のcautionが出ます(caption.styおよびmain.tex)が，気にしないでください．

## Config

`.vscode/settings.json`は，[こちら](https://github.com/being24/latex-template-ja)のテンプレートにあったものを引用しています．
VSCodeはこの設定を自動で読み込むため，設定を変更する必要は無いそうです．

## Contact

不明点は穂苅彩音(hokaria.tuat@gmail.com)に聞いてください．

## 参考URL

<https://github.com/being24/latex-template-ja>

<https://poyo.hatenablog.jp/entry/2020/12/05/110000>

<https://qiita.com/shizuma/items/2b2f873a0034839e47ce>
