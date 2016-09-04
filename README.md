# sphinx-rest-exercise1

Sphinx を使った reStructuredText の練習その1です。

実際にHTMLビルダーで生成したサイト : https://msakamoto-sf.github.io/sphinx-rest-exercise1/

検証環境 : `CentOS7 (64bit)` (pythonやShinxのバージョンなどは後述)

Sphinxのバージョン : 1.4.6 以上 (1.3で追加された `numref` なども使ってる。他にも1.4以降の機能を使ってるので、左記バージョン以上とさせてください。)

## Sphinxのインストール

### 1. pyenvのインストール : https://github.com/yyuu/pyenv

```
$ sudo yum groupinstall "Development Tools"
$ sudo yum install zlib-devel bzip2 bzip2-devel readline-devel sqlite sqlite-devel openssl-devel xz
$ git clone https://github.com/yyuu/pyenv.git ~/.pyenv
$ echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
$ echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
$ echo 'eval "$(pyenv init -)"' >> ~/.bashrc
$ source ~/.bashrc
$ pyenv install 2.7.12
$ pyenv global 2.7.12
```

### 2. pyenv-virtualenv のインストール : https://github.com/yyuu/pyenv-virtualenv

```
$ git clone https://github.com/yyuu/pyenv-virtualenv.git ~/.pyenv/plugins/pyenv-virtualenv
$ echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bashrc
$ source ~/.bashrc
```

### 3. Sphinx用のvirtualenv作成とインストール

```
$ pyenv virtualenv 2.7.12 sphinxt1

(cd to test dir)

$ pyenv local 2.7.12/envs/sphinxt1
$ pip install Sphinx
$ pyenv rehash
```

### 4. sphinx_rtd_theme を使うのでpipでインストール : https://github.com/snide/sphinx_rtd_theme

```
$ pip install sphinx_rtd_theme
```

### 5. sphinxドキュメントの作成（初回のみ）

```
$ sphinx-quickstart
```

参考：検証時点(2016-09-03)でインストールされたパッケージとバージョン

```
$ pip list
alabaster (0.7.9)
Babel (2.3.4)
docutils (0.12)
imagesize (0.7.1)
Jinja2 (2.8)
MarkupSafe (0.23)
pip (8.1.2)
Pygments (2.1.3)
pytz (2016.6.1)
setuptools (26.1.1)
six (1.10.0)
snowballstemmer (1.2.1)
Sphinx (1.4.6)
sphinx-rtd-theme (0.1.9)
wheel (0.29.0)
```

## HTMLのビルド

```
$ make clean html
```

なお github-pages が認識する `docs/` ディレクトリに出力できるよう、`Makefile` をカスタマイズしてます。

# Sphinx や reStructuredText の参考サイト

reStructuredTextの仕様を含む、ベースとなっているdocutils関連：

 * Docutils Project Documentation Overview
   * http://docutils.sourceforge.net/docs/
   * この中に reStructuredText の本家リファレンスが含まれている。
 * Docutils (Sphinx-Users.jp からの日本語訳)
   * http://docutils.sphinx-users.jp/

Sphinx, Sphinx-Users.jp：

 * Sphinx 公式
   * http://www.sphinx-doc.org/en/stable/
 * Sphinx-Users.jp — Python製ドキュメンテーションビルダー、Sphinxの日本ユーザ会
   * http://sphinx-users.jp/
   * 日本語リファレンスだけでなく、逆引きガイドやクックブックなど、実践的な情報も揃っている。
 * Sphinx-Users.jp からのTwitterハッシュタグ : `#sphinxjp`
   * https://twitter.com/search?q=%23sphinxjp

チュートリアルなど：

 * sphinx handson — study sphinx 1 documentation
   * http://planset-study-sphinx.readthedocs.io/ja/latest/index.html




