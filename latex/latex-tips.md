Gambar
======

Di awal:

```latex
  \usepackage{graphicx}
```

Menggunakan di text:

```latex
  ... cake can be seen in Figure~\ref{fig:swtechstack}

  \begin{figure}
    \begin{center}
      \includegraphics[scale=0.5]{images/layerCake.png}
    \end{center}
    \caption{Semantic Web technology stack}
    \label{fig:swtechstack}
  \end{figure}
```

Listing program
===============

Di awal:

```latex
  \usepackage{listings}
  ...
  ...
  \lstset{numbers=left,basicstyle=\scriptsize,numberstyle=\scriptsize,frame=tb,captionpos=b,backgroundcolor=\color{light-gray},showspaces=false,showstringspaces=false}
```

Contoh pemakaian:

```latex
\lstset{language=XML,caption=XML declaration for XHTML document}
\begin{lstlisting}
    <?xml version="1.0" encoding="UTF-8" ?>
\end{lstlisting}
```

Footnote
========

```latex
text\footnote{asdasda}
```

Citation
========

di bibliografi:

```latex
\bibitem{infomaproposal}Tim Berners-Lee, \textit{Information Management: A Proposal}, \url{http://www.w3.org/History/1989/proposal.html}, accessed on January 23rd, 2009, 10:21AM.
```

di text:

```latex
asdasda~\cite{infomaproposal}
```

Index
=====

di teks:

```latex
Cloud Computing adalah \index{Cloud Computing} suatu ...
```

bagian dari suatu indeks:

```latex
PaaS adalah \index{Cloud Computing!PaaS} suatu ...
```

Glossary, Acronym, dan Symbol
=============================

Buat file masing-masing untuk glossary, acronym, dan simbol:

Glossary
--------

```(def-glossaries.tex)
\newglossaryentry{Linux}
{
  name=Linux,
  description={is a generic term referring to the family of Unix-like
               computer operating systems that use the Linux kernel},
  plural=Linuces
}
```

Acronym 
-------

```(def-abbreviations.tex)
%Some entries for the list of symbols
\newglossaryentry{symb:Pi}{
name=$\pi$,
description={A mathematical constant whose value is the ratio of any circle's circumference to its diameter.},
sort=symbolpi, type=symbolslist
}
\newglossaryentry{symb:Phi}{
name=$\varphi$,
description={An angle.},
sort=symbolphi, type=symbolslist
}
\newglossaryentry{symb:Lambda}{
name=$\lambda$,
description={Lambda indictes an eigenvalue in the mathematics  of linear algebra.},
sort=symbollambda, type=symbolslist
}
```

Acronym
-------

```(def-abbreviations.tex)
\newacronym{www}{WWW}{The World Wide Web}
```

Penggunaan di dalam teks:

```

\usepackage[acronym]{glossaries}
%Generate a list of symbols
\newglossary[slg]{symbolslist}{syi}{syg}{List of symbols}

\makeglossaries
\loadglsentries{components/def-abbreviations}
\loadglsentries{components/def-symbols}
\loadglsentries{components/def-glossaries}
 
\begin{document}

....
....
% This is how to use a glossary:
% glossary: 
%	A \gls{Linux} entry 
%	Plurals: \glspl{Linux}. 
%	Symbol: \gls{symb:Pi} 
%	Acronym: \gls{www}

```
