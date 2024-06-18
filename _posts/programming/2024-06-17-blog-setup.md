---
layout: default
title: "Setting up a Math blog"
---

### Glossary

| Term      | Definition     |
|-----------|----------------|
| **[HTML](https://html.com/)** | (Hypertext Markup Language) is a standard markup language for building files that are showcased as web pages. |
|**[CSS](https://en.wikipedia.org/wiki/CSS)** | (Cascading Style Sheets) is a style sheet language used for describing the presentation of a document written in HTML or XML, including colors, layout, and fonts. |
|**[JavaScript](https://en.wikipedia.org/wiki/JavaScript)** | is a programming language that is primarily used for scripting web pages and creating web applications. Not to be confused with **Java**, which is another high-level programming language.|
|**Web server / Hosting service**| provides the infrastructure and services necessary for websites to be accessed and maintained on the internet. |
|||
| **[GitHub Pages](https://pages.github.com/)** | is a system allowing users to create and serve websites directly from their GitHub repositories. The service is free for public repositories and simple pages can be created and served with very little configuration required. Behind the scenes GitHub Pages uses a static site generator called **Jekyll**. |
| **[Jekyll](https://jekyllrb.com/)** | is a static site generator written in **Ruby**. It takes text files (like Markdown), applies templates, and generates a complete static website made up of **HTML**, **CSS**, and **JavaScript** files. These files can then be hosted on any **web server** or **hosting service**. |
|**[Bundler](https://bundler.io/)** | is a Ruby package manager that manages an application's dependencies. |
|||
|**[Markdown](https://www.markdownguide.org/cheat-sheet/)** | is a lightweight language with plain-text formatting syntax. |
|**[Mathjax](https://docs.mathjax.org/en/latest/basic/mathjax.html)** | is an open-source JavaScript display engine for mathematics that works in all modern browsers. It provides support for LaTeX and MathML syntax. |
|||
|**[Ruby](https://www.ruby-lang.org/en/)** | is a high-level programming language. |


<br>

### Mathjax
[MathJax](https://docs.mathjax.org/en/latest/basic/mathjax.html) is an open-source JavaScript display engine for LaTeX, MathML, and AsciiMath notation that works in all modern browsers. It requires no setup on the part of the user (no plugins to download or software to install), so the page author can write web documents that include mathematics and be confident that users will be able to view it naturally and easily. One simply includes MathJax and some mathematics in a web page, and MathJax does the rest.

#### Using MathJax from a Content Delivery Network (CDN)

[The easiest way](https://docs.mathjax.org/en/latest/web/start.html) to use MathJax is to link directly to a public installation available through a Content Distribution Network (CDN). When you use a CDN, there is no need to install MathJax yourself, and you can begin using MathJax right away. The CDN will automatically arrange for your readers to download MathJax files from a fast, nearby server. One such CDN, **jsdelivr**, can be used by including the following javascript code in the header of your webpage. 

    <script type="text/javascript" id="MathJax-script" async
        src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
    </script>

<br>

### References
 - [Carpentries Incubator lesson on Building Websites With Jekyll and GitHub](https://carpentries-incubator.github.io/jekyll-pages-novice/)
