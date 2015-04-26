# Introduction

This repo provides a starting point for a slide deck based on [deck.js](http://imakewebthings.com/deck.js/ "deck.js"). It includes the following:

* Core deck.js files including the Swiss theme ([stable branch](https://github.com/imakewebthings/deck.js/tree/latest "imakewebthings/deck.js at latest") as of 2015-04-26)
* deck.menu extension
* [SyntaxHighlighter](http://alexgorbatchev.com/SyntaxHighlighter/ "SyntaxHighlighter") library (3.0.9) with the default [theme](http://alexgorbatchev.com/SyntaxHighlighter/manual/themes/ "SyntaxHighlighter - Themes") and PHP and XML [brushes](http://alexgorbatchev.com/SyntaxHighlighter/manual/brushes/ "SyntaxHighlighter - Brushes")

Like deck.js itself, this project is licensed under the [MIT License](http://www.opensource.org/licenses/mit-license.php "Open Source Initiative OSI - The MIT License").

# Basic Setup

Open `index.html` in your preferred text editor. Update the `title` tag value and `meta` tag attribute values at the top. Scroll down to within the `body` tag and find the `div` tag with the `id` attribute value of `title-slide`. Within that `div` tag, update the `h1` and `h2` tags.

At this point, you can open `index.html` in a browser and see your title slide. If you want to add any custom CSS, you can do it in `css/deck.custom.css`. It's already included by `index.html`. The same applies to `js/deck.custom.js` for custom JS. `index.html` also includes the version of [jQuery](http://jquery.com "jQuery") bundled with deck.js (currently 1.10.2) as well as the SyntaxHighlighter library.

To create new slides, copy and paste the `div` block below the one for the title slide (it has `id="new-slide"`), change the `div` tag `id` attribute value and the `h2` tag value, and add your content. See the [deck.js introduction](http://imakewebthings.com/deck.js/introduction/ "Getting Started with deck.js") for more information on how to format slide markup. You can use SyntaxHighlighter to [add source code highlighting](http://alexgorbatchev.com/SyntaxHighlighter/manual/installation.html#pre__method "SyntaxHighlighter - Installation").

I typically create an `img` directory on the same level as the `css` and `js` directories and store any image files there, then reference them using relative paths as in the example below. You'll have to create the directory yourself as git doesn't support tracking empty directories.

    <img src="img/filename.png">

# Customization

Here are a few things you can do to tailor this base to your liking:

* Change the deck.js [theme or transition](https://github.com/imakewebthings/deck.js/tree/stable/themes "makewebthings/deck.js at stable")
* Remove or add deck.js extensions
* Change the SyntaxHighlighter [theme](http://alexgorbatchev.com/SyntaxHighlighter/manual/themes/ "SyntaxHighlighter - Themes") or [brushes](http://alexgorbatchev.com/SyntaxHighlighter/manual/brushes/ "SyntaxHighlighter - Brushes")
* Hack in some custom JS - the [deck.js docs](http://imakewebthings.com/deck.js/docs/ "Docs - deck.js") might be handy for this
* Try upgrading dependencies, like [Modernizr](http://www.modernizr.com/ "Modernizr") or [jQuery](http://jquery.com "jQuery") - this could break things, so back up the current versions first

If this project gets behind the current stable branch of [deck.js](https://github.com/imakewebthings/deck.js "imakewebthings/deck.js"), just clone the deck.js repo, check out the stable branch, and update the relevant files:

```bash
cp deck.js/core/deck.core.css deck.js-base/css/deck.core.css
cp deck.js/extensions/menu/deck.menu.css deck.js-base/css/extensions/deck.menu.css
cp deck.js/themes/style/swiss.css deck.js-base/css/style/swiss.css
cp deck.js/themes/transition/horizontal-slide.css deck.js-base/css/transition/horizontal-slide.css
cp deck.js/modernizr.custom.js deck.js-base/js/modernizr.custom.js
cp deck.js/jquery.min.js deck.js-base/js/jquery.min.js
cp deck.js/core/deck.core.js deck.js-base/js/deck.core.js
cp deck.js/extensions/menu/deck.menu.js deck.js-base/js/extensions/deck.menu.js
```

To update [SyntaxHighlighter](https://github.com/syntaxhighlighter/syntaxhighlighter "syntaxhighlighter/syntaxhighlighter"):

1. [Install SASS](http://sass-lang.com/install)
2. Either clone the git repo or download and decompress the archive:

    ```bash
    # Either:
    git clone git@github.com:syntaxhighlighter/syntaxhighlighter.git
    cd syntaxhighlighter
    git checkout v3.0.9
    # or:
    wget -c https://github.com/syntaxhighlighter/syntaxhighlighter/archive/v3.0.9.zip
    unzip v3.0.9.zip
    mv syntaxhighlighter-3.0.9 syntaxhighlighter
    ```

3. Compile the core stylesheet and copy the JS files:

    ```bash
    sass syntaxhighlighter/src/sass/shCoreDefault.scss deck.js-base/js/sh/shCoreDefault.css
    cp syntaxhighlighter/src/js/shCore.js deck.js-base/js/sh/shCore.js
    cp syntaxhighlighter/src/js/shBrushPhp.js deck.js-base/js/sh/shBrushPhp.js
    cp syntaxhighlighter/src/js/shBrushXml.js deck.js-base/js/sh/shBrushXml.js
    ```

# Contributing

I'm certainly open to improving this deck.js base. If you have suggestions, feel free to message me on GitHub or send me a pull request. Thanks in advance for your contribution.
