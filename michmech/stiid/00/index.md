# 340088-1 VO Sprachtechnologien, Informations- und Interfacedesign

<div class="column centered">

  ![Photo](michmech.jpg) <!-- .element: class="portrait" -->
  
  Michal Měchura  
  Lecturer  
  michal.mechura@univie.ac.at

</div>
<div class="column centered">

  ![Photo](helene.jpg) <!-- .element: class="portrait" -->

  Helene Seidl  
  Tutor  
  helene.seidl@univie.ac.at

</div>

---

## Your lecturer’s journey through language technology
1. Software localisation @ Microsoft Ireland
2. Language resource managment @ Dublin City University
    - Terminologue: www.terminologue.org
    - Lexonomy: www.lexonomy.eu
    - The book *An Ríomhaire Ilteangach* [*The Multilingual Computer*] (2016)
3. Researcher & lecturer @ University of Vienna
    - Fairslator: www.fairslator.com
4. Co-founder & CTO @ Intlingua

---

## Why language professionals need to understand technology
- Most language work happens on computers
- The language industry has become *digitised*

---

## Why technologists need to understand languages
- Computers are tools for *communication*, not for computation
- The cyberspace is multilingual

---

Quick poll
## Are you more a *language* person or more a *technology* person?

---

## Prerequisites for this course
- Basic computer skills
  - Keyboard and mouse
  - Files and folders
  - Word processing
  - E-mails
  - Browsing the web

---

Quick poll
## Are smartphones *computers*?

---

## What this course will *not* teach you
- Programming, coding
- Software development, software engineering
- “Hacking” (whatever that is)   

---

## Clarification: what do we mean by *language*?

### Human languages
- Spoken/written languages: English, German, Mandarin...
  - Invented languages: Esperanto...
- Sign languages: Austrian Sign Language...    

### Formal languages  
- Programming languages: Python, C++, JavaScript...
- Data languages: XML, JSON...
- Formal notations in mathematics, chemistry...

### Semiotic systems
- The “language” of traffic signs, “body language”...

---

Quick poll
## How many languages are there in the world?

---

## What is language technology?
*“[...] studies methods of how computer programs or electronic devices can analyze, produce, modify or respond to human texts and speech.”* – Wikipedia

---

## What is language technology (1/7)
- Machine translation (MT)
- Computer-aided translation (CAT)
- Translation management systems (TMS)
- Terminology management
- Terminology extraction

---

## What is language technology (2/7)
- Text-to-speech, speech synthesis
  - Screen readers, assistive technology
- Speech-to-text, speech recognition
  - Dictation
  - Automatic subtitling
- Optical character recognition (OCR)
- Speech-to-speech translation
- Language identification

---

## Sidenote: the *modalities* of language
- Spoken
- Written
- Signed

---

## What is language technology (3/7)
- Predictive texting
- Spellchecking
- Autocorrect
- Grammar checking
- AI writing assistants

---

Quick poll
## How do you input text on your mobile phone?

---

Quick poll
## Who uses AI writing assistants?

---

## What is language technology (4/7)
- Character encoding
- Keyboard layouts
- Text encoding
- Language-specific text handling
  - Alphabetical sorting
  - Capitalisation
  - Formatting numbers, dates, times, currencies

---

Quick poll
## Who has heard of *Unicode*?

---

Quick poll
## Who has heard of *ASCII*?

---

Quick poll
## Who has heard of *XML* and/or *HTML*?

---
## What is language technology (5/7)
- Software localisation 
- Software internationalisation
- Multilingual websites

---

Quick poll
## What language is your smartphone in?

---

## What is language technology (6/7)
- Natural language processing (NLP)
  - Word spliting, tokenisation
  - Sentence splitting
  - Lemmatisation/stemming
  - Part-of-speech tagging
  - Syntax parsing
  - Named-entity recognition
  - Sentiment detection
- Full-text search, information retrieval 
- Computational linguistics
- Corpus liguistics

---

## What is language technology (7/7)
- Language modelling
- Word vectors/embeddings
- Neural networks
- Large language models (LLMs)
- AI chatbots

---

Quick poll
## “Large language models (LLMs) are basically machines for predicting the next word.”
True or false?

---

## The lectures

### Language technology
- (LT1) How computers represent characters: ASCII, Unicode and everything in between
- (LT2) Working with text: spellcheckers, grammar correctors, AI writing assistants
- (LT3) Intro to Natural Language Processing (NLP): tagging, parsing and their applications
- (LT4) Understanding the technology behind NLP: language models, vectors, word embeddings
- (LT5) Large Language Models (LLMs): understanding how they do what they do

### Information management
- (IM1) Formats for representing text: Markdown, XML and their uses
- (IM2) Managing data: JSON, YAML, relational databases, Semantic Web.
- (IM3) Understanding Internet technology: how the Internet works under the hood

### User interface design
- (UI1) Understanding user interfaces: what designing a good user experience is about
- (UI2) Software localisation and globalisation: the challenge of translating on-screen text
- (UI3) Managing multilingual websites: pitfalls to avoid on the multilingual web

---

## Probable ordering of the lectures

### Foundational technologies
- (LT1) How computers represent characters: ASCII, Unicode and everything in between
- (LT2) Working with text: spellcheckers, grammar correctors, AI writing assistants
- (IM1) Formats for representing text: Markdown, XML and their uses
- (IM2) Managing data: JSON, YAML, relational databases, Semantic Web.

### A dive into NLP and AI
- (LT3) Intro to Natural Language Processing (NLP): tagging, parsing and their applications
- (LT4) Understanding the technology behind NLP: language models, vectors, word embeddings
- (LT5) Large Language Models (LLMs): understanding how they do what they do

### Multilingual software
- (UI1) Understanding user interfaces: what designing a good user experience is about
- (UI2) Software localisation and globalisation: the challenge of translating on-screen text
- (IM3) Understanding Internet technology: how the Internet works under the hood
- (UI3) Managing multilingual websites: pitfalls to avoid on the multilingual web

---

## (LT1) How computers represent characters: ASCII, Unicode and everything in between
- How computers represent the characters of various languages, alphabets and writing systems.
- The diversity of European character sets.
- The evolution of character encoding from ASCII to Unicode.
- Concepts such as ‘codepage’ and ‘extended character’.
- Understanding (some of) the complexity of Unicode: combining characters, Unicode normalisation, UTF-8.
- Dealing with wrongly encoded text.
- Changing the character encoding of text in various software packages.
- Inputting text in various languages using different keyboard layouts, alternative input methods and character pickers.

---

## (LT2) Working with text: spellcheckers, grammar correctors, AI writing assistants
- Going above the level of character encoding: language-specific issues to be aware of when handling text in various languages.
- Punctuation, quotation marks, number and date formatting, capitalisation, names of people and things, alphabetical sorting, end-of-line word hyphenation.
- Writing tools and writing assistants.
- How autocorrect, spellcheckers and grammar correctors work and what their limitations are.
- Finding and installing spellcheckers and grammar correctors for your language.
- AI-based writing assistants.

---

## (LT3) Intro to Natural Language Processing (NLP): tagging, parsing and their applications
- Tokenisation, sentence splitting and chunking.
- Lemmatisation and stemming.
- Part-of-speech tagging, common tagging schemes.
- A brief excursion into corpus linguistics.
- Syntax parsing, dependency syntax versus phrase-structure syntax, Universal Dependencies.
- Named-entity recognition. Co-reference resolution.
- Sentiment analysis. Intent recognition. Information extraction (events, relationships...).
- Bringing all this together into an ‘NLP pipeline’. Tools tech people usually use to build NLP pipelines, e.g. spaCy.
- NLP for fulltext search and infomation retrieval.
- Speech 	technologies: text-to-speech and speech-to-text.

---

## (LT4) Understanding the technology behind NLP: language models, vectors and word embeddings
- Rule-based versus statistical approaches.
- What’s a language model?
- Modelling human language as a Markov chain, “predicting the next word”, applications of this approach e.g. predictive typing on mobile phones.
- A brief introduction to neural networks and their applications.
- How tech people train and evaluate language models.
- Vectors, word embeddings and sentence embeddings. Applications of word and sentence embeddings for semantic search.
- Strengths and weaknesess of rule-based versus statistical language models: accuracy versus coverage, reliability versus need for human verification, potential for bias.

---

## (LT5) Large Language Models (LLMs): understanding how they do what they do
- What even is ‘AI’?
- Deterministic versus stochastic technology.
- The evolution of neural network architectures up to and including transformers.
- What are LLMs useful for?
- Prompt engineering.
- Language-specific properties of LLMs, evaluating and benchmarking the language skills of LLMs.
- LLM output in freeform text versus structured output.
- The problem of hallucinations.
- Fine-tuning, few-shot learning.
- LLMs with reasoning capabilities.
- LLMs that make use of external tools, MCP (Model Context Protocol).
- LLMs that ‘do stuff’, AI agents.
- The economics of LLMs: ‘tokens’, ‘compute’, energy consumption.
- Open-source and open-weight LLMs. Running an LLM locally versus in the cloud.
- The ethics of LLMs: copyright issues, environmental impact, harmful output.

---

## (IM1) Formats for representing text: Markdown, XML and their uses
- Starting from plain text. What even is plain text and how does it differ from e.g. a Microsoft Word document?
- Markdown as a lightweight text-structuring format.
- A step-by-step introduction to XML. XML elements and XML attributes.
- XML schemas, valid versus invalid XML.
- Popular XML schemas for representing text: TEI, DocBook etc.
- Did you know that a Microsoft Word document is actually an XML file?
- Types of XML files you may come across in the language industry: TMX, TBX, XLIFF.

---

## (IM2) Managing data: JSON, YAML, relational databases, Semantic Web.
- Two-dimensional tables (à la Excel) and how to represent them in plain text: CSV (Comma-Separated Values), TSV (Tab-Separated Values) etc.
- When a table isn’t enough: the concept of ‘structured data’.
- Representing structured data in XML.
- JSON and YAML as alternatives for representing structured data.
- A quick introduction to relational databases: why would you ever need one instead of just a pile of JSON files?
- Meet SQL, the query language for relational databases.
- Finally, a look at RDF and the ‘Semantic Web’ as an alternative approach for working with structured data.

---

## (IM3) Understanding Internet technology: how the Internet works under the hood
- ‘The Internet’ versus ‘the Web’.
- A quick introduction to how the Internet works: URLs and domain names, requests and responses, browsers and servers, “the cloud”
- The anatomy of a webpage: HTML, CSS, JavaScript.
- Language codes in HTML.
- Multilingualism on the Internet: how are various languages represented on the Internet in terms of content volumes and user numbers?
- Non-ASCII characters in Internet domain names.
- The importance of human-readable URLs for people, search engines and AI agents.

---

## (UI1) Understanding user interfaces: what designing a good user experience is about
-  Interfaces for humans: command-line, point-and-click, chat interfaces.
- Metaphors and skeumorphism in user interface design: buttons, tabs etc.
- Trends in user interface design, e.g. Flat Design.
- Responsive design for different screen sizes.
- A quick introduction to User Experience (UX), Interaction Design.
- Accessibility in user interfaces.
- Interfaces for machines rather that humans: APIs (Application Programming Interfaces), MCP (Model Context Protocol).

---

## (UI2) Software localisation and globalisation: the challenge of translating on-screen text
- The concept of ‘locale’.
- ISO standards for abbreviations of language names and country names.
- The Unicode CLDR (Common Locale Data Repository).
- Configuring and customising various software packages for specicifc locales.
- Changing the user interface language in various software packages.
- How software localisation differs from text translation: the challenges when translating on-screen text for user interfaces.

---

## (UI3) Managing multilingual websites: pitfalls to avoid on the multilingual web
- Indicating the language/locale in the URL.
- Guessing the user’s preferred language/locale from browser settings and/or geolocation.
- Offering choice to the user through language selectors or splash screens.
- Why you probably shouldn’t use flags as symbols for languages.
- Boilerplate text versus main content.
- Dealing with content gaps: what if we don’t have a content item in the user’s preferred language?
- Fallback languages.
- Tread carefully with machine translation.
- Dealing with user-generated content.

---

## Finally, what is *not* included in this course 
- Computer-aided translation (CAT), translation management systems (TMS)
- Machine translation (MT), MT evaluation, MT post-editing
- Terminology management, terminology extraction

### Where to get this from instead
- 340320 VO Machine Translation (Dragoș Ciobanu)
  - 340100, 340007, 340369 UE Machine Translation
- 340109 VO Fachkommunikation und Terminologie (Vesna Lušicky)

---

## That’s it, see you next week!
