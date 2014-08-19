
## Omni Markup Preview

-----

Description
-----------

OmniMarkupPreviewer is a plugin for both [Sublime Text 2] and [Sublime Text 3]
that preview markups in web browsers. OmniMarkupPreviewer renders markups into
htmls and send it to web browser in the backgound, which enables a live preview.
Besides, OmniMarkupPreviewer provide support for exporting result to
html file as well.

[Sublime Text 2]: http://www.sublimetext.com/2
[Sublime Text 3]: http://www.sublimetext.com/3

OmniMarkupPreviewer has builtin support following markups:

* [Markdown](http://daringfireball.net/projects/markdown/)
* [reStructuredText](http://docutils.sourceforge.net/rst.html)
* [WikiCreole](http://wikicreole.org/)
* [Textile](http://www.textism.com/tools/textile/)
* [Pod](http://search.cpan.org/dist/perl/pod/perlpod.pod) (Requires Perl >= `5.10`
  and can be found in `PATH`, if the perl version < `5.10`, `Pod::Simple` should be
  installed from `CPAN`.)
* [RDoc](http://rdoc.sourceforge.net/) (Requires `ruby` in your `PATH`)
* [Org Mode](http://orgmode.org) (Requires `ruby`, and gem `org-ruby` should be installed)
* [MediaWiki](http://www.mediawiki.org/) (Requires `ruby`, as well as gem `wikicloth`)
* [AsciiDoc](http://www.methods.co.nz/asciidoc/) (Requires `ruby`, as well as gem `asciidoctor`)
* Literate Haskell


## Installing Package

Go <kbd>Preferences > Package-Control > Install Package > OmniMarkupPreviewer</kbd>

Run auto markdown preview with <b>[ctrl+alt+o]</b> shortcuts.