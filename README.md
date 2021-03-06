CRM114.rb: CRM114 Controllable Regex Mutilator for Ruby
=======================================================

This is a Ruby interface to the CRM114 Controllable Regex Mutilator, an
advanced and fast text classifier that uses sparse binary polynomial
matching with a Bayesian Chain Rule evaluator and a hidden Markov model to
categorize data with up to a 99.87% accuracy.

* <http://crm114.rubyforge.org/>
* <http://github.com/bendiken/crm114>
* <http://ar.to/2006/07/spam-filters-alien-technology-and-ruby-on-rails>

### About CRM114

* <http://crm114.sourceforge.net/>
* <http://en.wikipedia.org/wiki/CRM114>
* <http://en.wikipedia.org/wiki/Dr_Strangelove>
* <http://www.paulgraham.com/wsy.html>

Usage
-----

The CRM114 library interface is very similar to that of the
[Classifier](http://rubyforge.org/projects/classifier) project.

Here follows a brief example:

    require 'crm114'

    crm = Classifier::CRM114.new([:interesting, :boring])

    crm.train! :interesting, 'Some data set with a decent signal to noise ratio.'
    crm.train! :boring, 'Pig latin, as in lorem ipsum dolor sit amet.'

    crm.classify 'Lorem ipsum'       => [:boring, 0.99]
    crm.interesting? 'Lorem ipsum'   => false
    crm.boring? 'Lorem ipsum'        => true

Have a look at the included unit tests for more comprehensive examples.

Dependencies
------------

Requires the CRM114 binaries to be installed. Specifically, the `crm` binary
should be accessible in the current user's `PATH` environment variable.

Download
--------

To get a local working copy of the development repository, do:

    % git clone git://github.com/bendiken/crm114.git

Alternatively, you can download the latest development version as a tarball
as follows:

    % wget http://github.com/bendiken/crm114/tarball/master

Installation
------------

The recommended installation method is via RubyGems. To install the latest
official release from Gemcutter, do:

    % [sudo] gem install crm114

Resources
---------

* <http://gemcutter.org/gems/crm114>
* <http://rubyforge.org/projects/crm114>
* <http://raa.ruby-lang.org/project/crm114/>
* <http://www.ohloh.net/p/crm114-ruby>
* <http://www.elegantchaos.com/node/129> (crm.py)
* <http://rubyforge.org/projects/classifier>
* <http://rubyforge.org/projects/bishop>

Author
------

* [Arto Bendiken](mailto:arto.bendiken@gmail.com) - <http://ar.to/>

License
-------

CRM114.rb is free and unencumbered public domain software. For more
information, see <http://unlicense.org/> or the accompanying UNLICENSE file.
