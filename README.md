# fast-text-sandbox

## Venv

```
virtualenv -p python3 venv
source venv/bin/activate
```

## Wiki Data

```
wget https://dumps.wikimedia.org/jawiki/latest/jawiki-latest-pages-articles.xml.bz2
```

##  Wikiextractor

```
git clone git@github.com:attardi/wikiextractor.git
cd wikiextractor
python wikiextractor/setup.py install
```

## Corpus

```
python wikiextractor/WikiExtractor.py -b 500M -o corpus source/jawiki-latest-pages-articles.xml.bz2
```

## MeCab

```
brew install mecab
brew install mecab-ipadic
brew install swig
pip install --upgrade pip
pip install mecab-python3
```