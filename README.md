# LibreOffice Utils

[![Actions Status](https://github.com/scivision/libreoffice-utils/workflows/ci_python/badge.svg)](https://github.com/scivision/libreoffice-utils/actions)
[![PyPi versions](https://img.shields.io/pypi/pyversions/loutils.svg)](https://pypi.python.org/pypi/loutils)
[![PyPi Download stats](http://pepy.tech/badge/loutils)](http://pepy.tech/project/loutils)

Headless (command line) operations on Word, Excel, Powerpoint and most other
[formats LibreOffice can handle](https://en.wikipedia.org/wiki/LibreOffice#Supported_file_formats)
for:

* Doc => PDF conversion  (LibreOffice only)
* printing (to the system default printer only)

from Python command line using LibreOffice or Microsoft Word

## .doc / .docx to PDF conversion

Convert a directory of .doc / .docx to .pdf by:

```sh
doc2pdf ~/Documents
```

## Printing

CAUTION:

The doc2print.py script can print an unlimited number of pages to an unwanted printer, possibly causing great expense or violation of private documents to a public printer. Use great care with these scripts, preferably to a local non-networked printer you are sitting next to.


```sh
doc2print ~/mydocs
```

The `-exe` parameter allows selecting the printing program.
The script does not check that the files can be printed appropriately, it just prints.
Thus use the `-s` parameter to select only the suffixes wanted.
For example to print all Markdown files in a directory with Notepad++:

```sh
doc2print ~/mydocs -s .md -exe notepad++
```

## Notes

### LibreOffice

Since the command-line globbing of LibreOffice conversion is broken, this program provides a sane workaround for mass document conversion using LibreOffice.
LibreOffice is not thread-safe, so documents are converted or printed one at a time.