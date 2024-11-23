---
title: Benzene
firstDate: 5th Jul, 2024
draft: true
tags:
  - "#ZP"
  - chemistry
  - organic-chemistry
aliases:
---

This is benzene:

```tikz
\usepackage{chemfig} 
\begin{document}
\chemfig{**6(------)} 
\end{document}

```


- Circle represents delocalized $\pi$ electrons.
- This delocalization of $e^-$ gives rise to [[resonance]], where the three double-bonds continuously switch between each other:
```tikz
\def\pgfsysdriver{pgfsys-xetex.def}
\usepackage{chemfig} 

\begin{document}
	\chemfig{*6(=-=-=-)} 
\schemestart
	\arrow{<=>} 
\schemestop
	\chemfig{*6(-=-=-=)}

\end{document}

```

# Related Notes


# Literary (Further Reading)
