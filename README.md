# Creating `beamer` presentations from Markdown using `pandoc`

## Requirements

* Installed pandoc
* Installed LaTeX distribution
* Markdown document for the presentations

## Good to have 

* A good markdown editor
* A pdf viewer with automatic reload capabilities
* Some type of versioning method, e.g. `git` plays nicely with markdown!
* Know your desired [beamer theme](https://hartwork.org/beamer-theme-matrix/)
    - Note: the `jlug` beamer theme is specific for the [Justus-Liebig-University Giessen](http://www.uni-giessen.de/index.html) and may not be used by non-members.

## How to use

1. Write your markdown file [1] and save it, see the template [slides.md](./slides.md).
2. Convert the slides to a pdf using the command in the command line / shell:\
    ``` pandoc -t beamer slides.md -o ../slides.pdf ```
3. Open the [slides.pdf](./slides.pdf) and enjoy.

### Customisation

* Using a different beamer (theme) and `xelatex`:\
    ``` pandoc -t beamer slides.md -V theme:(theme) --pdf-engine=xelatex -o slides.pdf ```
* Using the `jlug` theme (a bit hacky currently):
    1. Navigate into the folder [theme/](./theme/)
    2. ``` pandoc -t beamer ../slides.md -V theme:jlug --pdf-engine=xelatex -o ../slides.pdf ```

## Ressources used for this project

* [1] See [Producing slide shows with pandoc](http://pandoc.org/MANUAL.html#producing-slide-shows-with-pandoc) for available options
* [2] [Building pretty slides using Markdown and pandoc](https://avalz.it/2017/02/01/build-pretty-slides/)  by AvalZ 
* [3] [Talks with LaTeX Beamer, written in Markdown](https://nval.andreasherten.de/2016/01/26/latex-beamer-with-markdown.html) by Andreas Herten
* [4] [Better-looking LaTeX/Beamer slides](https://kbroman.wordpress.com/2013/10/07/better-looking-latexbeamer-slides/) by Karls Borman