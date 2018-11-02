# [Ultimate Guide to Understand & Implement NLP](https://www.analyticsvidhya.com/blog/2017/01/ultimate-guide-to-understand-implement-natural-language-processing-codes-in-python/)

Tokenization – process of converting a text into tokens
Tokens – words or entities present in the text
Text object – a sentence or a phrase or a word or an article

#### Insatll nltk
```bash
pip install nltk
```

#### Download NLTK data
```python
import nltk
nltk.download()
```

# Text Preprocessing
Conversion of raw text into structured data, ready for analysis.  
Predominantly comprised of three steps:
* Noise Removal
* Lexicon Normalization
* Object Standardization

Text Preprocessing not discussed here includes encoding-decoding noise, grammar checker, spelling correction, etc. See [this article](https://www.analyticsvidhya.com/blog/2014/11/text-data-cleaning-steps-python/)


## Noise Removal
Noise - Any piece of text which is not relevant to the context of the data and the end-output.

#### Sample code to remove noisy words from a text
```python
noise_list = ["is", "a", "this", "..."]
def _remove_noise(input_text):
    words = input_text.split()
    noise_free_words = [word for word in words if word not in noise_list]
    noise_free_text = " ".join(noise_free_words)
    return

_remove_noise("this is a sample text")
>>> "sample text"
```
#### Sample code to remove a regex pattern
```python
import re

def _remove_regex(input_text, regex_pattern):
    urls = re.finditer(regex_pattern, input_text)
    for i in urls:
        input_text = re.sub(i.group().strip(), '', input_text)
    return input_text

regex_pattern = "#[\w]*"  

_remove_regex("remove this #hashtag from analytics vidhya", regex_pattern)
>>> "remove this  from analytics vidhya"
```

## Lexicon Normalization
Another type of textual noise is about the multiple representations exhibited by single word.  

Lemma - normalized form of words with with different contextual variations  

Stemming - rudimentary rule-based process of stripping the suffixes (“ing”, “ly”, “es”, “s” etc) from a word.  

Lemmatization - organized & step by step procedure of obtaining the root form of the word, making use of vocabulary and morphological analysis  

#### Lemmatization and stemming using NLTK
```python
from nltk.stem.wordnet import WordNetLemmatizer
lem = WordNetLemmatizer()

from nltk.stem.porter import PorterStemmer
stem = PorterStemmer()

word = "multiplying"

lem.lemmatize(word, "v")
>> "multiply"

stem.stem(word)
>> "multipli"
```

## Object Standardization
Words or phrases which are not present in any standard lexical dictionaries also create noise. This is fixed with regular expressions and manually prepared data dictionaries.
``` python
lookup_dict = {'rt':'Retweet', 'dm':'direct message', "awsm" : "awesome", "luv" :"love", "..."}
def _lookup_words(input_text):
    words = input_text.split()
    new_words = []
    for word in words:
        if word.lower() in lookup_dict:
            word = lookup_dict[word.lower()]
        new_words.append(word) new_text = " ".join(new_words)
        return new_text

_lookup_words("RT this is a retweeted tweet by Shivam Bansal")
>> "Retweet this is a retweeted tweet by Shivam Bansal"
```
# Text to Features (Feature Engineering on text data)

## Syntactical Parsing
### Dependency Grammar
### Part of Speech Tagging

## Entity Parsing
### Phrase Detection
### Named Entity Recognition
### Topic Modelling
### N-Grams

## Statistical features
### TF – IDF
### Frequency / Density Features
### Readability Features

## Word Embeddings


# Important tasks of NLP

## Text Classification

## Text Matching
### Levenshtein Distance
### Phonetic Matching
### Flexible String Matching

## Coreference Resolution

## Other Problems


# Important NLP libraries
