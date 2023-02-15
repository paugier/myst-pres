# A MyST to presentation converter

Warning: currently this repository only contains notes on a tool that I (Pierre
Augier) would like to have.

## Notes on the project

### Why a MyST to presentation converter?

I would like to write my presentations in MyST markdown (1 .myst.md file + 1
.css file for 1 presentation). There are already markdown to presentation
converters (in particular [markdown-to-presentation] and [Marp]/[Marpit]), but
they do not support MyST markdown and notebooks. [nbconvert] can also convert a
notebook (`.ipynb` file) to a [reveal.js] presentation, but it does not support
MyST syntax.

[reveal.js]: https://revealjs.com/
[markdown-to-presentation]: https://github.com/anthonywritescode/markdown-to-presentation
[Marp]: https://marp.app/
[Marpit]: https://marpit.marp.app/
[nbconvert]: https://nbconvert.readthedocs.io
[Quarto]: https://quarto.org

Simple markdown is a bit too limited to express what is needed for a good
presentation (for example 2 columns layout, movies, images with added texts on
it, etc.). One can use html to express more advanced things but it is not
possible to mix html and markdown. I feel that MyST could be a great solution.

With MyST markdown, we have syntaxes to express what is needed for a good
presentation and moreover we can represent the input of a Jupyter notebook
(with executable cells).

[Quarto] (built on [Pandoc]) is very close to what I'd like and many things can
be expressed with their Markdown flavor (see
https://quarto.org/docs/presentations/revealjs/)!

[Pandoc]: https://pandoc.org

### Objectives

We'd like to have something similar to
https://quarto.org/docs/presentations/revealjs, but dependencies instalable
with `pip` and with nice MyST syntaxes.

One can also have a look at the [Marp] syntax for inspiration.

#### Basics

- [reveal.js] slides and fragments (no subslides)
- exportable in pdf for offline presentations
- good default CSS and easily extendable (in particular with one .css file)
- `myst2pres-monitor` command
- columns, images, subimages, ...

#### Later

- ability to add text and images on an image
- executable cells with ability to hide/show input and/or output

### Notes on the implementation

It would be convenient not to depend on NodeJS nor Sphinx.

We have [jupytext] and [jupyter-cache] for converted to and caching a notebook.

[jupytext]: https://jupytext.readthedocs.io
[jupyter-cache]: https://jupyter-cache.readthedocs.io

[nbconvert] has an advanced Jinja template system.

[markdown-to-presentation] uses `.scss` and [libsass].

[libsass]: https://pypi.org/project/libsass/

### Related Github issues

- [nbconvert MyST compatibility](https://github.com/jupyter/nbconvert/issues/1806)

- [myst and jupyter-nbconvert --to slides](https://github.com/orgs/executablebooks/discussions/772)

- [CSS for MyST outside of jupyter-book?](https://github.com/orgs/executablebooks/discussions/823)