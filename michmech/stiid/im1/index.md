## Plan for today
- Plain text
- Approaches for adding structure and/or formatting to plain text  
  - Markdown
  - LaTeX
  - XML
    - Common XML schemas: Open Document Format, Office Open XML, DocBook, TEI
    - Related technologies: HTML, XSL
    - XML schemas common in the language industry: TMX, TBX, XLIFF

---
## What is plain text?
- A sequence of Unicode codepoints *only*
  - No formatting: no italics, no bold etc.
  - No explicit structure: is this a heading, a subheading, a bulletted list...?
  - No information about language

---
## What isn't plain text?
- A Microsoft Word document
- A Google Docs document
- etc.

---
## How do you edit plain text?
- The file usually has the extension `.txt`
- Most operating systems have an app for editing plain text files.
  - Windows: Notepad
  - Ubuntu Linux: GNME Text Editor
- All programming code (eg. code in Python, in JavaScript...) is also plain text.
  - Programmers use specialised code editors.

---
## What is the opposite of plain text?
- "Rich text", "formatted text", "structured text"

---
## Markdown

---
## The syntax of Markdown

```
# Weekend Trip to Salzburg

We are planning a **three-day getaway** to explore the historic old town of *Salzburg*. The weather forecast predicts light rain, so we need to pack accordingly. 

Remember to check the [Salzburg Tourism Board](https://salzburg.info) for any last-minute event updates or scheduling changes.

## To-Do List Before Leaving

- Book the train tickets online.
- Confirm the hotel check-in time.
- Water the apartment plants.
```

---
## Output from Markdown

> # Weekend Trip to Salzburg
> 
> We are planning a **three-day getaway** to explore the historic old town of *Salzburg*. The weather forecast predicts > light rain, so we need to pack accordingly. 
> 
> Remember to check the [Salzburg Tourism Board](https://salzburg.info) for any last-minute event updates or scheduling changes.
> 
> ## To-Do List Before Leaving

> - Book the train tickets online.
> - Confirm the hotel check-in time.
> - Water the apartment plants.

---
## Working with Markdown
- You can use any plain text editor
- Many specialised Markdown editors exist (eg. Obsidian)
  - Syntax highlighting
  - Keyboard shortcuts
  - Export to PDF, HTML...

---
## What is Markdown used for?
- Popular for technical documentation
- LLMs like Markdown!

---
## What else do you need to know about Markdown?
- Created by John Gruber in 2004
- Not strictly standardised, many different flavours exist
  - GitHub-Flavoured Markdown (GFM)
  - CommonMark
  - etc.

---
## Markdown "competitors"
- reStructuredText
- AsciiDoc
- etc.

---
## LaTeX

---
## The syntax of LaTeX

```
\begin{document}

\section*{Weekend Trip to Salzburg}

We are planning a quick \textbf{three-day getaway) to explore the historic old town of \textit{Salzburg}. The weather forecast predicts light rain, so we need to pack accordingly. 

Remember to check the \href{https://salzburg.info}{Salzburg Tourism Board} for any last-minute event updates or scheduling changes.

\subsection*{To-Do List Before Leaving}

\begin{itemize}
    \item Book the train tickets online.
    \item Confirm the hotel check-in time.
    \item Water the apartment plants.
\end{itemize}

\end{document}
```

---
## Output from LaTeX

> # Weekend Trip to Salzburg
> 
> We are planning a **three-day getaway** to explore the historic old town of *Salzburg*. The weather forecast predicts > light rain, so we need to pack accordingly. 
> 
> Remember to check the [Salzburg Tourism Board](https://salzburg.info) for any last-minute event updates or scheduling changes.
> 
> ## To-Do List Before Leaving

> - Book the train tickets online.
> - Confirm the hotel check-in time.
> - Water the apartment plants.

---
## Working with LaTeX
- Complex tooling
  - Installing/managing plug-ins etc.
  - Producing PDFs 
- Specialised LaTeX editors exist (eg. Overleaf)
  - Syntax highlighting
  - Keyboard shortcuts
  - Export to PDF, HTML...

---
## What is LaTeX used for?
- Popular for scientific publications

---
## What else do you need to know about LaTeX?
- LaTeX: created by Leslie Lamport in 1984
  - TeX: ceated by Donald Knuth in 1978
- Not strictly standardised
  - Community-driven

---
## XML

---
## Limitations of Markdown
- Custom inline markup
  - Names of people, placenames, dates, times...
- Non-typical documents
  - Theatrical plays, dictionary entries...
- Non-typical layouts
  - Parallel bilingual text...

---
## The syntax of XML

```
<article>
    <title>Weekend Trip to Salzburg</title>

    <paragraph>
        We are planning a quick three-day getaway to explore the historic old town and catch a concert. The weather forecast predicts light rain, so we need to pack accordingly.
    </paragraph>

    <paragraph>
        Remember to check the <link url="https://salzburg.info">Salzburg Tourism Board</link> for any last-minute event updates or scheduling changes.
    </paragraph>

    <subtitle>To-Do List Before Leaving</subtitle>

    <list type="bulletted">
      <item>Book the train tickets online.</item>
      <item>Confirm the hotel check-in time.</item>
      <item>Water the apartment plants.</item>
    </list>
</article>
```

