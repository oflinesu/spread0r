spread0r
========

spread0r is a txt reader, which makes your reading twice as fast as usual


Installation
============

spread0r should run on all platforms supporting perl and gtk2-perl. 
Just clone into the github repo or download a snapshot of:
[spread0r github repo](https://github.com/xypiie/spread0r)

After installing perl and gtk2-perl `chmod a+x ./spread0r.pl` you can start it by double clicking
spread0r.pl or running it in terminal like:

`./spread0r.pl`

Dependencies on ArchLinux
-------------------------
`pacman -S gtk2-perl`

Dependencies on Fedora
-------------------------
`yum install perl-Gtk2`

Dependencies on OSX
-------------------
### Preparation:
  * Install and setup X11
  * Install and setup Homebrew

### Setup
1. Install glib/Pango/Gtk2 with Homebrew
  * brew install glib pango gtk+
2. Add X11 Package Config Path to bashrc
  * add: export PKG_CONFIG_PATH=$PKG_CONFIG_PATH:/opt/X11/lib/pkgconfig
2. Local Perl CPAN Setup
  * perl -MCPAN -e shell
  * follow setup
  * $ echo '[ $SHLVL -eq 1 ] && eval "$(perl -I$HOME/foo/lib/perl5 -Mlocal::lib=$HOME/foo)"' >>~/.bashrc
3. Install Perl modules
  * perl -MCPAN -e shell
  * perl> install Glib
  * perl> install Cairo
  * perl> install Pango
  * perl> install Gtk2
3. have fun with spread0r

Dependencies on Windows
-----------------------
### Disclaimer:
This section does not come with any warranty, whatsoever.
The following steps are copied from [this tutorial](http://foobaring.blogspot.de/2013/03/howto-install-gtk2-in-activeperl-in.html).

### Preparation:
  * Install [Perl](http://downloads.activestate.com/ActivePerl/releases/5.18.2.1801/)
  * Install [GTK for windows](http://downloads.sourceforge.net/gladewin32/gtk-2.8.20-win32-1.exe)

### Setup
  * Open a Command shell
  * run `ppm repo add http://www.sisyphusion.tk/ppm`
  * run `ppm install Gtk2 --force`


Converting ebooks
=================

Ebook-tools
-----------
Using [ebook-tools](http://sourceforge.net/projects/ebook-tools/) and
[html2text](http://www.mbayer.de/html2text) you can
convert your .epubs (or any other format supported by ebook-tools) into a .txt
file using this command:
`einfo -p input_book.epub | html2text | sed -r "s/<[^>]+>//g" > blackout.txt`

Calibre
-------
Using [Calibre](http://calibre-ebook.com/download) you can convert your .epubs
(or any other format supported by calibre) into a .txt file, which can be used
by spread0r.  To do this, you've got two options:
1. use the calibre GUI 
2. use the commandline tool "ebook-convert" of calibre installation
  * Open a terminal
  * run `ebook-convert input_ebook.epub output_ebook.txt`

Converting PDFs
=================

Poppler
-----------
On Linux you can use `pdftotext` from [Poppler](http://poppler.freedesktop.org/):

`$ pdftotext file.pdf`
