## A02. Raw Data Corpus and Regular Expression

1. Describe the class of strings matched by the following regular expressions.

[a-zA-Z]+
[A-Z][a-z]*
p[aeiou]{,2}t
\d+(\.\d+)?
Test your answers using nltk.re_show().

2. Are you able to write a regular expression to tokenize text in such a way that the word don't is tokenized into do and n't? Explain why this regular expression won't work: «n't|\w+».

3. Try to write code to convert text into hAck3r, using regular expressions and substitution, where a → A, e → 3, i → 1, o→ 0, l → |, s → $ (initial) or 5 (internal) , . → 5w33t!, ate → 8. Normalize the text to lowercase before converting it. 

Add more substitutions of your own. Now try to map s to two different values: $ for word-initial s, and 5 for word-internal s.

: Answer : 

Hacker ate sugar cookie last night. → hAck3r 8 $ugAr c00k13 |A5t n1ght5w33t!

[re.sub()の説明](https://note.nkmk.me/python-str-replace-translate-re-sub/)
