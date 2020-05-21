---
layout: post
title:  "Edge Cases"
date:   2020-04-13 17:04:01
categories: post
---
Some edge cases and cautionary examples on using Markdown for writing content using this theme. In particular, list syntax can really knot things up.
<!--more-->

### Mathjax improperly parsing greater and less than and ampersands inside blocks

The mathjax HTML ```<head>``` scripts have been modified to properly render block style mathjax expressions inside a ```$$ ... $$``` set of character pairs,
using the standard Kramdown parser. Some examples sent to me by Quxiaofeng are now parsing correctly, I believe.

This code:

```latex
$$
  D = \left(\begin{matrix}
  1 & -1 & & & & \\
  &    & \cdots &   & \\
  &    &        & 1 & -1
 \end{matrix}
 \right)
$$
```
yields this:

$$
D = \left(\begin{matrix}
  1 & -1 & & & & \\
  &    & \cdots &   & \\
  &    &        & 1 & -1
\end{matrix}
\right)
$$

Other examples from the [wikia Tex reference](http://latex.wikia.com/wiki/Matrix_environments):

$$
\begin{matrix}
\alpha& \beta^{*}\\
\gamma^{*}& \delta
\end{matrix}
$$


$$
\begin{bmatrix}
\alpha& \beta^{*}\\
\gamma^{*}& \delta
\end{bmatrix}
$$

$$
\begin{Bmatrix}
\alpha& \beta^{*}\\
\gamma^{*}& \delta
\end{Bmatrix}
$$

$$
\begin{vmatrix}
\alpha& \beta^{*}\\
\gamma^{*}& \delta
\end{vmatrix}
$$

$$
\begin{Vmatrix}
\alpha& \beta^{*}\\
\gamma^{*}& \delta
\end{Vmatrix}
$$

$$
\begin{Vmatrix}
\alpha& \beta^{*}\\
\gamma^{*}& \delta
\end{Vmatrix}
$$

However, a problem still exists for inline matrix notation, from an example [here](https://en.wikibooks.org/wiki/LaTeX/Mathematics#Matrices_in_running_text):

A matrix in text must be set smaller: $$ \bigl(\begin{smallmatrix}a & b \\ c & d\end{smallmatrix} \bigr) $$ to not increase leading in a portion of text. The way this inline matrix is written is: ```$$ \bigl(\begin{smallmatrix}a & b \\ c & d\end{smallmatrix} \bigr) $$```

