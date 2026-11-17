340088-1 VO Sprachtechnologien, Informations- und Interfacedesign  
Language technology lecture 3
# Introduction to Natural Language Processing (NLP) 

---
## Language identification

---
## Word splitting
- Segmenting a text into words
- aka *tokenisation*
  - **Warning!** In the context of LLMs, *tokenisation* means something a little different!
- Demos:
  - https://hanlp.hankcs.com/en/demos/tok.html
  - https://cst.dk/online/tokeniser/uk/index.html

---
## Word splitting: glued-on punctuation
```
In 1990, more than 60% of people in East Asia were in extreme poverty.
```

---
## Word splitting: clitics and contractions
```
don't
l'homme
je m'appelle
j'habite
```

---
## Word splitting: punctuation inside words
```
aujourd'hui
quelqu'un
```

---
## Word splitting: apostrophes
```
the boy's toys
the boys' toys
A film called 'Schindler's List'.
```

---
## Sentence splitting
- aka *segmentation* (you know this from CAT tools)
- Demo:
  - https://cst.dk/online/tokeniser/uk/index.html
```
Apple is the first U.S. public company to reach a $1 trillion market value.
DeepL has finally arrived in the U.S.
```

---
## Lemmatisation
- Reducing each (inflected) word to its *lemma* (base form) 
  -  *traf, trifft, treffe* → *treffen*
- aka *stemming*
- Demos:
  - https://cst.dk/online/lemmatiser/uk/

---
## Lemmatisation
The **leaves** are falling. → leaf  
She **leaves** tomorrow. → leave

I've been **running** all day.  
I like **running**.  
**Running** is my favourite way to relax.  

The trains **scheduled** for this afternoon will be delayed.

---
## Part-of-speech Tagging
- aka *POS tagging*
- Assigning a part of speech (grammatical category) to each word
  - verb, noun, adjective...
- May or may not also assign additional grammatical properties
  - tense, mood, person, number...
- Demos:
  - https://context-lab.com/llm-course/demos/pos-tagging/
  - https://hanlp.hankcs.com/en/demos/pos.html
  - https://cst.dk/online/pos_tagger/uk/index.html

---
## POS tagging schemes
- CLAWS (BNC)
  https://share.google/MS67n5jYEXim7ymyZ
- PAROLE
  https://www.corpas.ie/en/extras/tags/
  https://www.corpas.ie/en/info/users-guide/words-lemmas-and-tags/
- Majka
  https://nlp.fi.muni.cz/raslan/2018/paper11-Pala.pdf

---
## A brief excursion into corpus linguistics 
TBD

---
## Syntax parsing
- "Diagramming" the structure of a sentence.
- aka just *parsing*

---
## The two flavours of syntax parsing
- **Depedency parsing**
  Discovering syntactic relations between words.
    - subject – veb
    - noun – modifying adjective
- **Constituency parsing** (aka *Phrase-structure parsing*)
  Discovering the larger units ("constituents") formed by words.
    - noun phrase: "that very large open window"
    - adjectival phras: "very large"

---
## Dependency parsing
- *Universal dependencies*
  - https://universaldependencies.org/
- Demos:
  - https://context-lab.com/llm-course/demos/pos-tagging/
  - https://lindat.mff.cuni.cz/services/udpipe/
  - https://demos.explosion.ai/displacy
  - https://hanlp.hankcs.com/en/demos/dep.html

---
## Constituency parsing
~[](phrase-structure.svg)
- Demos:
  - https://hanlp.hankcs.com/en/demos/con.html
  - https://ironcreek.net/syntaxtree/  
    `[S [NP [PRP$ My] [JJ older] [NN brother]][VP [VBZ is][ADJP [RB very] [JJ talented]]]]`

---
## Bib
- Uszkoreit, Hans. (2010). Language Technology. A First Overview. German Research Center for Artificial Intelligence (2000): 1-4.
- Carstensen, Kai-Uwe (2017): Sprachtechnologie. Ein Überblick. Online verfügbar unter: http://kai-uwe-carstensen.de/Publikationen/Sprachtechnologie.pdf

