Raqm
====

[![Build](https://github.com/HOST-Oman/libraqm/actions/workflows/ci.yml/badge.svg?branch=master)](https://github.com/HOST-Oman/libraqm/actions)

Raqm is a small library that encapsulates the logic for complex text layout and
provides a convenient API.

It currently provides bidirectional text support (using [FriBiDi][1]), shaping
(using [HarfBuzz][2]), and proper script itemization. As a result,
Raqm can support most writing systems covered by Unicode.

The documentation can be accessed on the web at:
> http://host-oman.github.io/libraqm/

Raqm (Arabic: رَقْم) is writing, also number or digit and the Arabic word for
digital (رَقَمِيّ) shares the same root, so it is a play on “digital writing”.

Building
--------

Raqm depends on the following libraries:
* [FreeType][3]
* [HarfBuzz][2]
* [FriBiDi][1]

To build the documentation you will also need:
* [GTK-Doc][4]

To install dependencies on Fedora:

    sudo dnf install freetype-devel harfbuzz-devel fribidi-devel meson gtk-doc

To install dependencies on Ubuntu:

    sudo apt-get install libfreetype6-dev libharfbuzz-dev libfribidi-dev meson gtk-doc-tools

On Mac OS X you can use Homebrew:

    brew install freetype harfbuzz fribidi meson gtk-doc
    export XML_CATALOG_FILES="/usr/local/etc/xml/catalog" # for the docs

Once you have the source code and the dependencies, you can proceed to build.
To do that, run the customary sequence of commands in the source code
directory:

    $ meson build
    $ ninja -C build
    $ ninja -C build install

To build the documentation, pass `-Ddocs=enable` to the `meson`.

To run the tests:

    $ ninja -C test

Contributing
------------

Once you have made a change that you are happy with, contribute it back, we’ll
be happy to integrate it! Just fork the repository and make a pull request.

Projects using Raqm
-------------------

1. [ImageMagick](https://github.com/ImageMagick/ImageMagick)
2. [LibGD](https://github.com/libgd/libgd)
3. [FontView](https://github.com/googlei18n/fontview)
4. [Pillow](https://github.com/python-pillow)
5. [mplcairo](https://github.com/anntzer/mplcairo)

The following projects have patches to support complex text layout using Raqm:

2. SDL_ttf: https://bugzilla.libsdl.org/show_bug.cgi?id=3211
3. Pygame: https://bitbucket.org/pygame/pygame/pull-requests/52
4. Blender: https://developer.blender.org/D1809



[1]: http://fribidi.org
[2]: http://harfbuzz.org
[3]: https://www.freetype.org
[4]: https://www.gtk.org/gtk-doc
