---
layout: default
title: "Setting up a Math blog"
---

### HTML
Hypertext Markup Language is a standard mark–up language for building files that are showcased as web pages.

<br>

### Mathjax
[MathJax](https://docs.mathjax.org/en/latest/basic/mathjax.html) is an open-source JavaScript display engine for LaTeX, MathML, and AsciiMath notation that works in all modern browsers. It requires no setup on the part of the user (no plugins to download or software to install), so the page author can write web documents that include mathematics and be confident that users will be able to view it naturally and easily. One simply includes MathJax and some mathematics in a web page, and MathJax does the rest.

#### Using MathJax from a Content Delivery Network (CDN)

[The easiest way](https://docs.mathjax.org/en/latest/web/start.html) to use MathJax is to link directly to a public installation available through a Content Distribution Network (CDN). When you use a CDN, there is no need to install MathJax yourself, and you can begin using MathJax right away. The CDN will automatically arrange for your readers to download MathJax files from a fast, nearby server. One such CDN, **jsdelivr**, can be used by including the following javascript code in the header of your webpage. 

    <script type="text/javascript" id="MathJax-script" async
        src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
    </script>

