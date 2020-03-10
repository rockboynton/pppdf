# pppdf

Pretty Print a PDF of code

This is a simple script to create a pdf of source code.

The code shall be rendered in color with line numbers shown.

**Note:** No lines in the source code shall be more than ~ 80 characters to
avoid wrapping. The order of the files is important:

## Installation

Install from source using `git`:
`$ git clone git@github.com:rockboynton/pppdf.git`

Move the script ideally in your user’s `/bin` directory

## Usage

1. In general, the first file will be whatever source file contains
`main()`

2. Any project-wide header file(s).

3. Each class’s header file followed by its source
file.

4. The Makefile.

If you don't have guidelines to follow, it is generally best to order them in
decreasing order of importance/integration.

## Example

If a particular source code has files appearing in this order,

* main.cpp, class1.h, class1.cpp, class2.h, class2.cpp, Makefile.

then you can run the script as follows:

`$ pppdf source main.cpp, class1.h, class1.cpp, class2.h, class2.cpp`

## Implementation Details

`a2ps` takes a text file and converts it to be printed on a Postscript printer and add features such as a
header and footer, page numbers, and most importantly, source code formatting.

Another tool, `ps2pdf` will take Postscript code and render it to pdf.
