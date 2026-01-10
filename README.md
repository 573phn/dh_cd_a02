# Collecting Data - Assignment 2
Coursework for [Collecting Data (LHU012M05)](https://ocasys.rug.nl/2025-2026/catalog/course/LHU012M05).

## Poem Corpus
This repository contains an annotated corpus of poems by [Henry Wadsworth Longfellow](https://wikipedia.org/wiki/Henry_Wadsworth_Longfellow) and [Edgar Allan Poe](https://wikipedia.org/wiki/Edgar_Allan_Poe). It contains all poems by these authors that are available through the [PoetryDB](https://github.com/thundercomb/poetrydb) API. Each poem has been annotated using [spaCy](https://github.com/explosion/spaCy). It can be used to perform linguistic research on these author's poetry, but also contains a Jupyter Notebook file that can be easily adjusted to expand the corpus to include other authors.

### Files
This repository is structured in the following way:
|File/folder|Content|
|---|---|
|[`data`](data)|This directory contains subdirectories for each poet in the corpus|
|`data/[Author]`|Directory of poems by an author, where `[Author]` is the name of the author, e.g. [`data/Edgar Allan Poe`](data/Edgar%20Allan%20Poe)|
|`data/[Author]/[#T]_[#L] [Title].txt`|A single poem by an author, where `[Author]` is the name of the author, `[#T]` is the token count of the poem, `[#L]` is the line count of the poem, and `[Title]` is the title of the poem, e.g. [`data/Edgar Allan Poe/1489_113 The Raven.txt`](data/Edgar%20Allan%20Poe/1489_113%20The%20Raven.txt)|
|[`corpus_data.csv`](corpus_data.csv)|Annotated corpus, more [details below](#annotated-corpus)|
|[`poem.ipynb`](poe.ipynb)|Jupyter Notebook file used to preprocess and annotate the poems|
|[`README.md`](README.md)|This is the file you are reading now|
|[`requirements.txt`](requirements.txt)|Requirements file to help you install the necessary Python modules, and spaCy's English language model, to be able to run the Jupyter Notebook file|

### Annotated corpus
Each poem in the corpus has been pre-processed and has had linguistic features added with the use of spaCy. The results can be found in the `corpus_data.csv` file, which contains one poem per row. The corpus file contains the following information for each poem:

|Column|Description|
|---|---|
||Unnamed column which contains the poem's ID|
|filename|The name of the file in which the poem is stored|
|title|The title of the poem|
|document|The content of the document, which is identical to how the poem is stored in the `data` directory|
|text|A pre-processed version of the text, in which underscores (`_`) have been removed and spaces have been added around double dashes (`--`) to aid with the tokenization|
|tokens|A tokenized version of the text|
|lemmas|A lemmatized version of the text|
|parts-of-speech|POS-tags of the text|
|author|The name of the poem's author|
|linecount|The number of lines in the poem, as retrieved from the PoetryDB API|
|tokencount|The number of tokens in the poem, after tokenization with spaCy|

#### Known issues
The Jupyter Notebook file requires Python 3.13 or older, as Pydantic V1 (which seems to be used by SpaCy) is incompatible with Python 3.14. 
