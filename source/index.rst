.. vim:set expandtab tabstop=2 shiftwidth=2 softtabstop=2 autoindent smartindent ft=rst:
.. sphinx-test1 documentation master file, created by
   sphinx-quickstart on Sat Sep  3 17:07:20 2016.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

========================================
Sphinxとrestの練習
========================================

.. contents:: このページ内の目次
   一覧

**toctreeのselfには、numberedしても各見出しに番号付かないのか・・・。**

.. toctree::
  :caption: 全体目次
  :name: mastertoc
  :maxdepth: 3
  :numbered:

  self
  re-st_syntax/ex-typical1.rst
  re-st_syntax/ex-role-dirs.rst
  re-st_syntax/ex-css-class-theme.rst
  re-st_syntax/ex-citation1.rst
  re-st_syntax/ex-indice.rst

toctreeをもう一つ入れてみる
=============================

.. toctree::
  :caption: 全体目次2
  :maxdepth: 3
  :numbered:

  re-st_syntax/ex-typical1.rst
  re-st_syntax/ex-role-dirs.rst

TODO
=======

.. todolist::

インデックスなど
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

