# script-formatter

Takes a Shakespearean script formatted as a spreadsheet and produces nicely
formatted text, HTML, or XSL-FO output.

## Quick Start

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

# select a different input format
# given an input file name, it will use the file extension to select a parser
# for Excel files, it selects sheet 1 by default; use --sheet to change
scriptf -c speaker=2 -c number=3 -c text=4 -i richard2.xlsx --sheet 2 >richard2.html
```
