# Yet Another Japanese-Wikipedia Entity Vectors

## Overview

Distribution vector representations of words and Wikipedia entities appeared in Japanese Wikipedia. The data is created based on the specification of "[Japanese-Wikipedia Entity Vectors (in Japanese)](http://www.cl.ecei.tohoku.ac.jp/~m-suzuki/jawiki_vector/)" released by Masatoshi Suzuki of Inui-Suzuki Laboratory in Tohoku University.

## Basic Usage

Here are examples with [Gensim library](https://radimrehurek.com/gensim/).
Segmented words are registered as word2vec words.

```
>>> from gensim.models import KeyedVectors
>>> w2v_model = KeyedVectors.load_word2vec_format('entity_vector.model.bin', binary=True, unicode_errors='ignore')
>>> print(w2v_model.most_similar(['こと']))
[('事', 0.9618349075317383), ('もの', 0.7732754349708557), ('ため', 0.7425500154495239), ... ]
```

Entities that link to Wikipedia articles are registered as word2vec words with square brackets on either side in the format `[entity]`.

```
>>> from gensim.models import KeyedVectors
>>> w2v_model = KeyedVectors.load_word2vec_format('entity_vector.model.bin', binary=True, unicode_errors='ignore')
>>> print(w2v_model.most_similar(['[72時間ホンネテレビ]']))
[('[AbemaPrime]', 0.6929168701171875), ('[原宿AbemaNews]', 0.6854027509689331), ...]
```

## Download
Due to the large file size, files are uploaded to Dropbox.

https://www.dropbox.com/sh/601gucye55nr1gq/AABekRrz4IYtp2n0_lTrKsGma

### Dictionary: [mecab-ipadic](https://github.com/taku910/mecab/tree/master/mecab-ipadic)
| File | jawikicorpus | Dictionary | md5 |
| --- | --- | --- | --- |
| [jawikivec.ipadic.20181020.tar.xz](https://www.dropbox.com/s/57ksqqjpfp9tt01/jawikivec.ipadic.20181020.tar.xz) | jawikicorpus.20181020 | mecab-ipadic-2.7.0-20070801 | 2524636714d1418cba5ff0cbf1947c50 |
| [jawikivec.ipadic.20181001.tar.xz](https://www.dropbox.com/s/6j68x5ou2g76f0x/jawikivec.ipadic.20181001.tar.xz) | jawikicorpus.20181001 | mecab-ipadic-2.7.0-20070801 | 693a9d75b936c9a2cb25147575f51eea |
| [jawikivec.ipadic.20180920.tar.xz](https://www.dropbox.com/s/y5dh9ytdqana1rc/jawikivec.ipadic.20180920.tar.xz) | jawikicorpus.20180920 | mecab-ipadic-2.7.0-20070801 | ae63c1cb0c64382773ddfc823c0fce10 |
| [jawikivec.ipadic.20180901.tar.xz](https://www.dropbox.com/s/umk05okgafzuj38/jawikivec.ipadic.20180901.tar.xz) | jawikicorpus.20180901 | mecab-ipadic-2.7.0-20070801 | 0a55a6a33e8e79151f7347378f70e5b5 |
| [jawikivec.ipadic.20180820.tar.xz](https://www.dropbox.com/s/axmm2yq3hftjf1h/jawikivec.ipadic.20180820.tar.xz) | jawikicorpus.20180820 | mecab-ipadic-2.7.0-20070801 | cc524c551cccf8fae29b086add0252b5 |
| [jawikivec.ipadic.20180720.tar.xz](https://www.dropbox.com/s/5kzopgrw88ez1a2/jawikivec.ipadic.20180720.tar.xz) | jawikicorpus.20180720 | mecab-ipadic-2.7.0-20070801 | b3841ad1b46a024b403ed384609d4aad |
| [jawikivec.ipadic.20180701.tar.xz](https://www.dropbox.com/s/4qpvs1dxass1fwo/jawikivec.ipadic.20180701.tar.xz) | jawikicorpus.20180701 | mecab-ipadic-2.7.0-20070801 | 65ee15ad182adf96cfc722b55c17b9ea |
| [jawikivec.ipadic.20180620.tar.xz](https://www.dropbox.com/s/gufurtfv0dhzl85/jawikivec.ipadic.20180620.tar.xz) | jawikicorpus.20180620 | mecab-ipadic-2.7.0-20070801 | ac7afc5daaf15080b0beb3985281636b |
| [jawikivec.ipadic.20180601.tar.xz](https://www.dropbox.com/s/s8p3eob5ysyxwqk/jawikivec.ipadic.20180601.tar.xz) | jawikicorpus.20180601 | mecab-ipadic-2.7.0-20070801 | a72e03aec91be9c287678ea7f3e17527 |
| [jawikivec.ipadic.20180520.tar.xz](https://www.dropbox.com/s/98ftqtydopryaua/jawikivec.ipadic.20180520.tar.xz) | jawikicorpus.20180520 | mecab-ipadic-2.7.0-20070801 | 898b2562d6b851b84e4b467b92e5782a |

### Dictionary: [mecab-ipadic-NEologd](https://github.com/neologd/mecab-ipadic-neologd)

| File | jawikicorpus | Dictionary | md5 |
| --- | --- | --- | --- |
| [jawikivec.ipadic-neologd.20181020.tar.xz](https://www.dropbox.com/s/fvcd2vrt21cpuh2/jawikivec.ipadic-neologd.20181020.tar.xz) | jawikicorpus.20181020 | mecab-ipadic-NEologd,b3f3ac6fbdb5130894243c40726a9c4878075649 | 4b4713493a7ffd8e1104bc393e0b3344 |
| [jawikivec.ipadic-neologd.20181001.tar.xz](https://www.dropbox.com/s/4rp6w1fawwtid9h/jawikivec.ipadic-neologd.20181001.tar.xz) | jawikicorpus.20181001 | mecab-ipadic-NEologd,1e9da37787c202f157e59d4c9b19cd4636d8a60d | 03c0536e5e68310f8ce40559728a7c06 |
| [jawikivec.ipadic-neologd.20180920.tar.xz](https://www.dropbox.com/s/lxc9jd3t88e6xhb/jawikivec.ipadic-neologd.20180920.tar.xz) | jawikicorpus.20180920 | mecab-ipadic-NEologd,3326dc5bb7467b51e7875f0f332cef6d89049617 | 2d8e0a4e38dc31f073eb97a32d14e684 |
| [jawikivec.ipadic-neologd.20180901.tar.xz](https://www.dropbox.com/s/qgjub2yo570n8fr/jawikivec.ipadic-neologd.20180901.tar.xz) | jawikicorpus.20180901 | mecab-ipadic-NEologd,3326dc5bb7467b51e7875f0f332cef6d89049617 | 084942f0153444c5e56ff76db81706dd |
| [jawikivec.ipadic-neologd.20180820.tar.xz](https://www.dropbox.com/s/e9w6yatsqi77vnk/jawikivec.ipadic-neologd.20180820.tar.xz) | jawikicorpus.20180820 | mecab-ipadic-NEologd,5dc3499bc3fcd28eed960ed03cd51765c5330fe2 | 8d361239c9ec57df78b1f2d527029f44 |
| [jawikivec.ipadic-neologd.20180720.tar.xz](https://www.dropbox.com/s/kk1p76vtft19361/jawikivec.ipadic-neologd.20180720.tar.xz) | jawikicorpus.20180720 | mecab-ipadic-NEologd,172cfaa0aad1375d53879d273426cefe4a322e98 | 1587854da8d6efb742117d9e2933ab02 |
| [jawikivec.ipadic-neologd.20180701.tar.xz](https://www.dropbox.com/s/u1yfj0ebou02pt4/jawikivec.ipadic-neologd.20180701.tar.xz) | jawikicorpus.20180701 | mecab-ipadic-NEologd,f4d27e2d50c5980a375d326fd8f0e95c881ed1ca | a6c996ab30adbf924270fcb3f292268e |
| [jawikivec.ipadic-neologd.20180620.tar.xz](https://www.dropbox.com/s/4ch6rjkp8w1ej5n/jawikivec.ipadic-neologd.20180620.tar.xz) | jawikicorpus.20180620 | mecab-ipadic-NEologd,1c6e9eb600bba348fa772e218b8ce57d4ce70d85 | 1431b93833a8431689fa2b8eef5d45c4 |
| [jawikivec.ipadic-neologd.20180601.tar.xz](https://www.dropbox.com/s/7lcbp3wd8c9slo3/jawikivec.ipadic-neologd.20180601.tar.xz) | jawikicorpus.20180601 | mecab-ipadic-NEologd,3f6f113bc2b7b9eecbce45103a628ba715af3b33 | 2c88c8685ad9a821ffdc0ea833475e9a |
| [jawikivec.ipadic-neologd.20180520.tar.xz](https://www.dropbox.com/s/wvq0s1fyaxuo8gy/jawikivec.ipadic-neologd.20180520.tar.xz) | jawikicorpus.20180520 | mecab-ipadic-NEologd,b8b282537589becf7256e74c80c543aa2eba5674 | 9d67c83dfe2ceb79bb3ac446a42ede40 |

## Files

By decompressing an archive with the following tar command, 5 files are created.

```
tar xvJf jawikivec.[dictionary].yyyyMMdd.tar.xz
```

### entity_vector.model.bin

An output file saved in binary word2vec format.

### entity_vector.model.txt

An output file saved in text word2vec format.

### entities.tsv
A tsv file containing terms appeared in a plain text and corresponding Wikipedia entities. More details are described in [Japanese-Wikipedia Wikification Corpus](https://github.com/wikiwikification/jawikicorpus).

### version.yml

A [YAML](https://en.wikipedia.org/wiki/YAML)-formatted file to store version information for referred dictionary and corpus.

### LICENSE.md

Document regarding licensing.

## Supplementary

### Word2vec options

Distribution vector representations are created in the following settings.

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
