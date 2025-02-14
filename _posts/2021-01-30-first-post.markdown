---
layout: post
title:  "Markdown Cheatsheet"
date:   2021-01-30 20:20:20 +0100
categories: web
tags: cheatsheet markdown
---
<!--more-->

{% include math.html %}

Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-title.MARKUP`

Jeykll blog posts use markdown syntax, where a linebreak is achieved by keeping an empty line between two paragraphs (two line breaks). Word's shift enter line break doesnt exist. Adding further empty lines will not increase the space between paragraphs, it is therefore non-space sensitive after 1 line break. With regular spaces it's also space insensitive after the first one.

Jekyll also offers powerful support for code snippets.

Javascript:
```javascript
const hotline = new Audio("sounds/elevator.mp3");
document.addEventListener("keydown", toggleRotation);
function toggleRotation(e) {
  if (e.code == 'Space') {
    render = (render == freeze) ? animate : freeze;
    isRoatationToggled = !isRoatationToggled; //Roatate is def not a typo...
    hotline.play();
  }
}
```

Same code but in ruby (see the different formatting, I doubt it would compile...):
```ruby
const hotline = new Audio("sounds/elevator.mp3");
document.addEventListener("keydown", toggleRotation);
function toggleRotation(e) {
  if (e.code == 'Space') {
    render = (render == freeze) ? animate : freeze;
    isRoatationToggled = !isRoatationToggled; //Roatate is def not a typo...
    hotline.play();
  }
}
```

----

## Header 2 (H1 is reserved for post titles)

Jekyll is an active open source project that is updated frequently. If the github-pages gem on your computer is out of date with the github-pages gem on the GitHub Pages server, your site may look different when built locally than when published on GitHub. To avoid this, regularly update the github-pages gem on your computer.

1. Open Git Bash.
2. Update the github-pages gem.
    * If you installed Bundler, run bundle update github-pages. (this is my case, because I have Windows...)
    * If you don't have Bundler installed, run gem update github-pages.

And now the moment of truth... This is a math post because I decided to include a math snipet to showcase myself how to include "latex", or I'd rather say [Mathjax](https://math.stackexchange.com/editing-help), formatting:

 {% raw %}
 Block equation:

$$\sum_{i=0}^{n}\frac{1}{2^n} = 2$$

In-line equation: \\(\sum_{i=0}^{n}\frac{1}{2^n} = (\frac{1}{2^0})\cdot \frac{1}{1-\frac{1}{2}} = 2\\)

An arbitrary matrix:

$$
\begin{bmatrix}
    x_{11}       & x_{12} & x_{13} & \dots & x_{1n} \\
    x_{21}       & x_{22} & x_{23} & \dots & x_{2n} \\
    \cdots & \cdots & \cdots & \cdots & \cdots \\
    x_{d1}       & x_{d2} & x_{d3} & \dots & x_{dn}
\end{bmatrix}
=
\begin{bmatrix}
    x_{11} & x_{12} & x_{13} & \dots  & x_{1n} \\
    x_{21} & x_{22} & x_{23} & \dots  & x_{2n} \\
    \vdots & \vdots & \vdots & \ddots & \vdots \\
    x_{d1} & x_{d2} & x_{d3} & \dots  & x_{dn}
\end{bmatrix}
$$

A vector

$$
\begin{pmatrix}
    x_{1} \\
    x_{2}  \\
    \cdots  \\
    x_{d} 
\end{pmatrix}
$$


 {% endraw %}

 Using the raw liquid tag to ensure Markdown parsers do not interfere with MathJax syntax.

 ![Computer Science has always been about math][math-meme]
 *Insert image test*

That was the end of the post, below you won't see anything else, but in the markdown file I can see an additional line (with a proper line break before) with "\[math-index\]: /blog/announcement", which allows me to use `_[announcement-index]` as a variable with an assigned hyperlink. If I use one without a value assignment then I get this for instance: [Jekyll Talk][jekyll-talk].

Edit, just wanted to add a table:

To add a table, use three or more hyphens (---) to create each column’s header, and use pipes (\|) to separate each column. You can optionally add pipes on either end of the table.

| Syntax      | Description |
| ----------- | ----------- |
| Lorem       | Ipsum       |
| Paragraph   | Text        |
| Paragraph   | Text        |
| Paragraph   | Text        |

You can use pipes | To have a 2 column block of text

[math-index]: /math
[math-meme]:{{ site.baseurl }}/images/first_post/cs_is_math.png