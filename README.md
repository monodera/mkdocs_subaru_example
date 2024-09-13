# Example of MkDocs for Subaru Telescope

## 環境の構築

### リポジトリのクローン

まずはこのリポジトリを適当なディレクトリでクローンして、そのディレクトリに移動してください。

```
git clone https://github.com/monodera/mkdocs_subaru_example.git
cd mkdocs_subaru_example
```

ウェブサイトのビルドにはPython が必要です。便宜的に 3.9 以上のバージョンとしましたが、それより前のものでも大丈夫かもしれません（自分は作成時に3.11.xを使っています。他のバージョンでは検証はしてません）。また、ウェブサイトのビルドには MkDocs というパッケージを使います（作成時は 1.4.2 を使いました）。

### Python 仮想環境の作成

```
# 仮想環境の作成
python3 -m venv .venv

# 仮想環境のアクティベート
source .venv/bin/activate
```

### MkDocs のインストール

```
python3 -m pip install mkdocs
```

## ウェブサイトのテスト

ウェブサイトをローカル環境で試すには以下のコマンドを実行してください。

```
mkdocs serve
```

ブラウザで [http://127.0.0.1:8000/](http://127.0.0.1:8000/) を開いてください。エラーになる場合は、ターミナルで表示されたURLを確認してそれを開いてください。

このモード (`serve`) では、`docs` 以下のファイルや、設定ファイルである `mkdocs.yml` を変更すると自動でリロードされます。開発時はこれをつかうとよいでしょう。

終了するには `Ctrl-C` を押します（2回押す必要があるかもしれません）。


## ウェブサイトのビルド

ウェブサイトをビルドするときは以下のコマンドを実行してください。

```
mkdocs build
```

これでエラーが出なければ、ビルドされたファイルが `site/` 以下にできていると思います。これを任意の場所に置くことでウェブサイトの更新ができます。

例を以下のサイトに示しました: https://www.naoj.org/staff/monodera/test_subaru_website/
