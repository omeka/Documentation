Omeka Documentation
===================

This is the developer documentation for Omeka. If you're looking to improve
the documentation or see how it works, you're in the right place. Otherwise,
you can see a human-readable and up-to-date version of the docs at [our
Read the Docs site](http://omeka.readthedocs.org).

Working on the documentation
----------------------------

This documentation uses the [Sphinx](http://sphinx-doc.org) documentation
generator, which runs in Python. The source files for each page are written
in [reStructuredText](http://docutils.sourceforge.net/rst.html), a wiki-like
markup syntax.

### Requirements

Since the files are pretty much all plain text, you can edit the
documentation with any text editor, or even directly through GitHub. But,
to see your changes as HTML, you'll need to *build* the docs, and for that
you'll need a few things:

 * The whole system runs on Python, so you'll obviously need that. A
   simple way to get the other packages you need is with `easy_install`,
   which is part of the `setuptools` package. On most systems, you'll
   probably already have these.
 * Sphinx: `easy_install -U Sphinx`
 * sphinxcontrib-phpdomain: `easy_install -U sphinxcontrib-phpdomain`
 * pygments-style-solarized: `easy_install -U pygments-style-solarized`

### Building

Once you've got the tools you need installed, building the documentation is easy: just run `make html` in the top-level documentation folder (where the `Makefile` is). That will spit out HTML sources for the docs under a folder called `build`.
