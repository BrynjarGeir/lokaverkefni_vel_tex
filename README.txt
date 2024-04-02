UoI MSc thesis template (English) V2.0.3 25.4.2022

https://gitlab.com/uice/thesistemplate

This version is based on an earlier template that was once available
on a SENS UGLA page where the author and license are unknown.  But
that version has obviously been put once online with the intend to be
used by students, so providing and using it should not be problem.

Starting from 2017, Helmut Neukirchen https://uni.hi.is/helmut updated
that earlier template and for the new 2021 desin, Helmut used a
tikzpicture-based approach for the title page created by
Þór Arnar Curtis 2022.

In summary, the license situation is unclear, but it can for sure be
used to create student theses and publish them.

The included banner with the University of Iceland logo is very likely
copyrighted by the University of Iceland, but
https://zeroheight.com/1b323cfd9/p/20f1e6-theses/b/29a61a
states that that document is intended to make it easier for students,
staff and print-shops to format the thesis and ensure a standardised
appearance. So providing them here and using them should be legal.


If you started with the template based on the <2021 HÍ design: this
template is based on the old template, i.e. simply paste your own text
followinf the \tableofcontents command (and adjust any extra packages
that you added and extra settings that you made in the LaTeX preamble)
and then, it should work.

But \thesistutors has been changed to \thesissupervisors
and \thesisnrofsupervisors to \thesisnrofsupervisors, so you need to adjust this!


What still needs to be done (volunteers please contact
Helmut https://uni.hi.is/helmut ):

- Instead of the bitmap HÍ logo, create a vector graphic version:
  you should be able to get an SVG or PDF from here:
  https://honnun.hi.is/5afb7ec03/p/191b65-myndmerki-h/b/620f36

- Create an Icelandic version (load the PDF from
  https://zeroheight.com/1b323cfd9/p/20f1e6-theses/b/29a61a into Gimp
  using a high-resolution to create a bitmap and cut the title banner
  from there, respecting the black cut marks that show what needs be cut
  away) and translate the hardcoded English strings.

- For the title page, the font Jost from
  https://honnun.hi.is/5afb7ec03/p/2645bd-letur/b/357a78
  could be used. But there seems to be a LaTeX issue:
  https://github.com/wspr/fontspec/issues/437


Changelog of Helmut Neukirchen's modification (in comparison to the
original pre-2017 version):

- \thesistutors has been changed to \thesissupervisors and
  \thesisnrofsupervisors to \thesisnrofsupervisors

- Used \ifx to ommit printing supervisor part or committee part if the
  names are empty.

- Changed font from the default (Computer Modern) to Latin Modern
  (Latin Modern is a Vector Font, whereas Computer Modern typically
  leads to a bitmap font being included in the generate PDF).

- Removed usage of ucs package (and changed inputencoding from utf8x
  to utf -- as it would again lead to using ucs) because the ucs
  package conflicts with a lot of other packages (and you rarely need
  characters that are only supported by ucs/utf8x, but not by utf8).

- Changed term "Faculty Representative" to "External Examiner".

- Added \hypersetup{pageanchor=...} to disable PDF page anchors
  (i.e. those shown by a PDF viewer as a table of contents) for the
  title page (which would otherwhise leads to pdflatex warnings).

- Added example for acronym package in "Abbrevations" chapter.

- Use BibLaTeX instead of Natbib (and added a sample *.bib file). If
  you run LaTeX locally on the command line, then you need to run
  first
    pdflatex MSc.tex
  then
    biber MSc
  (without the .tex), and then again
    pdflatex MSc.tex.
  (Overleaf does all this automatically for you.)

- Added example of using \ref for figures and chapters/sections.

- Fixed page headings for Abbreviations chapter to make them correct
  when the Abbreviations chapter covers more than one page.

- Title page is now tikz-based (thank to Þór Arnar) and used \vspace
  \stretch instead of vspace with hardcoded cm.

- Removed the word "Dedication" on the optional dedication page.


Note that the official 2021 HÍ corporate design https://honnun.hi.is
PDF template and Microsoft Word template contradict themselves
and Helmut tried to make a good compromise in this LaTeX template: 

- The PDF template uses on the front page blue text only,
whereas the Word template uses also black text.
(Helmut decided to use in this LaTeX template uses also black.)

- While, the Word template has, e.g. supervisor info on the cover
title page, this information does in Helmut's opponion not belong
there. (The PDF template has neither this information. Therefore, this
LaTeX template has this only on the inner title plage.)

- The Word template has no cover title verso page (i.e. the back of
the cover): this makes no sense at all: if you go to a printshop, they
will ignore your A4 cover page and create their own cover page (in A3
so that they can bind it around your thesis) with an empty cover verso
page. (This LaTeX template, therefore has an empty cover title verso
page to make the generated PDF look like the versions that a printshop
would create. However, this LaTeX template is no back cover page.)

Visit https://uni.hi.is/helmut?s=latex to check for updated versions
of this template.


Helmut Neukirchen
https://uni.hi.is/helmut
