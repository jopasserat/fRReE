# Description #

This package contains:
 - the LaTeX style package fRReE.sty to design and make available publications
 - some logos in png and eps, plus the related gimp project (xcf) of various institutions
 - a sample document using the package template-fRReE.tex

# Usage #
Use git clone to get the original repository, then rename template-fRReE.tex and modify it to fit your publication.

Most variables are filled with ??? by default when no other value is explicitely set.

# Documentation #

 - **\RRdate { date }**

This command is optional, but if you do not use it, you will
get a LaTeX warning. The date argument is normally formed of the
month and year of publication.


  - **\RRversion { N }**

This command is used when the current document is not the
original version but the N version (with at least N 2).


  - **\RRdater { date }**

This indicates the revision date, if it is a version two
or greater.

    %% Case of a v2
    \RRversion{2}
    % publication date of version 2
    \RRdater{November 2008}


  - **\RRauthor**  

    - *\RRauthor { author }*  
    - *\RRaffiliation { affiliation }*
    - *\RRaffiliation [ label ] { affiliation }*
    - *\RRaffiliationref{ label }*


This command sets the name of the author of the report. Of course, the argument
ment is formed of the complete first and last names. One can optionally
mention affiliations, using the `\RRaffiliation` command. Multiple authors are separated by the command `\and`.

    \RRauthor {
      % first author and his affiliations 
      John \textsc{Doe}
      \RRaffiliation[sfn0]{Imperial College London}
      \RRaffiliation[sfn1]{ISIMA, Institut Sup\'erieur d'Informatique, de Mod\'elisation et de ses Appplications, BP 10125, F-63173 AUBIERE}
      \RRaffiliation[sfn2]{Clermont Universit\'e, Universit\'e Blaise Pascal, BP 10448, F-63000 CLERMONT-FERRAND}
      \RRaffiliation[sfn3]{CNRS, UMR 6158, LIMOS, F-63173 AUBIERE}
      \and
      \\Toto \textsc{Toto}
      \RRaffiliationref{sfn0}
      \RRaffiliationref{sfn1}
      \and
      \\Alice \textsc{Bob}
      \RRaffiliationref{sfn2}
      \RRaffiliationref{sfn3}
      \and
      \\Arthur \textsc{Merlin}
      \RRaffiliationref{sfn0}
      \RRaffiliationref{sfn1}
      \RRaffiliationref{sfn3}
    }


The `\RRaffiliation` command hang the affiliation as a footnote on page one for an author.
If you want to share the same affiliation between two authors, use 
the command `\RRaffiliation[label]{Affiliation}` with a label argument for the first author, and for the second
the command `\RRaffiliationref{label}` with the same label.


  - **\RRtitle { titre }**

Set the title of the report.


    %% full title
    \RRtitle{Template and examples of a publication \\
    distributed using the fRReE.sty class}


  - **\RRtitlehead { short title }**

In the case where the title is very long, we can use `\RRtitlehead` to 
override he value of the title to be used in header of odd-numbered pages.
This command, can only be called after `\RRtitle`, and of course before `\begin{document}`.

      %%
      %% short version of the title in header on odd-numbered pages
      \RRtitlehead{Example of fRReE.sty}

  - **\RRauthorhead { short author }**

The header on even pages contains a list of authors automatically generated.
If this list is so long that it does not fit on the
page, we can use the command `\RRauthorhead` to override the header with a shorted version on even-numbered pages.


    %% Appear in the header of each even page
    \RRauthorhead{Toto et al 2014}


  - **\RRnote { note }**

This command allows you to put notes on the first page.
It is not recommended to use the command `\footnote` on the first page.


    %%
    \RRnote{This is a note}
    \RRnote{This is another note}


  - **\RRabstract { resume }**

Defines the summary. Accepts text or `\input{filename}` content.
One can also use `\resume` an alias.


  - **\RRkeyword { keyword1, keyword2, ... }**

A simple list of keywords for the publication. Can be aliased by 
`\keywords`.

