---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Use a set, not a list
---

Picking the right
[stop words](https://en.wikipedia.org/wiki/Stop_words)
is hard.

Once you have them, make using them fast.

Containment tests (`in` and `not in`) are fast on a
[`set`](https://docs.python.org/3//library/stdtypes.html#set-types-set-frozenset)
and slow on a
[`list`](https://docs.python.org/3/library/stdtypes.html#sequence-types-list-tuple-range).

No matter how you get your stop words, always put them in a
[`set`](https://docs.python.org/3//library/stdtypes.html#set-types-set-frozenset).

## Libraries that don't give you a set...

[NLTK](https://www.nltk.org/)
```python
import nltk.corpus
stopwords = set(nltk.corpus.stopwords.words('english'))
```

[stop-words](https://github.com/Alir3z4/python-stop-words)
```python
import stop_words
stopwords = set(stop_words.get_stop_words('english'))
```

## Libraries that give you a set, making your code faster and cleaner...

[spaCy](https://spacy.io/)
```python
import spacy.lang.en
type(spacy.lang.en.STOP_WORDS) is set
```

[scikit-learn](https://scikit-learn.org/)
```python
import sklearn.feature_extraction.stop_words
type(sklearn.feature_extraction.stop_words.ENGLISH_STOP_WORDS) is frozenset
```
