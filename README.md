# French models for spaCy

This repository contains [releases](https://github.com/pagesjaunes/spacy-french-models/releases) of models for the
[spaCy](https://github.com/explosion/spaCy) NLP library. For more info on how to
download, install and use the models, see the
[models documentation](https://spacy.io/docs/usage/models).

## Releases
| Date | Model | Version | Size | Description | |
| --- | --- | --- | --- | -- | --- |
| `2017-04-04` | `fr_model` | 0.0.1 | 134 MB | POS Tagging, Dependency Parsing | [![][dl]][fr_model-0.0.1]

[fr_model-0.0.1]: https://github.com/pagesjaunes/spacy-french-models/releases/download/v0.0.1-alpha/fr_model-0.0.1.tar.gz
[dl]: http://i.imgur.com/gQvPgr0.png

## Installation
```bash
pip install https://github.com/pagesjaunes/spacy-french-models/releases/download/v0.0.1-alpha/fr_model-0.0.1.tar.gz

# set up shortcut link to load installed package as "fr_default"
python -m spacy link fr_model fr_default --force
```

## Loading and using models
To load a model, use `spacy.load()` with the model's shortcut link:

```python
import spacy
nlp = spacy.load('fr_default')

doc = nlp("Je voudrais réserver un hôtel à Rennes.")
for w in doc:
    print("%s\t%s\t%s" % (w, w.tag_, w.dep_))
```

```
Je          PRON    nsubj
voudrais    AUX     ROOT
réserver    VERB    ROOT
un          DET     det
hôtel       NOUN    obj
à           ADP     case
Rennes      PROPN   nmod
.           PUNCT   punct
```


## Evaluation
### POS Tagging
```
             precision    recall  f1-score   support

        ADJ       0.88      0.92      0.90       384
        ADP       0.99      0.99      0.99      1025
        ADV       0.95      0.80      0.87       400
        AUX       0.94      0.56      0.70       275
      CCONJ       0.00      0.00      0.00       174
       CONJ       0.00      0.00      0.00         0
        DET       0.99      0.98      0.99      1026
       INTJ       0.57      0.67      0.62         6
       NOUN       0.94      0.96      0.95      1236
        NUM       0.89      0.95      0.92       138
       PART       0.10      1.00      0.18         7
       PRON       0.98      0.97      0.97       441
      PROPN       0.92      0.82      0.87       335
      PUNCT       1.00      1.00      1.00       840
      SCONJ       0.85      0.96      0.90        98
        SYM       0.91      0.91      0.91        23
       VERB       0.79      0.92      0.85       606
          X       0.17      0.17      0.17         6

avg / total       0.92      0.91      0.91      7020
```



**📖 For more info and examples, check out the [models documentation](https://spacy.io/docs/usage/models).**


