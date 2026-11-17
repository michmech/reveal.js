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
- Reducing the (inflected) *surface form* of each word to its *lemma* (base form)
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
## Stop-word removal
1. "A quick recipe to bake a rich chocolate cake."
2. `["a", "quick", "recipe", "to", "bake", "a", "rich", "chocolate", "cake"]`
3. `["quick", "recipe", "bake", "rich", "chocolate", "cake"]`

---
## A brief excursion into full-text search

> "A quick recipe to bake a rich chocolate cake."
> "How to bake chocolate chip cookies quickly."
> "No-bake chocolate mousse."
> "Vanilla cupcake frosting tips."

Query:

> "quickly baking chocolate cakes"

---
## A brief excursion into full-text search

> "A quick recipe to bake a rich chocolate cake."
> `["recipe", "quick", "bake", "rich", "chocolate", "cake"]`
> "How to bake chocolate chip cookies quickly."
> `["bake", "chocolate", "chip", "cookie", "quick"]`
> "No-bake chocolate mousse."
> `["no", "bake", "chocolate", "mousse"]`
> "Vanilla cupcake frosting tips."
> `["vanilla", "cupcake", "frosting", "tip"]`

---
## A brief excursion into full-text search

> "A quick recipe to bake a rich chocolate cake."
> `["recipe", "quick", "bake", "rich", "chocolate", "cake"]`
> "How to bake chocolate chip cookies quickly."
> `["bake", "chocolate", "chip", "cookie", "quick"]`
> "No-bake chocolate mousse."
> `["no", "bake", "chocolate", "mousse"]`
> "Vanilla cupcake frosting tips."
> `["vanilla", "cupcake", "frosting", "tip"]`

Query:

> "quickly baking chocolate cakes"
> `["quick", "bake", "chocolate", "cake"]`

---
## Part-of-speech tagging
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
## Shallow parsing
- aka *chunking*

---
## Co-reference resolution
- Recognising what pronouns etc. *refer* to (inside the same text)
  - Paul liebt Bücher. **Er** liest oft.
  - Ich gieße Milch aus der Flasche in die Tasse, bis **sie** voll ist.  
    Ich gieße Milch aus der Flasche in die Tasse, bis **sie** leer ist.

---
## Word sense disambiguation
TBD

---
## Yes but what's it *for*?
- Linguistic research, corpus linguistics
- Language-related tasks: term extraction...
- Writing assistance tools: spellcheckers, grammar correctors
- Full-text search
- Base for higher-level NLP tasks

---
## Named-entity recognition
- Recognizing and classifying proper names
  - *Wien* → `location`
  - *Universität Wien* → `organisation`
- Can be followed by *entity linking*
- Demos:
  - https://demos.explosion.ai/displacy-ent
  - https://hanlp.hankcs.com/en/demos/ner.html
  - https://cst.dk/online/navnegenkender/uk/


---
## Sentiment analysis
- Recognising and clasifying *evaluative* language.
  - *Der Film war großartig.* → `positive`
  - *Their attritude left a lot to be desired.* → `negative`

---
## Topic modelling
- Discovering and naming the topic/theme/genre of a text

---
## Intent recognition
- "Where is my stuff? It was supposed to arrive yesterday." → `track_order`
- "I accidentally bought two of these, can I send one back?" → `initiate_return`
- "I think I left my Visa at the restaurant, freeze it." → `lock_card`

---
## Flagging problematic texts
- hate speech detection
- spam detection
- bias detection

---
## A brief excursion into bias in machine translation
TBD

---
## Tools for NLP
- NLP software libraries:
  - [spaCy](https://spacy.io/)
  - [NLTK](https://www.nltk.org/)
  - [Stanza](https://stanfordnlp.github.io/stanza/)
  - [Gensim](https://radimrehurek.com/gensim/)
- NLP pipelines

---
## Recommended reading

- 'Advanced NLP with spaCy' https://course.spacy.io/en

- 'A Gentle Introduction to Natural Language Processing' https://medium.com/data-science/a-gentle-introduction-to-natural-language-processing-e716ed3c0863

- Kai-Uwe Carstensen (2017): 'Sprachtechnologie: Ein Überblick' http://kai-uwe-carstensen.de/Publikationen/Sprachtechnologie.pdf
