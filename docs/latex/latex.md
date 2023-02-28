---
layout: default
title: Latex
nav_order: 8
has_children: true
permalink: docs/latex
---

### Normal text in math mode [Source](https://texblog.org/2012/09/24/normal-text-in-math-mode/)

The font type LaTeX uses in math mode is somewhat special since it is optimized for writing mathematical formulas. Letters are printed in italics, with more space left in-between, spaces are ignored. In certain cases it may be desirable to include “normal text” within an equation. There is a simple way to add “normal text” fragments in math mode.

```latex
$...\textrm{normal text}...$
```

Alternatively, using the amsmath package:

```latex
\usepackage{amsmath}
 
$...\text{normal text}...$
```

Normal text can be added no matter which math mode you are using.

Consider the following descriptive illustration of the fraction notation, first in math mode and below in “normal text”.


![fraction-notation-math-mode](https://i0.wp.com/texblog.org/Wordpress/wp-content/uploads/2012/09/fraction-notation-math-mode1.png?resize=276%2C166)

```latex
\documentclass{article}
\usepackage{amsmath}
\begin{document}
\begin{align*}
    fraction&=\frac{numerator}{denominator}\\
    &\\
    \text{fraction}&=\frac{\text{numerator}}{\text{denominator}}
\end{align*}
\end{document}
```

Taking a closer look at the first two characters of “fraction” in math mode shows that LaTeX assigns them more space, giving the word a somewhat unnatural appearance.

Here is another example where switching to normal text is desirable. Any whitespace is added in “normal text” mode since math mode ignores it.

![normal_text_math_mode1](https://i0.wp.com/texblog.org/Wordpress/wp-content/uploads/2012/09/normal_text_math_mode11.png?resize=246%2C105)

```latex
\documentclass{article}
\usepackage{amsmath}
\begin{document}
\[
    f(x) =
    \begin{cases}
        0 & \text{if $x=0$,}\\
        \frac{1}{x} & \text{otherwise.}
    \end{cases}
\]
\end{document}
```

See User Guide for the amsmath Package for more details on the amsmath package.

Addendum
For multi-letter variables in math mode, use \mathit{} to omit whitespace in-between letters. Can you see the difference?

```latex
$\mathit{def}$
```

multi-letter-variable-math-mode

Thanks for your comment João!