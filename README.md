# Example of MkDocs for Subaru Telescope

## 環境の構築

まずはこのリポジトリをクローンして、そのディレクトリに移動してください。

```
git clone https://github.com/monodera/mkdocs_subaru_example.git
cd mkdocs_subaru_example
```

ウェブサイトのビルドにはPython が必要です。便宜的に 3.8 以上のバージョンとしましたが、それより前のものでも大丈夫かもしれません（自分は作成時に3.11.1を使っています。他のバージョンでは検証はしてません）。
また、ウェブサイトのビルドには MkDocs というパッケージを使います（作成時は 1.4.2 を使いました）。

`poetry` や `pdm` といったパッケージマネージャを使っている場合は、`pyproject.toml` をつかって必要なパッケージをインストールすることができます（わたしは pdm を使っています。他は検証してません）。

```shell
pdm install
# poetry install
```

通常のPythonの場合は、多分以下のコマンドでパッケージが入ると思います。

```
python3 -m pip install mkdocs
```

## ウェブサイトのテスト

ウェブサイトをローカル環境で試すには以下のコマンドを実行してください。

```
# pdm
pdm run mkdocs serve

# poetry
poetry run mkdocs serve

# その他
mkdocs serve
```

ブラウザで [http://127.0.0.1:8000/](http://127.0.0.1:8000/) を開いてください。エラーになる場合は、ターミナルで表示されたURLを確認してそれを開いてください。

このモード (`serve`) では、`docs` 以下のファイルや、設定ファイルである `mkdocs.yml` を変更すると自動でリロードされます。開発時はこれをつかうとよいでしょう。

終了するには `Ctrl-C` を押します（2回押す必要があるかもしれません）。


## ウェブサイトのビルド

ウェブサイトをビルドするときは以下のコマンドを実行してください。

```
# pdm
pdm run mkdocs build

# poetry
poetry run mkdocs build

# その他
mkdocs build
```

これでエラーが出なければ、ビルドされたファイルが `site/` 以下にできていると思います。これを任意の場所に置くことでウェブサイトの更新ができます。

例を以下のサイトに示しました: http://www1.subaru.nao.ac.jp/~monodera/public/test_subaru_website/



