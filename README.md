# LaTeXで論文を書くためのテンプレート

[![Test Docker Image](https://github.com/being24/latex-template-ja/actions/workflows/test.yml/badge.svg)](https://github.com/being24/latex-template-ja/actions/workflows/test.yml)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)

このLaTeXテンプレートは，[こちら](https://github.com/being24/latex-template-ja)のテンプレートを参考に，本研究室向けに内容を改良したものです．

## Release note

* 2024/10/20 readme.mdを変更

## Function

* 個人環境にLaTeX workshopを構築せず、dockerでビルドします
* GitHub Actionsを使用してtextlintを実行します
* github上にreleaseします
* レジュメや論文用のテンプレートを持ちますが、あくまで個人の環境用に構築したものです

## Environment

* Windows 10 or later
* macOS 10.14 or later
* Ubuntu 18.04 LTS or later

Docker環境が必要です．

* Docker Desktop for Mac 2.1 or later
* Docker 18.06 or later
* Docker Desktop for Windows

windowsの場合は，[こちら](https://docs.docker.com/desktop/install/windows-install/)からDocker Desktop on Windowsをインストールしておいてください．

VSCodeが必要です．[こちら](https://code.visualstudio.com/)からインストールしておいてください．

また，ghcr.io/being24/latex-docker を使用します．詳しくはあとで説明します
ビルド用のdocker imageは[こちらのリポジトリ](https://github.com/being24/latex-docker)を参照してください


## How to use

ここでは，windowsを例として説明します．

# pull the docker image

はじめに，Docker Desktop on Windowsがダウンロードされており，sign upされていることを確認してください．

次に，コマンドプロンプトを起動し，以下のコマンドを入力してください．
"""
docker pull ghcr.io/being24/latex-docker:latest
"""

docker imageのpullが終わったら，次のコマンドを入力してください．
"""
docker images
"""

レポジトリの欄に'ghcr.io/being24/latex-docker'があれば，成功しています．

# clone the templete

はじめに，コマンドプロンプトを使って，LaTeXのテンプレートをダウンロードしたいディレクトリに移動してください．
"""
cd ダウンロードしたいところ
"""

次に，以下のコマンドを入力してください．
"""
git clone https://github.com/tuatikukolab/latex_template.git
"""
途中でログインを求められるので，ログインしてください．
done.が出てきたら，成功しています．

# use the templete

はじめに，vscodeを開き'Open Folder...'から先ほどダウンロードしたフォルダを開いてください．
このとき，拡張機能のインストール画面やバナーが出てきた場合はいったん全てインストールしてください．
また，左側の「Extensions」アイコンをクリックし，'LaTeX workshop'および'Remote Development'を検索してインストールしてください．

次に，左側の「LaTeX」アイコンをクリックし，COMMANDSから「Build LaTeX project」→「Recipe: compile」の順にクリックしてください．

最後に，「View LeTeX PDF」をクリックしてください．pdfファイルが出力されたら，成功しています．

（参考：元記事は[こちら](https://zenn.dev/being/articles/how-to-use-my-latex)です）

## License

CC0

## Author

Being

## config

VSCode上での設定例は[settings.json](.vscode/settings.json)を参照してください

## テンプレートについて

できるだけ現代的な設定を意識して作成したテンプレートですが、LaTeXに詳しいわけではないので誤りがあった場合は教えていただけると幸いです  
実際の使用時はexample等必要のないファイルは消してください

jlistingの代わりにmintedを使用し、参考文献はbiblatexを使用します
(mintedは環境によっては使用できないため、コメントアウトしてあります)

### resume.cls

[resume.cls](/classes/resume.cls)は2段組みのレジュメを作成するためのクラスファイルです  
使用方法は[例](/example/tex/resume_template.tex)を参照してください

### report.cls

[report.cls](/classes/report.cls)は論文を作成するためのクラスファイルです  
使用方法は[例](/example/tex/report_template.tex)を参照してください

### .vscode/settings.jsonについて

使用しやすい設定を参考程度ですが上げておきます。  
VSCodeであればこの設定を読み込んでくれるため、設定を変更する必要はありません

## 参考URL

<https://poyo.hatenablog.jp/entry/2020/12/05/110000>
