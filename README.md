# A Benchmark Dataset for Multi-Level Complexity-Controllable Machine Translation

- This repository contains the code and resources for multi-level complexity-controllable MT.
- Multi-level complexity-controllable MT is MT controlling the complexity of the output at three or more levels.

## Repo Structure

1. ```data```: Test dataset for Japanese-to-English multi-level complexity-controllable MT.
    Our test dataset consists of ja.txt and en.txt, which have sentence alignments across languages.
   1. ja.txt
        - Each line is separated into 2 elements by ```\t```:

            ```python
            set_id"\t"Japanese_sentence
            ```

        - The 'set_id' is defined in our dataset for aligning sentences between Japanese and English.
        - 'Japanese_sentence' was manually translated from English sentences in the Newsela corpus.
   2. en.txt
        - Each line is separated into 6 elements separated by ```\t```:

            ```python
            set_id"\t"article_title"\t"grade_level"\t"readability_level"\t"paragraph_index"\t"sentence_index_within_the_paragraph
            ```

        - The 'set_id' is shared between ja.txt and en.txt. The other factors are the same in the Newsela corpus.
        - Note that en.txt does NOT include original English sentences in the Newsela corpus. You should obtain the English sentences from the Newsela corpus by using article_title, paragraph_index, and sentence_index_within_the_paragraph.

2. ```src```: Codes of 2 benchmark multi-level complexity-controllable NMT models we evaluated
   : a pipleline NMT model and a multi-task NMT model (coming soon...).

## Instructions

- To use our dataset, please first obtain access to the [Newsela corpus](https://newsela.com/data/) and then extract the English sentences identified by en.txt.
- Please use Python 3 to run our codes.
