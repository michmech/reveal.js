340088-1 VO Sprachtechnologien, Informations- und Interfacedesign  
Language technology lecture 3
# Introduction to Natural Language Processing (NLP) 

---
## NLP tasks

<div class="column">

- Low-level tasks
  - Language indentification
  - Tokenisation
  - Lemmatisation
  - Part-of-speech tagging
  - Parsing
  - Co-reference resolution
  - Word-sentence disambiguation

</div>
<div class="column">

- High-level tasks
  - Named entity recognition
  - Sentiment analysis
  - Topic modelling
  - Intent recognition
  - Hate speech detection
  - Spam detection
  - Bias detection

</div>

---
## Language identification
- Demos:
  - https://developers.google.com/edge/mediapipe/solutions/text/language_detector
  - https://www.cl.cam.ac.uk/~avsm2/langdetect-js/langdetect.html

---
## Tokenisation, lemmatisation, part-of-speech tagging
*Das Gericht sprach von einer historischen Entscheidung.*

1. Tokenisation
  ```
  ["Das", "Gericht", "sprach",   "von",  "einer", "historischen", "Entscheidung", "."]
  ```

2. Lemmatisation
  ```
  ["das", "Gericht", "sprechen", "von",  "ein",   "historisch",   "Entscheidung", "."]
  ```

3. Part-of-peech tagging
  ```
  ["DET", "N",       "V",        "PREP", "DET",   "ADJ",          "N",            "PUNC"]
  ```

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
## Word splitting: hyphens
```
hands-free
singer-songwriter
No-Drama Obama
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
>
> "How to bake chocolate chip cookies quickly."  
> `["bake", "chocolate", "chip", "cookie", "quick"]`  
>
> "No-bake chocolate mousse."  
> `["no", "bake", "chocolate", "mousse"]`
>
> "Vanilla cupcake frosting tips."  
> `["vanilla", "cupcake", "frosting", "tip"]`  

---
## A brief excursion into full-text search

> "A quick recipe to bake a rich chocolate cake."  
> `["recipe", "quick", "bake", "rich", "chocolate", "cake"]`  
>
> "How to bake chocolate chip cookies quickly."  
> `["bake", "chocolate", "chip", "cookie", "quick"]`  
>
> "No-bake chocolate mousse."  
> `["no", "bake", "chocolate", "mousse"]`
>
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
## CLAWS

```
["The",  "quick",  "brown",  "fox",  "jumps",  "over",  "the",  "lazy",  "dog",  "."]
```
```
["AT",   "JJ",     "JJ",     "NN1",  "VVZ",    "II",    "AT",    "JJ",   "NN1",  "."]
```

<div class="small">

- The (AT): article
- quick (JJ): general adjective
- brown (JJ): general adjective
- fox (NN1): singular common noun
- jumps (VVZ): -s form of lexical verb
- over (II): general preposition
- the (AT): article
- lazy (JJ): general adjective
- dog (NN1): singular common noun
- . (.): full-stop punctuation

</div>

---
## PAROLE

```
["The",   "quick",  "brown",  "fox",   "jumps",   "over", "the",   "lazy",   "dog",   "."]
```
```
["Td00s", "Afp000", "Afp000", "Nc0sc", "Vmip3s0", "Sp",   "Td00s", "Afp000", "Nc0sc", "Fp"]
```

<div class="small">

- The (Td00s): T (Article), d (definite), 0 (no gender), 0 (no case), s (singular).
- quick (Afp000): A (Adjective), f (qualificative), p (positive degree), 0 (no gender), 0 (no number), 0 (no case).
- brown (Afp000): A (Adjective), f (qualificative), p (positive degree), 0 (no gender), 0 (no number), 0 (no case).
- fox (Nc0sc): N (Noun), c (common), 0 (no grammatical gender), s (singular), c (common case).
- jumps (Vmip3s0): V (Verb), m (main), i (indicative), p (present), 3 (third person), s (singular), 0 (no gender).
- over (Sp): S (Adposition), p (preposition).
- the (Td00s): T (Article), d (definite), 0 (no gender), 0 (no case), s (singular).
- lazy (Afp000): A (Adjective), f (qualificative), p (positive degree), 0 (no gender), 0 (no number), 0 (no case).
- dog (Nc0sc): N (Noun), c (common), 0 (no grammatical gender), s (singular), c (common case).
- . (Fp): F (Punctuation), p (period/full stop).

</div>

---
## PAROLE

```
["Der",   "schnelle", "braune", "Fuchs", "springt", "über", "den",   "faulen", "Hund",  "."]
```
```
["Tdmsn", "Afpmsn",   "Afpmsn", "Ncmsn", "Vmip3s0", "Sp",   "Tdmsa", "Afpmsa", "Ncmsa", "Fp"]
```

<div class="small">

- Der (Tdmsn): T (Article), d (definite), m (masculine), s (singular), n (nominative).
- schnelle (Afpmsn): A (Adjective), f (qualificative), p (positive degree), m (masculine), s (singular), n (nominative).
- braune (Afpmsn): A (Adjective), f (qualificative), p (positive degree), m (masculine), s (singular), n (nominative).
- Fuchs (Ncmsn): N (Noun), c (common), m (masculine), s (singular), n (nominative).
- springt (Vmip3s0): V (Verb), m (main), i (indicative), p (present), 3 (third person), s (singular), 0 (no gender).
- über (Sp): S (Adposition), p (preposition).
- den (Tdmsa): T (Article), d (definite), m (masculine), s (singular), a (accusative).
- faulen (Afpmsa): A (Adjective), f (qualificative), p (positive degree), m (masculine), s (singular), a (accusative).
- Hund (Ncmsa): N (Noun), c (common), m (masculine), s (singular), a (accusative).
- . (Fp): F (Punctuation), p (period/full stop).

</div>

---
## PAROLE

```
["Rychlá", "hnědá",  "liška", "skáče",   "přes", "líného",  "psa",    "."]
```
```
["Afpfsn", "Afpfsn", "Ncfsn", "Vmip3s0", "Spsa", "Afpmsay", "Ncmsay", "Fp"]
```

<div class="small">

- Rychlá (Afpfsn): A (Adjective), f (qualificative), p (positive degree), f (feminine), s (singular), n (nominative).
- hnědá (Afpfsn): A (Adjective), f (qualificative), p (positive degree), f (feminine), s (singular), n (nominative).
- liška (Ncfsn): N (Noun), c (common), f (feminine), s (singular), n (nominative).
- skáče (Vmip3s0): V (Verb), m (main), i (indicative), p (present), 3 (third person), s (singular), 0 (no gender).
- přes (Spsa): S (Adposition), p (preposition), s (simple), a (governs accusative case).
- líného (Afpmsay): A (Adjective), f (qualificative), p (positive degree), m (masculine), s (singular), a (accusative), y (animate).
- psa (Ncmsay): N (Noun), c (common), m (masculine), s (singular), a (accusative), y (animate).
- . (Fp): F (Punctuation), p (period/full stop).

</div>

---
## Brno Attributive Tagset

```
["Rychlá",       "hnědá",        "liška",    "skáče",        "přes", "líného",       "psa",      "."]
```
```
["k2eAgFnSc1d1", "k2eAgFnSc1d1", "k1gFnSc1", "k5eAaImIp3nS", "k7c4", "k2eAgMnSc4d1", "k1gMnSc4", "kIx"]
```

<div class="small">

- Rychlá (k2eAgFnSc1d1): k2 (adjective), eA (affirmative/not negated), gF (feminine), nS (singular), c1 (nominative), d1 (positive degree).
- hnědá (k2eAgFnSc1d1): k2 (adjective), eA (affirmative), gF (feminine), nS (singular), c1 (nominative), d1 (positive degree).
- liška (k1gFnSc1): k1 (noun), gF (feminine), nS (singular), c1 (nominative).
- skáče (k5eAaImIp3nS): k5 (verb), eA (affirmative), aI (imperfective aspect), mI (indicative mood), p3 (3rd person), nS (singular). (Note: Some versions omit aspect aI when it is treated as a lexical property of the lemma rather than an inflectional tag).
- přes (k7c4): k7 (preposition), c4 (governs accusative case).
- líného (k2eAgMnSc4d1): k2 (adjective), eA (affirmative), gM (masculine animate), nS (singular), c4 (accusative), d1 (positive degree).
- psa (k1gMnSc4): k1 (noun), gM (masculine animate—whereas gI marks masculine inanimate), nS (singular), c4 (accusative).
- . (kIx.): kI (punctuation), x. (full stop).

</div>


---
## POS tagging schemes
- CLAWS
  https://share.google/MS67n5jYEXim7ymyZ
- PAROLE
  https://www.corpas.ie/en/extras/tags/  
  https://www.corpas.ie/en/info/users-guide/words-lemmas-and-tags/
- Brno Attributive Tagset
  https://nlp.fi.muni.cz/raslan/2018/paper11-Pala.pdf

---
## A brief excursion into corpus linguistics 
Examples:
  - [Monitor Corpus of Irish](https://www.corpas.ie/en/cmg/kwic/?q=v%C3%ADreas)
  - [Sketch Engine](https://app.sketchengine.eu/#concordance?corpname=preloaded%2Fdetenten23_rft4&tab=basic&keyword=sagenhaft&attrs=word&viewmode=kwic&attr_allpos=all&linenumbers=1&refs_up=0&shorten_refs=1&glue=1&gdexcnt=300&show_gdex_scores=0&itemsPerPage=20&structs=s%2Cg&refs=%3Ddoc.website&showresults=1&showTBL=0&tbl_template=&gdexconf=&checkboxes=1&fullcontext=0&f_tab=basic&f_showrelfrq=1&f_showperc=0&f_showreldens=0&f_showreltt=0&c_itemsPerPage=20&c_customrange=0&t_attr=&t_absfrq=0&t_trimempty=1&t_threshold=5&operations=%5B%7B%22name%22%3A%22iquery%22%2C%22arg%22%3A%22sagenhaft%22%2C%22query%22%3A%7B%22queryselector%22%3A%22iqueryrow%22%2C%22iquery%22%3A%22sagenhaft%22%7D%2C%22id%22%3A4679%7D%5D)

---
## Syntax parsing
![](phrase-structure.svg)
- "Diagramming" the structure of a sentence.
- aka just *parsing*

---
## Constituency parsing

![](phrase-structure.svg)

- aka *phrase-structure parsing*
- Discovering the larger units ("constituents") formed by words.
    - noun phrase (NP): "that very large open window"
    - adjectival phrase (AP): "very large"
- Demos:
  - https://hanlp.hankcs.com/en/demos/con.html
  - https://ironcreek.net/syntaxtree/  
    `[S [NP [PRP$ My] [JJ older] [NN brother]][VP [VBZ is][ADJP [RB very] [JJ talented]]]]`

---
## Dependency parsing

![](dependency.png) <!--{.element style="width: 100%"}-->

- Discovering syntactic relations between words.
    - verb – subject
    - noun – modifying adjective
- *Universal Dependencies*
  - https://universaldependencies.org/
- Demos:
  - https://context-lab.com/llm-course/demos/pos-tagging/
  - https://lindat.mff.cuni.cz/services/udpipe/
  - https://demos.explosion.ai/displacy
  - https://hanlp.hankcs.com/en/demos/dep.html

---
## Shallow parsing
- aka *chunking*

```
["The quick brown fox", "wants to jump", "over", "the lazy dog"]
```
```
["NP",                  "VP",            "",     "NP"]
```

---
## Co-reference resolution
- Recognising what pronouns etc. *refer* to (inside the same text)
  - Paul liebt Bücher. **Er** liest oft.
  - Ich gieße Milch aus der Flasche in die Tasse, bis **sie** voll ist.  
    Ich gieße Milch aus der Flasche in die Tasse, bis **sie** leer ist.

---
## Word sense disambiguation
- Recognising which meaning/sense a word has
  - She has no money left in the **bank**.  
    The fisherman stood on the **bank**.

---
## Yes but what is it all *for*?
- Linguistic research, corpus linguistics
- Language-related tasks: term extraction...
- Writing assistance tools: spellcheckers, grammar correctors
- Full-text search
- Higher-level NLP tasks

---
## NLP tasks

<div class="column">

- Low-level tasks <!--{.element class="grey"}-->
  - Language indentification
  - Tokenisation
  - Lemmatisation
  - Part-of-speech tagging
  - Parsing
  - Co-reference resolution
  - Word-sentence disambiguation

</div>
<div class="column">

- High-level tasks
  - Named entity recognition
  - Sentiment analysis
  - Topic modelling
  - Intent recognition
  - Hate speech detection
  - Spam detection
  - Bias detection

</div>

---
## Named entity recognition
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
- Hate speech detection
- Spam detection
- Bias detection

---
## A brief excursion into bias in machine translation
![](doctors.png) <!--{.element class="framed" style="width: 75%"}-->

- [Faislator](https://www.fairslator.com/?machine=google&srcLang=en&trgLang=de&text=The%20doctor%20and%20the%20nurse%20saved%20the%20patient%27s%20live.)

---
## NLP tasks

<div class="column">

- Low-level tasks <!--{.element class="grey"}-->
  - Language indentification
  - Tokenisation
  - Lemmatisation
  - Part-of-speech tagging
  - Parsing
  - Co-reference resolution
  - Word-sentence disambiguation

</div>
<div class="column">

- High-level tasks <!--{.element class="grey"}-->
  - Named entity recognition
  - Sentiment analysis
  - Topic modelling
  - Intent recognition
  - Hate speech detection
  - Spam detection
  - Bias detection

</div>

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

- Kai-Uwe Carstensen: 'Sprachtechnologie: Ein Überblick' http://kai-uwe-carstensen.de/Publikationen/Sprachtechnologie.pdf
