## A05. Information Extraction

問題文

## 1. Write a tag pattern to match noun phrases containing plural head nouns, e.g. "many/JJ researchers/NNS", "two/CD weeks/NNS", "both/DT new/JJ positions/NNS". 

Try to do this by generalizing the tag pattern that handled singular noun phrases.

(Comment: Default tagger of NLTK is PennTreebank Tagger (https://www.cs.upc.edu/~nlp/SVMTool/PennTreebank.html). 

The sample code of pos taggin for raw text as: 

```py.py
text = word_tokenize("And now for something completely different")
nltk.pos_tag(text)
```

> [('And', 'CC'), ('now', 'RB'), ('for', 'IN'), ('something', 'NN'), ('completely', 'RB'), ('different', 'JJ')]

and if you want to information about plural noun, then NNS is this case.

if you want to use some other corpus, you need to translate tag sets but it is better to use Universal tag set because this is enough to small.) 

## 2. Write a tag pattern to cover noun phrases that contain gerunds, e.g. "the/DT receiving/VBG end/NN", "assistant/NN managing/VBG editor/NN". 

Add these patterns to the grammar, one per line. Test your work using some tagged sentences of your own devising.

## 3. Carry out the following evaluation tasks for any of the chunkers you have developed earlier. 

(Note that most chunking corpora contain some internal inconsistencies, such that any reasonable rule-based approach will produce errors.)

a. Evaluate your chunker on 100 sentences from a chunked corpus, and report the precision, recall and F-measure.

b. Use the chunkscore.missed() and chunkscore.incorrect() methods to identify the errors made by your chunker. Discuss.

c. Compare the performance of your chunker to the baseline chunker discussed in the evaluation section of this chapter.

（There is no description about "baseline_chunker" (a special baseline_chunker described on nltk document version 0.9.5, but this is deleted, so, we define baseline chunker as follows)

```py.py
grammar = r"NP: {<[CDJNP].*>+}"
cp = nltk.RegexpParser(grammar)
print(cp.evaluate(test_sents))
```

> ChunkParse score:

> IOB Accuracy:  87.7%

> Precision:     70.6%

> Recall:        67.8%

> F-Measure:     69.2%
