# このソフトウェアについて

GitHubアップローダにサイトのContributions自動バックアップ機能を追加した。

* [GitHub.Uploader.FunctionTest.RepoDelete.201705131257](https://github.com/ytyaru/GitHub.Uploader.FunctionTest.RepoDelete.201705131257)
* [GitHub.DB.Insert.Contributions.201705140939](https://github.com/ytyaru/GitHub.DB.Insert.Contributions.201705140939)

# 問題

Contributions自動バックアップ実行のタイミングが問題。

本来はリポジトリ生成時、コミット時に行いたかった。しかし今回は起動時に行うようにした。起動時に全ユーザのContributionsを自動バックアップする。以下の問題が生じる。

* 起動後にアップローダでコミット等したContributionsにおいてはバックアップされない。それは次回の起動時にならないと取り込まれない。
* 起動時間が遅くなる。アカウント6件で7〜8秒間の遅延発生

## 原因

* [私のスキル不足。](http://ytyaru.hatenablog.com/entry/2018/03/05/000000)後戻り作業を回避するために今回は妥協案が最善と判断した。

# 開発環境

* Linux Mint 17.3 MATE 32bit
* [Python 3.4.3](https://www.python.org/downloads/release/python-343/)
* [SQLite](https://www.sqlite.org/) 3.8.2

## WebService

* [GitHub](https://github.com/)
    * [アカウント](https://github.com/join?source=header-home)
    * [AccessToken](https://github.com/settings/tokens)
    * [Two-Factor認証](https://github.com/settings/two_factor_authentication/intro)
    * [API v3](https://developer.github.com/v3/)

# ライセンス

このソフトウェアはCC0ライセンスである。

[![CC0](http://i.creativecommons.org/p/zero/1.0/88x31.png "CC0")](http://creativecommons.org/publicdomain/zero/1.0/deed.ja)

Library|License|Copyright
-------|-------|---------
[requests](http://requests-docs-ja.readthedocs.io/en/latest/)|[Apache-2.0](https://opensource.org/licenses/Apache-2.0)|[Copyright 2012 Kenneth Reitz](http://requests-docs-ja.readthedocs.io/en/latest/user/intro/#requests)
[dataset](https://dataset.readthedocs.io/en/latest/)|[MIT](https://opensource.org/licenses/MIT)|[Copyright (c) 2013, Open Knowledge Foundation, Friedrich Lindenberg, Gregor Aisch](https://github.com/pudo/dataset/blob/master/LICENSE.txt)
[bs4](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)|[MIT](https://opensource.org/licenses/MIT)|[Copyright © 1996-2011 Leonard Richardson](https://pypi.python.org/pypi/beautifulsoup4),[参考](http://tdoc.info/beautifulsoup/)
[pytz](https://github.com/newvem/pytz)|[MIT](https://opensource.org/licenses/MIT)|[Copyright (c) 2003-2005 Stuart Bishop <stuart@stuartbishop.net>](https://github.com/newvem/pytz/blob/master/LICENSE.txt)
[furl](https://github.com/gruns/furl)|[Unlicense](http://unlicense.org/)|[gruns/furl](https://github.com/gruns/furl/blob/master/LICENSE.md)
[PyYAML](https://github.com/yaml/pyyaml)|[MIT](https://opensource.org/licenses/MIT)|[Copyright (c) 2006 Kirill Simonov](https://github.com/yaml/pyyaml/blob/master/LICENSE)

