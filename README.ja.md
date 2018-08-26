# Yet Another Japanese-Wikipedia Entity Vectors

## 概要

日本語版Wikipediaから抽出した単語および記事へのリンクを表すエンティティの分散表現ベクトルです。東北大学 乾・鈴木研究室の鈴木正敏さんが公開している[「日本語 Wikipedia エンティティベクトル」(日本語ページ)](http://www.cl.ecei.tohoku.ac.jp/~m-suzuki/jawiki_vector/)の仕様を基にデータを作成しています。

## 簡単な使い方

[Gensimライブラリ](https://radimrehurek.com/gensim/)を用いた例を示します。

分かち書きされた単語についてはそのままの形でword2vecの単語として登録しています。

```
>>> from gensim.models import KeyedVectors
>>> w2v_model = KeyedVectors.load_word2vec_format('entity_vector.model.bin', binary=True, unicode_errors='ignore')
>>> print(w2v_model.most_similar(['こと']))
[('事', 0.9618349075317383), ('もの', 0.7732754349708557), ('ため', 0.7425500154495239), ... ]
```

またWikipedia記事へのリンクを指し示すエンティティについては前後に半角の角括弧をつけた `[エンティティ]` の形でword2vecの単語として登録しています。
```
>>> from gensim.models import KeyedVectors
>>> w2v_model = KeyedVectors.load_word2vec_format('entity_vector.model.bin', binary=True, unicode_errors='ignore')
>>> print(w2v_model.most_similar(['[72時間ホンネテレビ]']))
[('[AbemaPrime]', 0.6929168701171875), ('[原宿AbemaNews]', 0.6854027509689331), ...]
```

## ダウンロード方法
サイズが大きいため、Dropboxにファイルをアップロードしています。

https://www.dropbox.com/sh/601gucye55nr1gq/AABekRrz4IYtp2n0_lTrKsGma

### 辞書: [mecab-ipadic](https://github.com/taku910/mecab/tree/master/mecab-ipadic)
| File | jawikicorpus | Dictionary | md5 |
| --- | --- | --- | --- |
| [jawikivec.ipadic.20180801.tar.xz](https://www.dropbox.com/s/1opft0fnid2bk6r/jawikivec.ipadic.20180801.tar.xz) | jawikicorpus.20180801 | mecab-ipadic-2.7.0-20070801 | e4b528a59d3cbf3f4d90a0dc2c8ce9cb |
| [jawikivec.ipadic.20180720.tar.xz](https://www.dropbox.com/s/5kzopgrw88ez1a2/jawikivec.ipadic.20180720.tar.xz) | jawikicorpus.20180720 | mecab-ipadic-2.7.0-20070801 | b3841ad1b46a024b403ed384609d4aad |
| [jawikivec.ipadic.20180701.tar.xz](https://www.dropbox.com/s/4qpvs1dxass1fwo/jawikivec.ipadic.20180701.tar.xz) | jawikicorpus.20180701 | mecab-ipadic-2.7.0-20070801 | 65ee15ad182adf96cfc722b55c17b9ea |
| [jawikivec.ipadic.20180620.tar.xz](https://www.dropbox.com/s/gufurtfv0dhzl85/jawikivec.ipadic.20180620.tar.xz) | jawikicorpus.20180620 | mecab-ipadic-2.7.0-20070801 | ac7afc5daaf15080b0beb3985281636b |
| [jawikivec.ipadic.20180601.tar.xz](https://www.dropbox.com/s/s8p3eob5ysyxwqk/jawikivec.ipadic.20180601.tar.xz) | jawikicorpus.20180601 | mecab-ipadic-2.7.0-20070801 | a72e03aec91be9c287678ea7f3e17527 |
| [jawikivec.ipadic.20180520.tar.xz](https://www.dropbox.com/s/98ftqtydopryaua/jawikivec.ipadic.20180520.tar.xz) | jawikicorpus.20180520 | mecab-ipadic-2.7.0-20070801 | 898b2562d6b851b84e4b467b92e5782a |

### 辞書: [mecab-ipadic-NEologd](https://github.com/neologd/mecab-ipadic-neologd)

| File | jawikicorpus | Dictionary | md5 |
| --- | --- | --- | --- |
| [jawikivec.ipadic-neologd.20180801.tar.xz](https://www.dropbox.com/s/ujhd5ji42ycpwvl/jawikivec.ipadic-neologd.20180801.tar.xz) | jawikicorpus.20180801 | mecab-ipadic-NEologd,5dc3499bc3fcd28eed960ed03cd51765c5330fe2 | 54ef946c8ca7239f22be67b52e24a5e8 |
| [jawikivec.ipadic-neologd.20180720.tar.xz](https://www.dropbox.com/s/kk1p76vtft19361/jawikivec.ipadic-neologd.20180720.tar.xz) | jawikicorpus.20180720 | mecab-ipadic-NEologd,172cfaa0aad1375d53879d273426cefe4a322e98 | 1587854da8d6efb742117d9e2933ab02 |
| [jawikivec.ipadic-neologd.20180701.tar.xz](https://www.dropbox.com/s/u1yfj0ebou02pt4/jawikivec.ipadic-neologd.20180701.tar.xz) | jawikicorpus.20180701 | mecab-ipadic-NEologd,f4d27e2d50c5980a375d326fd8f0e95c881ed1ca | a6c996ab30adbf924270fcb3f292268e |
| [jawikivec.ipadic-neologd.20180620.tar.xz](https://www.dropbox.com/s/4ch6rjkp8w1ej5n/jawikivec.ipadic-neologd.20180620.tar.xz) | jawikicorpus.20180620 | mecab-ipadic-NEologd,1c6e9eb600bba348fa772e218b8ce57d4ce70d85 | 1431b93833a8431689fa2b8eef5d45c4 |
| [jawikivec.ipadic-neologd.20180601.tar.xz](https://www.dropbox.com/s/7lcbp3wd8c9slo3/jawikivec.ipadic-neologd.20180601.tar.xz) | jawikicorpus.20180601 | mecab-ipadic-NEologd,3f6f113bc2b7b9eecbce45103a628ba715af3b33 | 2c88c8685ad9a821ffdc0ea833475e9a |
| [jawikivec.ipadic-neologd.20180520.tar.xz](https://www.dropbox.com/s/wvq0s1fyaxuo8gy/jawikivec.ipadic-neologd.20180520.tar.xz) | jawikicorpus.20180520 | mecab-ipadic-NEologd,b8b282537589becf7256e74c80c543aa2eba5674 | 9d67c83dfe2ceb79bb3ac446a42ede40 |

## ファイル構成
以下のtarコマンドでファイルを解凍すると5つのファイルが作られます。

```
tar xvJf jawikivec.[dictionary].yyyyMMdd.tar.xz
```

### entity_vector.model.bin

word2vecのバイナリ出力です。

### entity_vector.model.txt

word2vecのテキスト出力です。

### entities.tsv
テキスト中の語句とそれに対応するWikipediaエンティティが記載されたtsvファイルです。詳細については [Japanese-Wikipedia Wikification Corpus](https://github.com/wikiwikification/jawikicorpus) に記載しています。

### version.yml

利用した辞書、コーパスのバージョン情報を記載しています。[YAML](https://en.wikipedia.org/wiki/YAML)形式です。

### LICENSE.md

ライセンスについての文書です。

## 補足

### 日本語 Wikipedia エンティティベクトル

「日本語 Wikipedia エンティティベクトル」の簡単な説明を行います。詳しい内容は本家の[「日本語 Wikipedia エンティティベクトル」(日本語ページ)](http://www.cl.ecei.tohoku.ac.jp/~m-suzuki/jawiki_vector/) をご覧ください。

「日本語 Wikipedia エンティティベクトル」は、分かち書きされた単語とWikipediaのエンティティを同一の分散表現空間のベクトルとして表したものです。

以降ではWikipediaダンプデータからword2vecの入力テキストデータを作る工程を示します。
例として、[Japanese-Wikipedia Wikification Corpus](https://github.com/wikiwikification/jawikicorpus)のWikipediaのエンティティ「AbemaTV」を挙げます。記事の内容は以下のとおりです。強調部分の文字列が記事へのリンクを表します。

> **AbemaTV**
>
> AbemaTV（アベマティーヴィー）は、**PC**・**スマートフォン**向けのライブストリーミング形式である**インターネットテレビ**（放送事業者ではない）。**サイバーエージェント**と**テレビ朝日**が出資して設立した株式会社AbemaTVが運営している。
>
> ...
>
> サイバーエージェントは従前から自社サービスのブランド名として「**Ameba**」を用いているが、「AmebaTV」はカナダの企業が別サイトで使用しており、「10年以上続く「Ameba」と違う新しさがありながら、「Ameba」の延長であることも伝えたい」ためにマスコットキャラクターの「Abema」から「AbemaTV」とした。この名称は「覚えにくい・発音しにくい・間違えやすいの3点セット」「正直言って、半分くらい後悔しています」と藤田はブログに記している。『「逆さ読みにするとAmebaになる」と言う理由で採用した』と言う発言もしている。

word2vecの入力テキストには分かち書きされたものを使用する必要があります。そのため前処理として、リンク部分を `[エンティティ]` の形に書き換えた上で該当部分が必ず1トークンになるように制約を加えて分かち書きを行なっています。

しかし、先の前処理のみですと、上の記事の「Ameba」「AbemaTV」のようにWikipediaエンティティを表しているといえるものの大部分が単なるテキストであると見なされます。これは[Wikipediaのガイドライン](https://ja.wikipedia.org/wiki/Wikipedia:%E8%A8%98%E4%BA%8B%E3%81%A9%E3%81%86%E3%81%97%E3%82%92%E3%81%A4%E3%81%AA%E3%81%90)の「同一語に対してすべての出現箇所でリンクしてはいけない」という指針に起因します。この問題に対処するために、各リンクに後続するテキストのうちでリンクの表示文字列と最長一致した文字列はリンクに置換するという処理を行なっています。

以上の前処理を行うと上の記事は次のようになります。`/` は単語区切りを表します。

> [AbemaTV]
>
> [AbemaTV]  / （ / アベマティーヴィー / ） / は / 、 / [パーソナルコンピュータ] / ・ / [スマートフォン] / 向け / の / ライブストリーミング / 形式 / で / ある / [インターネットテレビ] / （ / 放送 / 事業 / 者 / で / は / ない / ） / 。 / [サイバーエージェント] / と / [テレビ朝日] / が / 出資 / し / て / 設立 / し / た / 株式会社 / [AbemaTV] / が / 運営 / し / て / いる / 。
> 
> ...
>
> [サイバーエージェント] / は / 従前 / から / 自社 / サービス / の / ブランド / 名 / として / 「 / [Ameba_(ネットサービス)] / 」 / を / 用い / て / いる / が / 、 / 「 / [Ameba_(ネットサービス)] / TV / 」 / は / カナダ / の / 企業 / が / 別 / サイト / で / 使用 / し / て / おり / 、 / 「 / 10 / 年 / 以上 / 続く / 「 / [Ameba_(ネットサービス)] / 」 / と / 違う / 新し / さ / が / あり / ながら / 、 / 「 / [Ameba_(ネットサービス)] / 」 / の / 延長 / で / ある / こと / も / 伝え / たい / 」 / ため / に / マスコットキャラクター / の / 「 / Abema / 」 / から / 「 / [AbemaTV] / 」 / と / し / た / 。 / この / 名称 / は / 「 / 覚え / にくい / ・ / 発音 / し / にくい / ・ / 間違え / やすい / の / 3 / 点 / セット / 」 / 「 / 正直 / 言っ / て / 、 / 半分 / くらい / 後悔 / し / て / い / ます / 」 / と / 藤田 / は / ブログ / に / 記し / て / いる / 。 / 『 / 「 / 逆さ / 読み / に / する / と / [Ameba_(ネットサービス)] / に / なる / 」 / と / 言う / 理由 / で / 採用 / し / た / 』 / と / 言う / 発言 / も / し / て / いる / 。

その後、word2vecのCBOWモデルを用いて200次元の分散表現ベクトルを生成しています。

### word2vecのオプション

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
