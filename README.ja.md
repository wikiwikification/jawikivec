# Yet Another Japanese-Wikipedia Entity Vectors

## 概要

日本語版Wikipediaから抽出した単語および記事へのリンクを表すエンティティの分散表現ベクトルです。
東北大学 乾・鈴木研究室の鈴木正敏さんが公開している[「日本語 Wikipedia エンティティベクトル」(日本語ページ)](http://www.cl.ecei.tohoku.ac.jp/~m-suzuki/jawiki_vector/)の仕様を元にデータを作成しています。

### もう少し詳しく

#### 単語の扱い

分かち書きされた単語についてはそのままの形で登録されています。

```
>>> from gensim.models import KeyedVectors
>>> w2v_model = KeyedVectors.load_word2vec_format('entity_vector.model.bin', binary=True, unicode_errors='ignore')
>>> print(w2v_model.most_similar(['こと']))
[('事', 0.9618349075317383), ('もの', 0.7732754349708557), ('ため', 0.7425500154495239), ... ]
```

またWikipedia記事へのリンクを指し示すエンティティについては前後に半角の角括弧をつけて `[エンティティ]` の形で登録されています。

```
>>> from gensim.models import KeyedVectors
>>> w2v_model = KeyedVectors.load_word2vec_format('entity_vector.model.bin', binary=True, unicode_errors='ignore')
>>> print(w2v_model.most_similar(['[72時間ホンネテレビ]']))
[('[AbemaPrime]', 0.6929168701171875), ('[原宿AbemaNews]', 0.6854027509689331), ...]
```

#### word2vecのオプション

以下の設定で分散表現ベクトルを生成しています。

| Option | Value |
| --- | --- |
| -size | 200 |
| -window | 5 |
| -sample | 1e-3 |
| -negative | 5 |
| -hs | 0 |
| -iter | 5 |
| -min-count | 5 |
| -cbow | 1 |

## ダウンロード方法
サイズが大きいため、Dropboxにファイルをアップロードしています。

https://www.dropbox.com/sh/601gucye55nr1gq/AABekRrz4IYtp2n0_lTrKsGma

### 辞書: mecab-ipadic
| File | jawikicorpus | Dictionary | md5 |
| --- | --- | --- | --- |
| jawikivec.ipadic.20180520.tar.xz | jawikicorpus.20180520 | mecab-ipadic-2.7.0-20070801 | 898b2562d6b851b84e4b467b92e5782a |

### 辞書: mecab-ipadic-NEologd

| File | jawikicorpus | Dictionary | md5 |
| --- | --- | --- | --- |
| jawikivec.ipadic-neologd.20180520.tar.xz | jawikicorpus.20180520 | mecab-ipadic-NEologd,b8b282537589becf7256e74c80c543aa2eba5674 | 9d67c83dfe2ceb79bb3ac446a42ede40 |

## ファイル構成
以下のtarコマンドでファイルを解凍すると5つのファイルが作られます。

```
tar xvJf jawikivec.[dictionary].yyyyMMdd.tar.xz
```

### entity_vector.model.bin

word2vecのバイナリ出力です。
Pythonの場合は[Gensimライブラリ](https://radimrehurek.com/gensim/)を利用するのが便利です。
以下のコードスニペットはモデルファイルを読み込んだ上で、Wikipediaエンティティ「ヤマハ」に分散表現の観点で近いエンティティおよび単語を取り出すというものです。

```
from gensim.models import KeyedVectors
w2v_model = KeyedVectors.load_word2vec_format('entity_vector.model.bin', binary=True, unicode_errors='ignore')

print(w2v_model.most_similar(['[ヤマハ]']))
```

### entity_vector.model.txt

word2vecのテキスト出力です。

### entities.tsv
テキスト中の語句とそれに対応するWikipediaエンティティが記載されたtsvファイルです。詳細については [Japanese-Wikipedia Wikification Corpus](https://github.com/wikiwikification/jawikicorpus) に記載しています。

### version.yml

利用した辞書、コーパスのバージョン情報を記載しています。[YAML](https://en.wikipedia.org/wiki/YAML)形式です。

### LICENSE.md

ライセンスについての文書です。
