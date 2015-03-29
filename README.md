## Photog!

Photog! turns a directory tree of source images into a photography
website with nested albums of chronologically sorted photographs. It
is created by [Jaap Joris Vens](http://rtts.eu/about/) who uses it for
[his personal photography website](http://www.superformosa.nl/).

## Installation

### Prerequisites

* [ImageMagick](http://imagemagick.org/): It's best to install this
  using your operating systems package manager, e.g.,
  `[apt-get|yum|brew|pacman|apt-cyg] install imagemagick`.

* [Cpanminus](https://github.com/miyagawa/cpanminus): This is [the
  recommended way](http://www.cpan.org/modules/INSTALL.html) to
  install Perl modules. An easy way to install it is to run `curl -L
  https://cpanmin.us | perl - --sudo App::cpanminus` (or just use your
  OS package manager again).

* [local::lib](search.cpan.org/perldoc/local::lib): Only needed if you
  want to install Photog! without requiring root permissions. Make
  sure to include `eval "$(perl -Mlocal::lib)"` into your `.bashrc`
  after installation.

### Installation - the easy way

    $ cpanm https://github.com/rtts/photog/archive/stable.tar.gz

This will fetch and build all dependencies and install Photog! to your
`$HOME/perl5` directory. To install Photog! system-wide, prepend `sudo` to
the above command.

### Installation - the old-fashioned way

    $ perl Makefile.PL
    $ make
    $ sudo make install

This works like you'd expect, but beware that you'll have to install
all the dependencies yourself.

### Installation - using Dist::Zilla

This module is maintained using [Dist::Zilla](http://dzil.org/), which
builds the module distributions and pushes them to the 'releases'
branch. Dist::Zilla can also be used for installing the module from
the original source code (which lives in the 'master' branch):

    $ git clone https://github.com/rtts/photog.git
    $ git checkout master
    $ dzil install

## Running Photog!

After installation, a manpage is available with the following command:

    man photog

To generate a photography website using default settings, simply `cd`
to your Pictures directory and execute `photog` with the destination
directory as its argument:

    cd ~/Pictures
    photog ~/public_html
