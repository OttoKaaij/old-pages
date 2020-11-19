---
layout: page
title: Latex Pandoc Markdown Beamer Magic 101
---

# Introduction

Using pandoc to convert from markdown to pdf has all the benefits of markdown
writing. It's fast, super easy for basic stuff, super lightweight. It also
comes with (almost) all the advantages of LaTeX. Clean typeset documents, well
managed references, etc.

This guide is on some quirks and some how to's and some good stuff. Pandocs'
user manual is fantastic, but clunky. This guide is basically a compilation of
the useful sections in that manual.

# Compiling

```
$ pandoc example.md -o example.pdf
```

Can also use a separate metadata file (with just the preample)

```
$ pandoc metadata.yaml example.md -o example.pdf
```

You can put chapters in separate files

```
$ pandoc metadata.yaml *.md -o example.pdf
```

Use utility program 'entr' to autocompile:

```
(ls *.md | entr pandoc metadata.yaml *.md -o example.pdf &)
```

# Reports

## The preamble

a list of preamble variables, good reference.

```yaml
---
title: Cyber Range User Manual
author: 
    - name: Otto Kaaij
      affiliation: TUDelft
      title: Teaching Assistant
      street: Suezkade 186
      postal: 2517CH
      KVK: 0123456789
      BTW: 0123456789
      extra: Extra info

toc: true
toc-depth: 2
numbersections: true
secnumdepth: 3

indent: true //paragraph indent vs line breaks
colorlinks: true
---
```

To enable the custom author tags, add this to your
/usr/share/pandoc/data/templates/default.latex

```
$if(author)$

\author{
	$for(author)$
	$if(author.name)$
	$author.name$
		$if(author.student-no)$
		- $author.student-no$
		$endif$
		$if(author.affiliation)$
		- $author.affiliation$
		$endif$
		$if(author.title)$
		\\ \textit{$author.title$}
		$endif$
		$if(author.street)$
		\\ \texttt{$author.street$}
		$endif$
		$if(author.postal)$
		\\ \texttt{$author.postal$}
		$endif$
		$if(author.KVK)$
		\\ Kvk-nr: \textit{$author.KVK$}
		$endif$
		$if(author.BTW)$
		\\ Btw-nr: \textit{$author.BTW$}
		$endif$
		$if(author.extra)$
		\\ \texttt{$author.extra$}
		$endif$
	$else$
	$author$
	$endif$
	$endfor$
	}
$endif$
```

## Tricks

### Table labling:

```
| table | column |
| ----  | -----  |
| content | content |

: Labeled table
```
### Footnotes



# Slides

