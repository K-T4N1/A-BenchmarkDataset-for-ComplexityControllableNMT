# A Benchmark Dataset for Multi-Level Complexity-Controllable Machine Translation

- This repository contains the code and resources for multi-level complexity-controllable MT.
- Multi-level complexity-controllable MT is MT controlling the complexity of the output at three or more levels.
- This dataset is based on [Newsela data](https://newsela.com/data/).
In accordance with our contract, we have applied to Newsela for permission to publish the dataset.
Please wait until the permission is granted.

## Repo Structure

1. ```data```: Test dataset for Japanese-to-English multi-level complexity-controllable MT.
    Our test dataset consists of ja.txt and en.txt, which have sentence alignments across languages.
   1. ja.txt
        - Each line is separated into 2 elements by ```\t```:

            ```python
            'set_id"\t"Japanese_sentence'
            ```

        - The 'set_id' is defined in our dataset for aligning sentences between Japanese and English.
        - 'Japanese_sentence' was manually translated from English sentences in the Newsela corpus.
   2. en.txt
        - Each line is separated into 6 elements separated by ```\t```:

            ```python
            'set_id"\t"article_title"\t"grade_level"\t"readability_level"\t"paragraph_index"\t"sentence_index_within_the_paragraph'
            ```

        - The 'set_id' is shared between ja.txt and en.txt. The other factors are the same in the Newsela corpus.
        - Note that en.txt does NOT include original English sentences in the Newsela corpus. You should obtain the English sentences from the Newsela corpus by using article_title, paragraph_index, and sentence_index_within_the_paragraph.

2. ```src```: Codes of 2 benchmark multi-level complexity-controllable NMT models we evaluated
   : a pipleline NMT model and a multi-task NMT model (coming soon...).

## Instructions

- To use our dataset, please first obtain access to the [Newsela corpus](https://newsela.com/data/) and then extract the English sentences identified by en.txt.
- Please use Python 3 to run our codes.

## Citation

```txt
@InProceedings{tani-EtAl:2022:LREC,
  author    = {Tani, Kazuki  and  Yuasa, Ryoya  and  Takikawa, Kazuki  and  Tamura, Akihiro  and  Kajiwara, Tomoyuki  and  Ninomiya, Takashi  and  Kato, Tsuneo},
  title     = {A Benchmark Dataset for Multi-Level Complexity-Controllable Machine Translation},
  booktitle      = {Proceedings of the Language Resources and Evaluation Conference},
  month          = {June},
  year           = {2022},
  address        = {Marseille, France},
  publisher      = {European Language Resources Association},
  pages     = {6744--6752},
  abstract  = {This paper presents a new benchmark test dataset for multi-level complexity-controllable machine translation (MLCC-MT), which is MT controlling the complexity of the output at more than two levels. In previous research, MLCC-MT models have been evaluated on a test dataset automatically constructed from the Newsela corpus, which is a document-level comparable corpus with document-level complexity. The existing test dataset has the following three problems: (i) A source language sentence and its target language sentence are not necessarily an exact translation pair because they are automatically detected. (ii) A target language sentence and its simplified target language sentence are not necessarily exactly parallel because they are automatically aligned. (iii) A sentence-level complexity is not necessarily appropriate because it is transferred from an article-level complexity attached to the Newsela corpus. Therefore, we create a benchmark test dataset for Japanese-to-English MLCC-MT from the Newsela corpus by introducing an automatic filtering of data with inappropriate sentence-level complexity, manual check for parallel target language sentences with different complexity levels, and manual translation. Moreover, we implement two MLCC-NMT frameworks with a Transformer architecture and report their performance on our test dataset as baselines for future research. Our test dataset and codes are released.},
  url       = {https://aclanthology.org/2022.lrec-1.726}
}
```
