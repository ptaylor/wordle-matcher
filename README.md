# Wordle Matcher

Help solve [wordle](https://www.powerlanguage.co.uk/wordle/)

Usage:
```
wordle-matcher [PATTERN]
```

Where PATTERN is a 5 character string consisting of 
* Upper case letters for any letter in the correct spot
* Lower case caracters for any letter in the word but in the wrong spot
* Any other caracter for any letter not in the word

For example ```-tNc-``` means 
* The letter ```N``` is correct in spot 3
* The letters ```t``` and ```c``` are in the word but in the wrong spot
* The letters at spot 1 and 5 are incorrect

```
./wordle-matcher -tNc-

Found 3 matching words
```



To view the words set the environment variable SHOW_MATCHING_WORDS to ```1```

```
SHOW_MATCHING_WORDS=1 ./wordle-matcher -tNc-

Found 3 matching words

  CENTS  TONIC  TUNIC

```

Pass in multiple patterns to further reduce the choices:
```
SHOW_MATCHING_WORDS=1 ./wordle-matcher  ?tNc? ?cNt?

Found 2 matching words

  TONIC  TUNIC
```

When no pattern is passed a histogram of letter frequencies and the words with the 
best score (based on letter frequency, number of vowels and repeated words) is shown:


The word list was sourced from http://www.mieliestronk.com/wordlist.html

