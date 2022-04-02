## 1. Extend the grammar in grammar2 with productions that expand prepositions as intransitive, transitive and requiring a PP complement. 

Based on these productions, use the method of the preceding exercise to draw a tree for the sentence Lee ran away home.

```py.py
grammar2 = nltk.CFG.fromstring("""
  S  -> NP VP
  NP -> Det Nom | PropN
  Nom -> Adj Nom | N
  VP -> V Adj | V NP | V S | V NP PP
  PP -> P NP
  PropN -> 'Buster' | 'Chatterer' | 'Joe'
  Det -> 'the' | 'a'
  N -> 'bear' | 'squirrel' | 'tree' | 'fish' | 'log'
  Adj  -> 'angry' | 'frightened' |  'little' | 'tall'
  V ->  'chased'  | 'saw' | 'said' | 'thought' | 'was' | 'put'
  P -> 'on'
  """)
```

You should put on the grammar as:

VT -> 'ate' | 'saw' ...

VI -> 'ran' | 'looked' ...

VP -> ... | VI PP | VT PP (Preposition rules such as: https://global-square.com/blog/learn-4-prepositions/)

P -> ... | 'away'

or some other rules which indicated on exercise questions.

## 2. Write a program to compare the efficiency of a top-down chart parser compared with a recursive descent parser (4). 

Use the same grammar and input sentences for both. Compare their performance using the timeit module (see 4.7 for an example of how to do this)
