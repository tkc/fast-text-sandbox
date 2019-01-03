# fast-text-sandbox

## Venv

```
virtualenv -p python3 venv
source venv/bin/activate
```

## Numpay

```
pip install numpy
```

## Cmake

```
brew update
brew install cmake
```

## FastText

```
git clone https://github.com/facebookresearch/fastText.git
cd fastText
mkdir build && cd build && cmake ..
make && make install
```

Building fastText using cmake . 
https://github.com/facebookresearch/fastText#building-fasttext-using-cmake


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

```
mecab ./corpus/AA/wiki_00 -O wakati -o ./corpus/out/wiki_00.txt
mecab ./corpus/AA/wiki_01 -O wakati -o ./corpus/out/wiki_01.txt
mecab ./corpus/AA/wiki_02 -O wakati -o ./corpus/out/wiki_02.txt
mecab ./corpus/AA/wiki_03 -O wakati -o ./corpus/out/wiki_03.txt
mecab ./corpus/AA/wiki_04 -O wakati -o ./corpus/out/wiki_04.txt
mecab ./corpus/AA/wiki_05 -O wakati -o ./corpus/out/wiki_05.txt
```

```
cat wiki_00.txt >out.txt
cat wiki_01.txt >>out.txt
cat wiki_02.txt >>out.txt
cat wiki_03.txt >>out.txt
cat wiki_04.txt >>out.txt
cat wiki_05.txt >>out.txt
```

## Make model

```
fasttext skipgram -input ./corpus/out/out.txt -output model -dim 300
```

## Predict 

```
python eval.py {word}
```
