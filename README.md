Tor Browser Launcher
====================
Tor Browser Launcher is intended to make the Tor Browser Bundle (TBB) easier to
maintain and use for GNU/Linux users. You install ```torbrowser-launcher``` from your
distribution's package manager and it handles everything else, including:

* Downloading the most recent version of TBB for you, in your language and for
  your architecture
* Automatically updating (while preserving your bookmarks and preferences)
* Verifying the TBB's [GnuPG signature](http://www.gnupg.org/gph/en/manual/x135.html)
* Adding a "Tor Browser" application launcher to your desktop environment's menu

Tor Browser Launcher isn't in any Debian repositories yet, but it will be soon.

Quick Start
-----------

If you're using a Debian-based distro like Debian, Ubuntu, or Linux Mint, the
following instructions will install dependencies, clone this repo, build a .deb, and
install it with dpkg.

    sudo apt-get install python-stdeb python-gtk2 python-psutil python-twisted python-lzma wmctrl gnupg fakeroot
    git clone https://github.com/micahflee/torbrowser-launcher.git
    cd torbrowser-launcher
    ./build_and_install.sh

Installing in Ubuntu
--------------------

I've created a PPA where I'm maintaining torbrowser-launcher binaries. You can install in an Ubuntu-based distribution like this:

    sudo add-apt-repository ppa:micahflee/ppa
    sudo apt-get update
    sudo apt-get install torbrowser-launcher

Building
========

Dependencies
------------

You need to have ```stdeb``` installed. If you're using Debian or Ubuntu you can
install it like this:

    apt-get install python-stdeb

Also install the ```torbrowser-launcher``` dependencies:

    apt-get install python-gtk2 python-psutil python-twisted python-lzma wmctrl gnupg fakeroot

Debian packages
---------------

To build a Debian source and binary packages:

    python setup.py --command-packages=stdeb.command sdist_dsc bdist_deb

Once you've made a ```.deb```, you can install by running this as root:

    dpkg -i deb_dist/torbrowser-launcher_VERSION_all.deb
