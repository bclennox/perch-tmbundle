Perch TextMate Bundle
=====================

Snippets and grammar for the [Perch content management system](http://grabaperch.com/).

Installation
------------

In your terminal:

    mkdir -p "$HOME/Library/Application Support/TextMate/Bundles"
    cd "$HOME/Library/Application Support/TextMate/Bundles"
    git clone git://github.com/bclennox/perch-tmbundle.git Perch.tmbundle

You also need to update the HTML bundle's grammar:

    # somewhere around line 184
    repository = {
      embedded-code = {
        patterns = (
          {	include = '#ruby'; },
          {	include = '#php'; },
          {	include = '#smarty'; },
          {	include = '#python'; },
          { include = '#perch'; },    # add this line...
        );
      };
      
      # ...and this line
      perch = { patterns = ( { include = 'text.xml.perch'; } ); };
    }

Then choose `Bundles > Bundle Editor > Reload Bundles`.

Snippets
--------

* `perch`: Call to `perch_content()`
* `percht`: Template tag for a text field
* `perchb`: Template tag for a text block
* `perchi`: Template tag for an image
* `perchii`: HTML `<img>` tag with `src` and `alt` attributes created as appropriate template tags
* `perchf`: Template tag for a file upload
* `perchff`: HTML `<a>` tag with `href` attribute and inner HTML created as appropriate template tags
* `perchs`: Template tag for a `<select>` element
* `perchd`: Template tag for a date selector

Todo
----

* Smarter regexps in the grammar might make it possible to switch the scope to `text.html` within block-level Perch elements (like `<perch:if>`)

Credits
-------

Inspired by [Ad Taylor](http://www.iamadtaylor.com/a-perch-textmate-bundle/)

License
-------

See COPYING.
