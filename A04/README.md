## A04. Document Classification

### 1. The Senseval 2 Corpus contains data intended to train word-sense disambiguation classifiers. 
 
It contains data for four words: hard, interest, line, and serve. Choose one of these four words, and load the corresponding data:

```python.py
from nltk.corpus import senseval
instances = senseval.instances('hard.pos')
size = int(len(instances) * 0.1)
train_set, test_set = instances[size:], instances[:size]
```
Using this dataset, build a classifier that predicts the correct sense tag for a given instance. 

See the corpus HOWTO at http://nltk.org/howto for information on using the instance objects returned by the Senseval 2 Corpus.

Hint:

```python.py
for i in train[:100]:
    p = i.position
    left = ' '.join(w for (w,t) in i.context[p-2:p])
    word = ' '.join(w for (w,t) in i.context[p:p+1])
    right = ' '.join(w for (w,t) in i.context[p+1:p+3])
    senses = ' '.join(i.senses)
    print ('%15s |%10s | %-15s -> %s' % (left, word, right, senses))

# HINT
def sense_features(instance):
    features = {}
    features["word-type"] = instance.word
    features["word-tag"] = instance.context[instance.position][1]
    features["prev-word"] = instance.context[instance.position-1][0]
    features["prev-word-tag"] = instance.context[instance.position-1][1]
    features["next-word"] = instance.context[instance.position+1][0]
    features["next-word-tag"] = instance.context[instance.position+1][1]
    return features
    
```

### 2. The synonyms strong and powerful pattern differently (try combining them with chip and sales). 

What features are relevant in this distinction? Build a classifier that predicts when each word should be used.

(Please make collocation word and its histogram, and make a bigram model classifier to use some corpus)

### 3. The dialog act classifier assigns labels to individual posts, without considering the context in which the post is found. 

However, dialog acts are highly dependent on context, and some sequences of dialog act are much more likely than others. 

For example, a ynQuestion dialog act is much more likely to be answered by a yanswer than by a greeting. Make use of this fact to build a consecutive classifier for labeling dialog acts. 

Be sure to consider what features might be useful. 

See the code for the consecutive classifier for part-of-speech tags in 1.7 to get some ideas.

（Please see 1.6 and 2.1 on Exercise 8)
