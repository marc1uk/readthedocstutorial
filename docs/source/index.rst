ReadTheDocs
==============
Building A Website
------------------
ReadTheDocs provides a **framework** for easily building websites from a set of files. Its configuration is simple, with global project options confiugred in a simple web browser dash page, and version-specific options defined by a handful of config files. Sourcefiles defining web pages reside in a github repository, and will be used by the framework to build appropriate html (and/or .pdf or .mobi documentation), which will be hosted by default at yourproject.readthedocs.io <https://yourproject.readthedocs.io/>.
Builds can be triggered either manually from the dash or automatically on github PRs, generating a preview website that can be checked prior to merging.
Branching of the source repository allows multiple documentation versions to be retained and selectable by users from the web site.
Overall, the framework seems simple to configure and provides everything I would imagine we'd need. But, it is just a framework; the real issue is how web pages are defined.

Defining Web Pages
-------------------
Web pages themselves may be written either using the **MkDocs** or **Sphynx** language - either or, not both.
**MkDocs** is a simple, mostly mark-down based language sufficient for simple pages, with support for things like a table of contents, section headers, links, code blocks, simple tables and images. More functionality is available via extensions.

**Sphynx** is the default ReadTheDocs language and provides a much more extensive feature set, while retaining an equivalent level of simplicity and human readability for simple content. It's an extended version of 'reStructuredText'<https://docutils.sourceforge.io/rst.html>; which is not *technically* Markdown, but is practically the same thing.
Initially developed for documenting the Python language and later extended for c++ and javascript, Sphynx provides extensive features for describing programming objects; simple structures that render page elements for describing classes, functions, argument lists, types and so on. It also provides many other useful elements and features such as:
* line-numbering and syntax highlighting on code blocks
* version changed notes
* deprecation warnings
* 'see also' hints
* named references to make linking easier
* embedding of code from an actual sourcefiles in the repository, for larger reference code sections
* latex expressions

While I still believe a full documentation of class APIs to be the domain of Doxygen, the ability to clearly reference programming elements within a more readable format seems extremely useful.
The API is ... well documented, although the documentation suffers from excessive use of jargon, reading rather like word-salad to a novice. Examples and templates would go a long way to helping make it more accessible.

A starting point for writing simple reStructuredText is here <https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html>
A starting point for looking up more complex elements is this page <https://www.sphinx-doc.org/en/master/usage/restructuredtext/index.html>.
For some example pages (presently very primitive but would be good to extend in the future), check out the :doc:`usage` section for further information, including
how to :ref:`installation` the project.


.. note::

   This project is under active development.

Contents
--------
Whereas MkDocs generates a table of contents based on source file hierarchy, Sphynx requires it to be defined in the main index page by a 'toctree' object.

.. toctree::

   examples: usage
   reference: api
