# LaTeXで論文を書くためのテンプレート

[![Test Docker Image](https://github.com/being24/latex-template-ja/actions/workflows/test.yml/badge.svg)](https://github.com/being24/latex-template-ja/actions/workflows/test.yml)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)

このLaTeXテンプレートは，[こちら](https://github.com/being24/latex-template-ja)のテンプレートを参考に，本研究室向けに内容を改良したものです．

## Release note

* 2024/10/22 README.mdを増強
* 2024/10/21 各種TeXファイルを作成

## Function

* 個人環境にLaTeX workshopを構築せず、dockerでビルドします
* GitHub Actionsを使用してtextlintを実行します
* github上にreleaseします
* 論文のテンプレートを持ちます

## Environment

* Windows 10 or later
* macOS 10.14 or later
* Ubuntu 18.04 LTS or later

Docker環境が必要です．

* Docker Desktop for Mac 2.1 or later
* Docker 18.06 or later
* Docker Desktop for Windows

windowsの場合は，[こちら](https://docs.docker.com/desktop/install/windows-install/)からDocker Desktop on Windowsをインストールしておいてください．環境変数PATHが正しく設定されていることを確認してください．確認するためには，コマンドプロンプトを開いて
```
where docker
```
と入力します．
あとで[こちらのリポジトリ](https://github.com/being24/latex-docker)のghcr.io/being24/latex-docker を使用します．詳しくは後ほど説明します．

VSCodeが必要です．[こちら](https://code.visualstudio.com/)からインストールしておいてください．

Gitも必要です．[こちら](https://git-scm.com/downloads)からインストールしておいてください．環境変数PATHが正しく設定されていることを確認してください．確認するためには，コマンドプロンプトを開いて
```
where git
```
と入力します．

## How to use

ここでは，windowsを例としてdocker imageの入手からテンプレートの出力までを[こちら](https://zenn.dev/being/articles/how-to-use-my-latex)の元記事を参考にもう少し詳しく説明します．

### Pull the docker image

Docker Desktop on Windowsがダウンロードされており，新規登録済みであることを確認してください．

はじめに，コマンドプロンプトを起動し，以下のコマンドを入力してください．
```
docker pull ghcr.io/being24/latex-docker:latest
```

(ハードウェア側で仮想環境を使えない設定にしている場合，上手くpullできないそうです．その場合は，BIOSから仮想環境の設定をenableにしてください．使っているPCによってBIOSの設定画面は異なるので，ネット等で調べてください)

次に，以下のコマンドを入力してください．
```
docker images
```

レポジトリの欄に`ghcr.io/being24/latex-docker`があれば，成功しています．

### Clone the templete

Gitがインストール済みであり，環境変数PATHが正しく通っていることを確認してください．

はじめに，コマンドプロンプトを使って，LaTeXのテンプレートをダウンロードしたいディレクトリに移動してください．

次に，以下のコマンドを入力してください．
```
git clone https://github.com/tuatikukolab/latex_template.git
```
途中でログインを求められるので，ログインしてください．
done.が出てきたら，成功しています．

### Use the template

はじめに，vscodeを開きFlie->Open Folder...から先ほどダウンロードしたフォルダを開いてください．
このとき，拡張機能のインストール画面やバナーが出てきた場合はいったん全てインストールしてください．
また，もしインストール済みでなければ，左側の「Extensions」アイコンから**LaTeX workshop**および**Remote Development**を検索してインストールしてください．
(LaTeX workshopはふたつあるそうです．James Yuさんが作成した方をインストールしてください．)

次に，左側のメニューから「TeX」アイコンをクリックし，COMMANDSから「Build LaTeX project」→「Recipe: compile」の順にクリックしてTeXファイルのコンパイルをしてください．
TeXファイルを表示している場合はウィンドウ右上の緑の矢印をクリックしても同様にコンパイルできます．

最後に，COMMANDSから「View LeTeX PDF」をクリックしてください．pdfファイルが出力されたら，成功しています．

## Config

`.vscode/settings.json`は，[こちら](https://github.com/being24/latex-template-ja)のテンプレートにあったものを引用しています．
VSCodeはこの設定を自動で読み込むため，設定を変更する必要は無いそうです．

## About the template

先輩から代々受け継がれているテンプレートをもとに，体裁を整えたものを載せています．1章ではLaTeXの使用経験があまりない学生を対象に初歩的な使用法をまとめています．誤りがあった場合や，新たに加えてほしい内容がありましたら教えていただけると幸いです．  
実際の使用時は，1章に載せた使用法は消してください．

また，コンパイルの際にデフォルトで2点のcautionが出ます(caption.styおよびmain.tex)が，気にしないでください．

## Contact

dockerやgithubまわりのエラーは，斎藤雅史君か江﨑郁磨君に聞いてください．

LaTeXまわりのエラーは穂苅彩音(hokaria.tuat@gmail.com)に聞いてください．

## 参考URL

<https://github.com/being24/latex-template-ja>

<https://poyo.hatenablog.jp/entry/2020/12/05/110000>
