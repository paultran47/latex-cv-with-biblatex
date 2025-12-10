---
layout: default
---

# Overview

The journey of a researcher is a long one; every researcher will accumulate an
abundance of research qualifications, publications, presentations, awards, and
teaching experience over time. As a result, a curriculum vitae (CV for short) is
an absolute necessity for job applications and annual performance reviews in the
academic, public, or private sectors, as well as just keeping track of publications.

In the academic world, LaTeX is the standard formatting language and for good
reason: LaTeX makes formatting easy for maintenance and quick updates. It's for
this very reason that I've created a CV entirely in LaTeX. To further tailor
this for academics, the CV has integration with the awesome [biblatex package](https://ctan.org/pkg/biblatex)
to easily update and maintain publications of all kinds.

Please note that because I'm an Economics PhD candidate and applied
macroeconomist on the 2025--26 job market, the files for this CV are customised
for an economist that is going on the job market in mind. As such, some code
and conventions might not be relevant for your own research needs!

## Prerequisites

To work with the source code and tailor this CV for your own needs, you will
need the following installed:

* Latest version of MikTeX or TeXLive.
* The following LaTeX packages: [newtxttext](https://ctan.org/pkg/newtx), [fontenc](https://ctan.org/pkg/fontenc),
[geometry](https://ctan.org/pkg/geometry), [ragged2e](https://ctan.org/pkg/ragged2e),
[fancyhdr](https://ctan.org/pkg/fancyhdr), [xcolor](https://ctan.org/pkg/xcolor),
[url](https://ctan.org/pkg/url), [hyperref](https://ctan.org/pkg/hyperref),
[booktabs](https://ctan.org/pkg/booktabs), [fmtcount](https://ctan.org/pkg/fmtcount),
[refcount](https://ctan.org/pkg/refcount), [datetime](https://ctan.org/pkg/datetime),
[titlesec](https://ctan.org/pkg/titlesec), [lastpage](https://ctan.org/pkg/lastpage),
[paralist](https://ctan.org/pkg/paralist), [enumitem](https://ctan.org/pkg/enumitem),
[array](https://ctan.org/pkg/array), and [biblatex](https://ctan.org/pkg/biblatex).

## Details

### Preamble

Before the actual CV document is rendered, your preamble (in the .tex file)
should look similar to the following (don't mind the comments):

```latex
\documentclass[a4paper, 10pt]{article}

%% Loading .sty file
\usepackage{tran_paul_le_cv}

%% Adding space before section headings
\titlespacing{\section}{0pt}{2ex}{1ex}

%% Entering in name and information
\name{Paul L. Tran}
\info{Office: & \href{https://liberalarts.utexas.edu/economics/ph-d-program/}{Department of Economics},\\
  & College of Liberal Arts,\\
  & University of Texas at Austin,\\
  & 2225 Speedway,\\
  & BRB 2.128, C3100,\\
  & Austin, Texas 78712\\
  \textbf{Citizenship}: & \textbf{United States of America}\\
  Cell: & +1 (512) 704-3025\\
  Email: & \href{mailto:pltran@utexas.edu}{pltran@utexas.edu}\\
  Website: & \href{https://paulletran.com/}{https://paulletran.com/}
}
%=================================================

%=================================================
%% Setting up bibliography
\addbibresource{tran_paul_le_cv_wps.bib}
% \addbibresource{tran_paul_le_cv_wips.bib}
\DeclareSourcemap{
  \maps[datatype = bibtex, overwrite]{
    \map{
      \step[fieldset = month, null]
    }
  }
}
\ExecuteBibliographyOptions{useprefix = true}

%% Add selected items from .bib files to be shown
\addtocategory{wps}{
  tran_fomcnn_jmp,
  tran_opecnn,
}
% \addtocategory{wips}{}
%=================================================

%=================================================
\begin{document}
  \maketitle
  \thispagestyle{firststyle}
  \section{Education}
  \begin{tabular}{p{4cm} p{2.5cm} p{3.6cm} p{4.1cm}}
    2020--May 2026 (Expected) & \textbf{PhD} & Economics & University of Texas at Austin
  \end{tabular}
  \begin{compactitem}
    \item Dissertation: ``Essays on Applications of Text Analysis in Macroeconomics''
  \end{compactitem}
  %% Putting standard vertical spacing of 1em due to compactitem and tabular environments not playing nice with each other
  \vspace{1em}
  \begin{tabular}{p{4cm} p{2.5cm} p{3.6cm} p{4.1cm}}
    2023 & \textbf{MS en Passant} & Economics & University of Texas at Austin\\
    2017 & \textbf{BA} & Mathematics, \newline Mathematical Economics & Pomona College
  \end{tabular}

  \section{Research Interests}
  \begin{compactitem}\parskip = 0cm
    \item \textbf{Fields}: Macroeconomics, Monetary Economics
    \item \textbf{Methods}: Text Analysis, Machine Learning
    %% Uncomment the following line to display the total value of publications, submissions, and so on that are included in the
    %% calculation of sumpapers (see .sty file for definition).
    % \item I have authored or co-authored \numberstringnum{\getrefnumber{sumpapers}} publications on economic topics. A list of these appear below.
  \end{compactitem}

  \section{Dissertation Committee and References}
  \begin{tabular}{p{5.6cm} p{6.6cm}}
    \textbf{Olivier Coibion (Co-Supervisor)} \newline Malcolm Forsman Centennial Professor \newline Department of Economics \newline University of Texas at Austin \newline \href{mailto:ocoibion@austin.utexas.edu}{ocoibion@austin.utexas.edu} \newline +1 (512) 475-8537 & \textbf{Christoph Boehm (Co-Supervisor)} \newline Associate Professor \newline Department of Economics \newline University of Texas at Austin \newline \href{mailto:cboehm@utexas.edu}{cboehm@utexas.edu} \newline +1 (734) 548-1090\\
    &\\
    \textbf{Saroj Bhattarai} \newline Associate Professor \newline Department of Economics \newline University of Texas at Austin \newline \href{mailto:saroj.bhattarai@austin.utexas.edu}{saroj.bhattarai@austin.utexas.edu} \newline +1 (512) 475-8539 & \textbf{Amy Handlan} \newline Yang Family Assistant Professor in Economics \newline Department of Economics \newline Brown University \newline \href{mailto:amy\_handlan@brown.edu}{amy\_handlan@brown.edu}
  \end{tabular}

  %% Adding working papers, works in progress, and publications .bib files
  %% You can include \printbib outside of the publications environment. They just won't be counted towards sumpapers (see .sty file for definition)
  \begin{publications}
    \printbib{wps}
    % \printbib{wips}
  \end{publications}

  \section{Presentations}
  \begin{tabular}{l p{14.3cm}}
    2025 & Texas Macro Job Candidate Conference (College Station, TX), IMIM Rising Stars Seminar Series \newline (Virtual)
  \end{tabular}
  
  \section{Teaching History}\label{sec:teaching_history}
  \begin{compactitem}\parskip = 0cm
    \item Since Fall 2024, student evaluations have rated my teaching 4.6 out of 5 on average.
    \item Since Fall 2020, student evaluations have rated my teaching assistance 4.4 out of 5 on average.
    \item I earned an \href{https://ctl.utexas.edu/teaching-preparation-series}{Advanced Teaching Preparation Certificate} in 2023 from the University of Texas at Austin.
  \end{compactitem}
  %% Putting standard vertical spacing of 1em due to compactitem and tabular environments not playing nice with each other
  \vspace{1em}
  \begin{tabular}{p{2.3cm} p{3.1cm} p{2.3cm} p{6.4cm}}
    University of \newline Texas at Austin & \textbf{Assistant Instructor} & Fall 2024-- & Introduction to Macroeconomics\\
    & \textbf{Teaching Assistant} & Spring 2024 & Macro and the Labor Market \newline (MA course), Andreas Mueller\\
    & & & Labor Economics\newline (MA course), Gerald Oettinger\\
    & & Fall 2021--2023 & Introduction to Microeconomics \newline (Synchronous Massive Online Course \newline for fall), Charity-Joy Acchiardo, \newline Wayne Geerling, Dirk Mateer\\
    & & Summer 2022 & Health Economics, Helen Schneider\\
    & & Fall 2020, \newline Spring 2021 & Introduction to Macroeconomics, \newline Michael Sadler, Charity-Joy Acchiardo
  \end{tabular}

  \section{Other Employment History}
  \begin{compactitem}\parskip = 0cm
    \item Please see the {\hypersetup{linkcolor = black}\hyperref[sec:teaching_history]{``Teaching history''}} section for details about my teaching employment and experience.
  \end{compactitem}
  %% Putting standard vertical spacing of 1em due to compactitem and tabular environments not playing nice with each other
  \vspace{1em}
  \begin{tabular}{lll}
    2018--2020 & \textbf{Senior Research Assistant} & Board of Governors of the Federal Reserve System\\
    2017--2018 & \textbf{Research Assistant} & Board of Governors of the Federal Reserve System
  \end{tabular}

  \section{Honours and Awards}
  \begin{tabular}{p{1.6cm} p{6.2cm} p{4.2cm} p{0.95cm}}
    2020-- & \textbf{Graduate Teaching Fellowship} & University of Texas at Austin &\\
    2025 & \textbf{PhD Summer Research Fellowship} & University of Texas at Austin & \$5,000\\
    2025 & \textbf{Empirical Macro Economics Policy \newline Center of Texas Dissertation Funding} & University of Texas at Austin & \$1,919\\
    2024 & \textbf{PhD Summer Research Fellowship} & University of Texas at Austin & \$5,000\\
    2023 & \textbf{PhD Summer Research Fellowship} & University of Texas at Austin & \$3,000\\
    2017 & \textbf{Distinction in Economics Senior Exercise} & Pomona College &\\
    2016 & \textbf{Harry G. Steele Scholarship} & Pomona College & \$4,000\\
    2014--2015 & \textbf{Pomona College Scholar} & Pomona College &\\
    2013 & \textbf{Flextronics Texas Scholarship} & Pomona College & \$1,000
  \end{tabular}

  \section{Service}
  \begin{tabular}{l p{13.8cm}}
    External & \href{https://paulletran.com/econ-grad-app-deadlines/}{https://paulletran.com/econ-grad-app-deadlines/} Creator and Maintainer (2019--)
  \end{tabular}

  \section{Miscellaneous Information}
  \begin{compactitem}\parskip = 0cm
    \item \textbf{Programming:} Matlab, Python, Bash, SAS, \href{https://en.wikipedia.org/wiki/FAME_(database)}{FAME}, (P)SQL, R, Stata, EViews, \LaTeX
    \item \textbf{Front-end Development:} Vanilla HTML, CSS, JS, Jekyll
    \item \textbf{Applications:} Visual Studio Code, Emacs, Git, Sublime Text, RStudio, Tableau, Microsoft Office
    \item \textbf{Operating Systems:} Unix, Linux, Windows
    \item \textbf{Languages:} English (native), Vietnamese (native)
  \end{compactitem}
\end{document}
```

* `\maketitle` after `\begin{document}` inserts the header box into the LaTeX
document. Afterwards, the rest of the .tex file outputs a typical LaTeX document
with `\section` commands.
* Sections that may have many columns with detailed information, such as
"Education" and "Teaching history" in my own CV, are structured as tabular
environments with the columns specified as paragraphs. This configuration allows
for flexible management of the column widths in order to prevent horizontal
overflow and crashing into the margins.
* To insert publications into the document, use the `\begin{publications}` environment.
  * Each `\printbib` command will insert a subsection that contains all
  publications in that category, in chronological and descending order, and
  sorted by name within each year.
    * Sorting specifics can be modified within the [biblatex](https://ctan.org/pkg/biblatex)
    package options in the .sty file.
  * The .sty file has options to display certain .bib entries, such as "abstract".
  This is especially useful for academics in the economics field, as displaying the
  abstract of your job market paper saves the search committees a lot of time when
  reviewing your application. There are also other customisations on how your .bib
  entries will output into the CV.

    ```latex
      %% Showing abstracts for biblatex entries (useful for JMCs IMO. Less useful when finished with the job market and can turn off to save space)
      \renewbibmacro*{finentry}{
        \setunit{\finentrypunct\par}
        \usebibmacro{abstract}
        \finentry
      }
    ```

  * The total number of publication items (e.g., refereed and working papers)
  listed inside the `publications` environment is calculated, converted into an
  integer, and displayed in the CV using the `fmtcount` package. The page
  numbers for the publications section are also stored inside of the `\printbib`
  command with the labels `\label{pubitemsstart}` and `\label{pubitemsend}`.
  These allow you to output them in the CV using the `\pageref` command. All of
  these configurations can be found inside of the .sty file.
  * You're allowed to have `\printbib` commands outside the `publications`
  environment, but the associated .bib items will not be counted towards the
  total number of publications.

    ```latex
      %% Creating publications environment
      \newenvironment{publications}{
        %% Creating label for the beginning of the publications environment for \pageref usage
        \label{pubitemsstart}
        \vspace*{0cm}
        \titlespacing{\section}{0pt}{1.5ex}{1ex}\itemsep = 0.00cm
      }{
        %% Creating label for the end of the publications environment for \pageref usage
        \label{pubitemsend}
        \addtocounter{sumpapers}{-1}
        \refstepcounter{sumpapers}
        \label{sumpapers}
      }
      \def\printbib#1{
        \printbibliography[category = #1, heading = #1]\lastref{sumpapers}
      }

      %% Counting total number of items included in the publications environment
      %% Sumpapers will naturally count everything contained inside of the publications environment. However, if you include categories
      %% inside of the environment that you don't want to be included into the sumpapers value, the following comments provide guidance on
      %% how to adjust the variable to display the value you want. As a reminder, .bib items added after and outside of the publications
      %% environment do not get added into the total value of sumpapers.
      %% Initialising the counter for pubitems to be 0.
      \newcounter{pubitems}\setcounter{pubitems}{0}

      %% Initialising the counter for total value sumpapers to be 0.
      %% If you want to remove x publication items from being included in the total value of sumpapers, simply replace 0 with -x.
      \newcounter{sumpapers}\setcounter{sumpapers}{0}

      %% Defining sumpapers to be the sum of the sub-totals of pubitems in every category listed inside of the publications environment.
      \def\lastref#1{
        \addtocounter{#1}{
          \value{pubitems}
        }
        \setcounter{pubitems}{0}
      }

      %% Add all papers in the bib files
      \nocite{*}
    ```

## Download

Feel free to take a look at the [.tex file here](https://raw.githubusercontent.com/paultran47/latex-cv-with-biblatex/master/tran_paul_le_cv.tex),
the [.sty file here](https://raw.githubusercontent.com/paultran47/latex-cv-with-biblatex/master/tran_paul_le_cv.sty),
my [personal CV](https://paulletran.com/cv/tran_paul_le_cv.pdf)
as an example, and the [GitHub repo](https://github.com/paultran47/latex-cv-with-biblatex)
for the source code (also found by the buttons at the top of this website).

## Closing note

If you want to find out more about me and my research, please visit my
[personal website](https://paulletran.com). You can also find my research on
[my Google Scholar profile](https://scholar.google.com/citations?user=0zKxrWgAAAAJ),
[my SSRN profile](https://papers.ssrn.com/sol3/cf_dev/AbsByAuth.cfm?per_id=7065188),
[my GitHub profile](https://github.com/paultran47), and my ORCID (0009-0000-8559-7915).
