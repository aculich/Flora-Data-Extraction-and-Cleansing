# Flora-Data-Extraction-and-Cleansing

Run this code on: [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/aculich/Flora-Data-Extraction-and-Cleansing/HEAD)

See also old repo: https://github.com/aculich/extract-flora

## How to run

First download the PDF files as `flora-book-01.pdf`, `flora-book-02.pdf`, `flora-book-03.pdf`.

Then extract the csv files and run the cleaning scripts:

```
python extract-flora-data-from-flora-pdf-files.py
python data-cleansing-of-extracted-flora-data.py
python data-cleansing-of-extracted-flora-data-Syria.py

```

## Installation Notes

### Fix error: ModuleNotFoundError: No module named 'frontend'

```
$ python extract-flora-data-from-flora-pdf-files.py 
Traceback (most recent call last):
  File "extract-flora-data-from-flora-pdf-files.py", line 1, in <module>
    import fitz
  File "/srv/conda/envs/notebook/lib/python3.7/site-packages/fitz/__init__.py", line 1, in <module>
    from frontend import *
ModuleNotFoundError: No module named 'frontend'
```

The 1.18 version of PyMuPDF does not work, so we need to explicitly downgrade to a previous version.

```
Requirement already satisfied: PyMuPDF in /srv/conda/envs/notebook/lib/python3.7/site-packages (1.18.19)
```

See: https://stackoverflow.com/a/63842725/462302

```
pip install PyMuPDF==1.16.14
```

So we'll explicitly pin this version of the package in [requirements.txt](./requirements.txt)
