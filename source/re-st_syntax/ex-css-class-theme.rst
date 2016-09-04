.. vim:set expandtab tabstop=2 shiftwidth=2 softtabstop=2 autoindent smartindent ft=rst:

=============================
HTMLのカスタマイズ
=============================

テーマに触らないカスタマイズ
==============================

参考とヒント:

* `HTMLテーマのサポート — Sphinx 1.4.4 ドキュメント <http://docs.sphinx-users.jp/theming.html>`_

  * http://docs.sphinx-users.jp/theming.html
  * ``テンプレート`` の解説を参照。

* `ビルド設定ファイル(conf.py) — Sphinx 1.4.4 ドキュメント <http://docs.sphinx-users.jp/config.html>`_

  * http://docs.sphinx-users.jp/config.html
  * ``templates_path`` の解説を参照。

* `Sphinx FAQ — Sphinx 1.4.4 ドキュメント <http://docs.sphinx-users.jp/faq.html>`_

  * http://docs.sphinx-users.jp/faq.html
  * Google Analytics の解説を参照。

静的CSS/JSのカスタマイズ
--------------------------

* CSSのカスタマイズ : 見出しに顔文字を入れてます。

  .. literalinclude:: /_static/mycustom.css
    :caption: /_static/mycustom.css
    :language: css

* JSのカスタマイズ : console.logを見てみてください。

  .. literalinclude:: /_static/mycustom.js
    :caption: /_static/mycustom.js
    :language: js

上記CSS/JSは、conf.pyにて以下のように読み込んでます。

.. code-block:: python
  :caption: conf.py

  def setup(app):
    app.add_stylesheet('mycustom.css')
    app.add_javascript('mycustom.js')

layout.htmlのカスタマイズ
---------------------------

テーマの方でlayout.htmlに用意済みのblockや変数などは、:file:`/_templates/layout.html` で元のlayout.htmlを継承してカスタマイズできる。

.. literalinclude:: /_templates/layout.html
  :caption: /_templates/layout.html
  :language: html

ただし、当然テーマの方で用意していないblockは埋め込めない。同じテーマでも、バージョンによって新しいblockが追加されていたりするので、もし新し目のlayout.htmlカスタマイズ記事の通りにしても「あれ？このblockが展開されない・・・」となった場合は、インストールしているテーマのバージョンが古い可能性がある。


テーマのカスタマイズ
==============================

参考とヒント:

* http://docs.sphinx-users.jp/theming.html
* http://docs.sphinx-users.jp/templating.html
* http://heartbeats.jp/hbblog/2013/08/sphinx-customize-theme.html
* http://blog.amedama.jp/entry/2016/01/06/122931
* http://sphinx-users.jp/cookbook/makingwebsite/index.html

mytheme1 テーマのファイル内容
-------------------------------

.. literalinclude:: /theme_test/mytheme1/theme.conf
  :caption: /theme_test/mytheme1/theme.conf
  :language: none

.. literalinclude:: /theme_test/mytheme1/layout.html
  :caption: /theme_test/mytheme1/layout.html
  :language: html

.. literalinclude:: /theme_test/mytheme1/static/main.css
  :caption: /theme_test/mytheme1/static/main.css
  :language: css

.. literalinclude:: /theme_test/mytheme1/static/mytheme.css
  :caption: /theme_test/mytheme1/static/mytheme.css
  :language: css

.. literalinclude:: /theme_test/mytheme1/static/mytheme.js
  :caption: /theme_test/mytheme1/static/mytheme.js
  :language: js

mytheme1 のCSSクラスを使ってみる
----------------------------------

↓main.cssで定義した p要素の mytheme classを使用
.. rst-class:: mytheme

  ああああああああああ
  いいいいいいいいいい
  うううううううううう

  えええええええええええええ
  おおおおおおおおおおおおおお

↑ここまで。

ABCDEFG
ABCDEFG
ABCDEFG
ABCDEFG

↓main.cssで定義した p要素の mytheme classを使用

.. rst-class:: mytheme

  * item1
  * item1
  * item1
  * item1


↑ここまで。




