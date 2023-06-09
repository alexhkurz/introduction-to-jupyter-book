# Introduction to Jupyter Books

This README describes how to create [this book template](https://alexhkurz.github.io/introduction-to-jupyter-book). Based on the tutorial [Create your first book](https://jupyterbook.org/en/stable/start/your-first-book.html), the following steps were taken.

### Basics

```
pip install -U jupyter-book
jupyter-book create introduction-to-jupyter-book
cd introduction-to-jupyter-book
```

To build the book run

```
jupyter-book build .
```

or also `jb build .`.

The book can now be opened in a browser by opening the file `_build/html/index.html`. On a mac, simply run `open _build/html/index.html`

To work with [Math and equations](https://jupyterbook.org/en/stable/content/math.html#math-and-equations), add to `_config.yml`

```
parse:
  myst_enable_extensions:
    # don't forget to list any other extensions you want enabled,
    # including those that are enabled by default!
    - amsmath
    - dollarmath
```

Adapt `_config.yml` and `_toc.yml`. Add your own files. Go through several iterations of 

```
jupyter-book build . ; open _build/html/index.html
```

### Creating a Repository

Downloading a `.gitignore` helps to avoid committing unnecessary (eg machine generated) files to git:

```
curl https://raw.githubusercontent.com/executablebooks/jupyter-book/master/.gitignore > .gitignore
```

To set up git locally run

```
git init
git branch -m main
git add *
git commit -m "initial commit"
```

To create a repo in the cloud go to a git server such as [Github](https://github.com/). 

Create an empty public repository at Github. Then run locally:

```
git remote add origin https://github.com/alexhkurz/introduction-to-jupyter-book.git
git push -u origin main
```

Since then the files are available at [`https://github.com/alexhkurz/introduction-to-jupyter-book`](https://github.com/alexhkurz/introduction-to-jupyter-book).


### Publishing

Following [Publish your book online](https://jupyterbook.org/en/stable/start/publish.html) install `ghp-import`

```
pip install ghp-import
```

and then publish the book by running

```
ghp-import -n -p -f _build/html
```

This makes the book available online at 

[`https://alexhkurz.github.io/introduction-to-jupyter-book`](https://alexhkurz.github.io/introduction-to-jupyter-book) 

(possibly after some waiting time). It also keeps the source files in the `main`-branch separate from the files in `_build` in the `gh-pages` branch.

### Important Commands

If, for example, the table of contents in the left-hand pane behaves in a strange way, clean out `_build`:

```
jupyter-book clean .
```

### References

- [Create your first book](https://jupyterbook.org/en/stable/start/your-first-book.html).
- [Math and equations](https://jupyterbook.org/en/stable/content/math.html#math-and-equations).
- [.gitignore](https://raw.githubusercontent.com/executablebooks/jupyter-book/master/.gitignore).
- [Publish your book online](https://jupyterbook.org/en/stable/start/publish.html).
