Boilerplate with Compass
========================

This project is the basic boilerplate I use with Compass_, including some configuration I always do between projects.


Requirements
------------

Ruby is essential for Compass_ but other tools use Node.js_ (e.g. Bower_).

Ruby
^^^^
Install **Ruby** with the RVM (Ruby Version Manager) from `<https://rvm.io>`_::

    \curl -sSL https://get.rvm.io | bash -s stable


Node.js
^^^^^^^

Ubuntu_::

    sudo add-apt-repository ppa:chris-lea/node.js
    sudo apt-get update
    sudo apt-get install python-software-properties python g++ make nodejs


`Mac OS X`_ (using homebrew_)::

    brew install node


Bower.io
^^^^^^^^

With Node.js_ installed and npm_ (comes with node)::

    npm install -g bower


TL;DR: How do I set this up?
----------------------------

If you have all requirements, for each project using this boilerplate you start with something like::

    cd <project>    # this will setup the ruby version and gemset with rvm
    bundle install  # install all ruby dependencies (reads Gemfile)
    bower install   # install all front-end dependencies (reads bower.json)
    compass watch   # start watching sass files for modifications and compile css



But what are all these files?
-----------------------------

Ruby
^^^^

When you ``cd`` into your project's directory, RVM will try to use the version of Ruby defined in ``.ruby-version``. If you don't have that version, RVM will install it for you.

``.ruby-gemset`` should be unique for your project. It behaves much like Python's virtualenv, so any ruby gem (ruby packages) installed for your project will be isolated in it's own dir, which is prepended to ``$PATH``. Just like ``.ruby-version``, this activation is done automatically when you ``cd`` into your project.

``Gemfile`` works like PIP requirement files. It defines the ruby gems that need to be installed for your project. It's used by Bundler_, which comes with RVM.


Bower.io
^^^^^^^^

Bower_ is a package manager for front-end libraries. Again, it's like PIP but for jQuery, et all.

We use ``.bowerrc`` to specify where we want the packages to be installed.

``bower.json`` is like ``Gemfile`` and specifies the package requirements so we can install them with ``bower install``.

This is where we define dependencies like jQuery, Modernizr and Foundation.


Compass
^^^^^^^

Compass_ only has ``config.rb`` which is how we setup the project for compass. Compass is in ruby so it's installed with Bundler_ along with other dependencies.


HTML
^^^^

The ``templates/base.html`` is based on the `HTML5 Boilerplate`_, the web's most popular front-end template.


.. _Compass: http://compass-style.org
.. _Bower: http://bower.io
.. _Bundler: http://bundler.io
.. _Node.js: http://nodejs.org
.. _npm: https://npmjs.org
.. _Ubuntu: https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager#ubuntu-mint-elementary-os
.. _Mac OS X: https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager#osx
.. _homebrew: http://brew.sh
.. _HTML5 Boilerplate: http://html5boilerplate.com
