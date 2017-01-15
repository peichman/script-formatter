# script-formatter

Takes a Shakespearean script formatted as a spreadsheet and produces nicely
formatted output.

## Synopsis

```
# default input format is CSV
# default output format is HTML
# the -c option selects the columns to use for the speaker, line number, and text of the line
# these are all required
scriptf -c speaker=2 -c number=3 -c text=4 <richard2.csv >richard2.html

# select a different ouptut format
# text
scriptf -c speaker=2 -c number=3 -c text=4 -f txt <richard2.csv >richard2.txt
# XSL-FO (using FOP to create PDF)
scriptf -c speaker=2 -c number=3 -c text=4 -f fo <richard2.csv | fop - - >richard2.pdf
# PDF (uses FOP internally)
scriptf -c speaker=2 -c number=3 -c text=4 -f pdf <richard2.csv >richard2.pdf
# PS (uses FOP internally)
scriptf -c speaker=2 -c number=3 -c text=4 -f ps <richard2.csv >richard2.ps

# select a different input format
# given an input file name, it will use the file extension to select a parser
# for Excel files, it selects sheet 1 by default; use --sheet to change
scriptf -c speaker=2 -c number=3 -c text=4 -i richard2.xlsx --sheet 2 >richard2.html
```

## Installation

The easiest way to install the prerequisite modules is to use [cpanm] to download and install the dependencies listed in the [cpanfile](cpanfile).

The following was tested and confirmed to work on a brand-new install of Ubuntu
Xenial Xerus:

```
sudo apt-get install gcc make libexpat1-dev cpanminus fop
git clone https://github.com/peichman/script-formatter.git
cd script-formatter
cpanm -S --installdeps .
```

[cpanm]: http://search.cpan.org/~miyagawa/App-cpanminus-1.7042/bin/cpanm
