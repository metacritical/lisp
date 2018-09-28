Interpretation of Lisp and scheme
=================================

This is the translation into Russian of the widely known in narrow circles Christian Kennek's book "Les Langages Lisp" (aka Lisp in Small Pieces ). The book deals with the basics of constructing Lisp interpreter and compilers (primarily its Scheme dialect), as well as a variety of options for understanding the semantics of its constructs and possibilities like environments, closures, exceptions, continuations, reflections and macros.

Ready assemblies
----------------

In the Gythkhab releases, pre-assembled versions are available:

  * lisp_a4.pdf - PDF for A4 format;
  * lisp- * pt.epub - reflowable EPUB with the appropriate font size.

On [Github Pages](http://ilammy.github.io/lisp/) hosted web-based version.


What is lying around
--------------------

| File              | Content                                                                    |
|-------------------|----------------------------------------------------------------------------|
| `build.*`         | build scripts                                                              |
| `makeindex.py`    | script that forms an index                                                 |
| `book-src/`       | the source text of the book; the contents of the files are self-evident    |
| `epub/`           | the source text of the book, the structure of the EPUB container, fonts    |
| `epub/fontconfig` | CSS with settings for different basic font sizes                           |
| `scm-src/`        | copy of the source code of the programs attached to the book               |


Assembly
--------

For assembly, pdfLaTeX and Python 2.7 are required. Run a simple script from the root directory `build.sh` or `build.bat` wait until LaTeX makes three passes through the text. Take it `lisp.pdf` from the root directory.

Python is needed to generate the index. Provide, please, the launch of the interpreter on command `python`.

Scripts do not install the necessary LaTeX packages. It is expected that they are either already available, or that your LaTeX distribution will automatically download them from CTAN when assembling the document.

The assembly was tested in Debian 7.0 (TeX Live) and Windows (MiKTeX 2.9). For Windows, you need to install MiKTeX, install CM-Super and PSCyr (0.4d-beta9) for it, the rest is automatically unloaded. For Debian, it's enough to do

    sudo aptitude install cm-super texlive-lang-english texlive-lang-french \
        texlive-lang-cyrillic texlive-latex-base texlive-latex-recommended  \
        texlive-latex-extra texlive-pictures

And install PSCyr manually.

Fonts from the PSCyr package are used only for letters and the title page, so if desired, this dependence can be easily disposed of without significant damage to quality. If there is no desire, then good luck with the installation:
  * PSCyr sources: ftp://scon155.phys.msu.su/pub/russian/psfonts/0.4d-beta
  * deb package: http://people.debian.org/~sgolovan/debian/pool/main/tex/tex-pscyr
  * installers for Windows I did not see, I write them myself and packages for LaTeX do not know how :(

### Build EPUB

To do this, Imagemagick and Ghostscript (for converting illustrations into PNG), and Info-ZIP (for packing the result into the EPUB container) are additionally required. For the assembly, call the scripts with the option `epub`. Take the pacha `lisp-*pt.epub` from the root directory.

The Imagemagick converter must be available on command `convert`. Info-ZIP - by command `zip`.

The assembly was tested in Debian 7.0 (Imagemagick 6.7.7, Ghostscript 9.05, Info-ZIP 3.0) and Windows (Imagemagick 6.8.7, Ghostscript 9.10, Info-ZIP 3.0).


----


### Contacts

The home page of Professor Kennek ([klac](http://pagesperso-systeme.lip6.fr/Christian.Queinnec/WWW/Queinnec.html)), his e-mail address: [Christian.Queinnec@lip6.fr](mailto:Christian.Queinnec@lip6.fr)

You `scm-src` can download the original source code from one archive [from here](http://pagesperso-systeme.lip6.fr/Christian.Queinnec/Books/LiSP-2ndEdition-2006Dec11.tgz).

If you are confused by GitHub or you are not able to find my personal email address and home address in Google, you can send complaints, threats and suggestions here: [lisp.in.small.pieces@gmail.com](mailto:lisp.in.small.pieces@gmail.com)


### Licensing and other riffraff

By agreement with the author of the book, this translation is distributed under the license [**CC BY-ND 3.0**](http://creativecommons.org/licenses/by-nd/3.0) (see the file  `LICENSE` with a copy).

So you can freely:

  * share , copy, distribute and share this work with others;;

  * use the work for commercial purposes.

With the obligatory observance of the following conditions:

  * "Attribution" — you must attribute the work, specifying in any convenient way the title of the book, the name of the author (Christian Kennek, Christian Queinnec), the name of the translator (ilammy), and also giving a link to this repository: [https://github.com/ilammy/lisp](https://github.com/ilammy/lisp).

  * "Without derivative works" — you can not change, transform or take as a basis this work.

Using the right to clarify the license, I personally do not consider foreknowledge works as the basis for correcting spelling, punctuation errors, fakapov in formulas and source codes, as well as other external flaws that do not affect the semantic content. And by this I give my permission (and even encourage their creation), provided that the relevant call-records are issued.

Naturally, derivative works also do not consider the translation of LaTeX sources into another format, reworking, repainting of illustrations and any design changes necessary to adequately transfer the contents of the book to another medium.

For permission to do anything else (shortening, translation, creating comic books based on motives, etc.), please contact the author of the book; he does not bite, his email is a little higher. Personally, I'm not against any use, but I do not have the right to decide this myself.

CC BY-ND also applies exclusively to the contents of the book: text and illustrations, as well as a file with the text of the license. LaTeX macros are by themselves, `makeindex.py` and everything else that does not directly relate to the content of the book is distributed on [WTFPL](http://www.wtfpl.net/) terms (read: it is in the public domain).

The source codes of the programs that are in `scm-src` and given in the text of the book are subject to the conditions described in `scm-src/README`. The directory `scm-src` is a mirror of the [original sources](http://pagesperso-systeme.lip6.fr/Christian.Queinnec/Books/LiSP-2ndEdition-2006Dec11.tgz), made solely for the sake of convenience. No changes were made to it.
