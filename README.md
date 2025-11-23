# Collecting Data - Assignment 2
Coursework for [Collecting Data (LHU012M05)](https://ocasys.rug.nl/2025-2026/catalog/course/LHU012M05).

## Edgar Allen Poe's Poem Corpus
This repository contains an annotated corpus of poems by [Edgar Allan Poe](https://en.wikipedia.org/wiki/Edgar_Allan_Poe). It contains all poems by Edgar Allan Poe that are available through the [PoetryDB API](https://github.com/thundercomb/poetrydb). Each poem has been annotated using [SpaCy](https://github.com/explosion/spaCy). It can be used to perform linguistic research on Edgar Allan Poe's poetry, but also contains a Jupyter Notebook file that can be easily adjusted to expand the corpus to include other authors.

### Files
This repository is structured in the following way:
|File/folder|Content|
|---|---|
|[`data`](data)|This directory contains subdirectories for each poet in the corpus|
|`data/[Author]`|Directory of poems by an author, where `[Author]` is the name of the author, e.g. [`data/Edgar Allan Poe`](data/Edgar%20Allan%20Poe)|
|`data/[Author]/[#] - [Title].txt`|A single poem by an author, where `[Author]` is the name of the author, `[#]` is the ID for the poem, and `[Title]` is the title of the poem, e.g. [`data/Edgar Allan Poe/0 - The Raven.txt`](data/Edgar%20Allan%20Poe/0%20-%20The%20Raven.txt)|
|[`corpus_data.csv`](corpus_data.csv)|Annotated corpus, more [details below](#annotated-corpus)|
|[`poe.ipynb`](poe.ipynb)|Jupyter Notebook file used to preprocess and annotate the poems|
|[`README.md`](README.md)|This is the file you are reading now|
|[`requirements.txt`](requirements.txt)|Requirements file to help you install the necessary Python modules, and SpaCy's English language model, to be able to run the Jupyter Notebook file|

### Annotated corpus
Each poem in the corpus has been pre-processed and has had linguistic features added with the use of SpaCy. The results can be found in the `corpus_data.csv` file, which contains one poem per row. The corpus file contains the following information for each poem:

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
