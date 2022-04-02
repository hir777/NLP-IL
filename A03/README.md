## A03. Word Sense

### 1. Use sorted() and set() to get a sorted list of tags used in the Brown corpus, removing duplicates.

### 2. Recall the example of a bigram tagger which encountered a word it hadn't seen during training, and tagged the rest of the sentence as None. 

It is possible for a bigram tagger to fail part way through a sentence even if it contains no unseen words (even if the sentence was used during training).

In what circumstance can this happen? Can you write a program to find some examples of this?

### 3. Preprocess the Brown News data by replacing low frequency words with UNK, but leaving the tags untouched. 

Now train and evaluate a bigram tagger on this data. How much does this help? 

What is the contribution of the unigram tagger and default tagger now?
