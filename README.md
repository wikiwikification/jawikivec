# Yet Another Japanese-Wikipedia Entity Vectors

## Summary

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
| [jawikivec.ipadic.20180520.tar.xz](https://www.dropbox.com/s/98ftqtydopryaua/jawikivec.ipadic.20180520.tar.xz) | jawikicorpus.20180520 | mecab-ipadic-2.7.0-20070801 | 898b2562d6b851b84e4b467b92e5782a |

### Dictionary: [mecab-ipadic-NEologd](https://github.com/neologd/mecab-ipadic-neologd)

| File | jawikicorpus | Dictionary | md5 |
| --- | --- | --- | --- |
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
