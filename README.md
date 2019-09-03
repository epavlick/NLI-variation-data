# NLI-variation-data

This directory contains the data used in the below paper.
If you have any question, please contact```ellie_pavlick@brown.edu```

```
@article{pavlick-and-kwiatkowski-2019,
    title = "Inherent Disagreements in Human Textual Inferences",
    author = "Pavick, Ellie and Kwiatkowski, Tom",
    journal = "Transactions of the Association for Computational Linguistics",
    year = "2019",
}
```

## Directory Contents
The directory contains the following files:

```
context-analysis/  
  lexical-entailments.txt
  preprocessed-context-data.jsonl
  raw/
    batch1.csv
    batch2.csv
    batch3.csv
sentence-pair-analysis/
  preprocessed-data.jsonl
  raw/
    batch1.csv
```

```sentence-pair-analysis``` contains the 50x redundant annotations for the ~500 premise/hypothesis
pairs drawn from existing NLI datasets (Sections 3 and 4 of the paper). ```context-analysis``` contains the
annotations for the ~100 pairs annotated with word, sentence, and paragraph-level contexts (Section 4 of the paper, under teh paragraph "Does context reduce disagreement?").

The ```preprocessed-*.jsonl``` files contain the data used for all of the analyses in the paper, i.e. after filtering out low-quality workers and z-normalizing scores. The fields in the json
are as follows:

* ```id``` id for the p/h pair, taken from original dataset when possible
* ```premise```
* ```hypothesis```
* ```task``` name of dataset from which the pair was drawn
* ```original-dataset-label``` label given to p/h pair in the original dataset from which it was drawn
* ```labels``` list of scores (-50 to 50) assigned by annotators on our annotation
* ```normed-labels``` list of z-normalized scores (-50 to 50) assigned by annotators on our annotation
* ```num-NA``` number of our annotators who indicated the p/h pair could not be judge for some reason

The ```raw/batch*.csv``` files contain the raw dumps from Mechanical Turk (i.e. before any type of preprocessing/filtering/normalization).

```context-analysis/lexical-entailments.txt``` contains the 300 lexical entailment pairs that were used to generate p/h pairs for the context analysis sections.