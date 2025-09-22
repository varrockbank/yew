# Syntax

The evaluation of Orgmode vs Markdown is really an issue of what is the best
language to take notes.

Markdown is more readable HTML.

Orgmode was for notetaking in Emacs. Its constructs has specific
behavior in Emacs. Orgmode is generally more logical then Markdown.
For example, `~~foobar~~` for strikethrough in Markdown vs `+foobar+` is orgmode. 

Markdown doesn't have underline. Markdown is also not one thing and 
worsely defined as a standard than Emacs. Emacs OrgMode IS THE STANDARD. 

Orgmode is in general more verbose than Markdown. However, if you are using 
Emacs then you don't actually have to type out this verbosity. The benefit 
of verbosity is also consistency. For example, Orgmode has one way of doing 
various kind of block codes.

At any rate, the question remains what is the best syntax for note-taking? 

Argument in favor of Orgmode vs Markdown: 
There is a clear target to strive for feature parity towards.

## Light Markup Languages

A common term for these set of language and syntax are called "light markup languages".
The term still hints at a markup for HTML. 

At any rate, Github supports a variety of these light markup languages.

In consideration of the de facto light markup language for Yew, we should work backwards
from the light markup languages supported by Github. As one HN user posits "Github is king".

Official: https://github.com/github/markup

### Tier List

#### Elimination Round 
Pod https://en.wikipedia.org/wiki/Plain_Old_Documentation 
  - More verbose than Markdown.
  - May be useful to document Perl code.
  - Recommendation: Markdown > Pod

Creole https://en.wikipedia.org/wiki/Creole_(markup)
  - More verbose than Markdown
  - Feels like Javascript template strings with interpolation 
  - You're more aware of the markup than just writing. Feels like code 

Rdoc https://ruby.github.io/rdoc/
  - The R stands for Ruby no R 
  - More for Ruby documentation
  - Kind of ironic that the documentation doesn't include actual literal examples
  - current development status is "quiet"

Textile https://textile-lang.com/
  - More of shorthand for HTML rather than plaintext notetaking

RST https://docutils.sourceforge.io/rst.html

```
Title
=====

Section
-------

Subsection
~~~~~~~~~~

*italic*
**bold**
``monospace``
        
* This is a bulleted list.
* a list

  * with a nested list
  * and some subitems

1. This is a numbered list.
2. It has two items too.

#. This is a numbered list.
#. It has two items too.

`A cool website`_

.. _A cool website: http://sphinx-doc.org
..
   _This: is a comment!
..
   _This: The link target is defined at the bottom of the section with .. _<link text>: <target>.
```

- "easy-to-read, what-you-see-is-what-you-get plaintext"
- yeah.... idk
  - links at bottom of section
  - weird looking syntax for comments
  - require empty line between nested list 
  - in general, you need a RST-aware editor that indents properly. Doesn't seem its meant to be handwritten 
  - indeed: https://news.ycombinator.com/item?id=27746646
  - good enough for software docs but not enough text controls for blogging. i.e. bold + italic.
    this is more a redflag about the half-baked implementation 

##### Mediawiki

Good comparison table here:

- Powerful, as evidenced by Wiki
- Meant for Wiki and a proxy for HTML, rather than notetaking in source
- Verbose
- 
#### Showdown

Markdown vs Org vs Asciidoc 

##### Markdown vs Asciidoc 

Syntactically, not that big of a deal. Maybe less than 3% of the time 
you'll have some annoyance with Asciidoc, but it's more powerful. 

One difference is Asciidoc allows for more metadata and commentary.


##### Asciidoc

Asciidoc is also a zombie project.

Asciidoc is also built for technical documentation. i.e. generating
a table of contents and search. Perhaps Asciidoc syntax is if you intend on using the Toolchain .


Markdown
 - fragmented implementation but "common markdown" widely supported, to some degree

Org
  - `Elijah Wood :: He plays Frodo`. inlines definition list.
  - Org: consistent syntax, clear implementation target, albeit a bit verbose

After all this work, I found this: https://hyperpolyglot.org/lightweight-markup


#### Mermaid Diagrams 


#### Honorable Mention

BBCode 
- good for short internet posts but not notetaking 