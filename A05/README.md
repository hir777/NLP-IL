## A05. Information Extraction

## 1. Write a tag pattern to match noun phrases containing plural head nouns, e.g. "many/JJ researchers/NNS", "two/CD weeks/NNS", "both/DT new/JJ positions/NNS". 

Try to do this by generalizing the tag pattern that handled singular noun phrases.

(Comment: Default tagger of NLTK is PennTreebank Tagger (https://www.cs.upc.edu/~nlp/SVMTool/PennTreebank.html). 

The sample code of pos taggin for raw text as: 

```py.py
text = word_tokenize("And now for something completely different")
nltk.pos_tag(text)
```

>>> [('And', 'CC'), ('now', 'RB'), ('for', 'IN'), ('something', 'NN'),
>>> ('completely', 'RB'), ('different', 'JJ')]
