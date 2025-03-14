![Version](https://img.shields.io/github/v/release/DCMLab/schubert_winterreise?display_name=tag)
[![DOI](https://zenodo.org/badge/388182679.svg)](https://doi.org/10.5281/zenodo.14997095)
![GitHub repo size](https://img.shields.io/github/repo-size/DCMLab/schubert_winterreise)
![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-9cf)


This is a README file for a data repository originating from the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora)
and serves as welcome page for both 

* the GitHub repo [https://github.com/DCMLab/schubert_winterreise](https://github.com/DCMLab/schubert_winterreise) and the corresponding
* documentation page [https://dcmlab.github.io/schubert_winterreise](https://dcmlab.github.io/schubert_winterreise)

For information on how to obtain and use the dataset, please refer to [this documentation page](https://dcmlab.github.io/schubert_winterreise/introduction).

# Franz Schubert – Winterreise (A corpus of annotated scores)

Schubert composed this groundbreaking song cycle in the form of a monodrama during the last year of his life. It was
first presented at one of the composer's famous 'Schubertiades', musical gatherings at his residence in Vienna. Through
the twenty-four numbers, the anguish at the speaker's loss of love is overtaken by a bleak existential depression. These
songs have become an essential part of the classical singer's repertoire. Our annotations highlight the long
contrapuntal elaborations and pedal points that support Schubert's innovative text-painting.

## Getting the data

* download repository as a [ZIP file](https://github.com/DCMLab/schubert_winterreise/archive/main.zip)
* download a [Frictionless Datapackage](https://specs.frictionlessdata.io/data-package/) that includes concatenations
  of the TSV files in the four folders (`measures`, `notes`, `chords`, and `harmonies`) and a JSON descriptor:
  * [schubert_winterreise.zip](https://github.com/DCMLab/schubert_winterreise/releases/latest/download/schubert_winterreise.zip)
  * [schubert_winterreise.datapackage.json](https://github.com/DCMLab/schubert_winterreise/releases/latest/download/schubert_winterreise.datapackage.json)
* clone the repo: `git clone https://github.com/DCMLab/schubert_winterreise.git` 


## Data Formats

Each piece in this corpus is represented by five files with identical name prefixes, each in its own folder. 
For example, the first song, *Gute Nacht*, has the following files:

* `MS3/n01.mscx`: Uncompressed MuseScore 3.6.2 file including the music and annotation labels.
* `notes/n01.notes.tsv`: A table of all note heads contained in the score and their relevant features (not each of them represents an onset, some are tied together)
* `measures/n01.measures.tsv`: A table with relevant information about the measures in the score.
* `chords/n01.chords.tsv`: A table containing layer-wise unique onset positions with the musical markup (such as dynamics, articulation, lyrics, figured bass, etc.).
* `harmonies/n01.harmonies.tsv`: A table of the included harmony labels (including cadences and phrases) with their positions in the score.

Each TSV file comes with its own JSON descriptor that describes the meanings and datatypes of the columns ("fields") it contains,
follows the [Frictionless specification](https://specs.frictionlessdata.io/tabular-data-resource/),
and can be used to validate and correctly load the described file. 

### Opening Scores

After navigating to your local copy, you can open the scores in the folder `MS3` with the free and open source score
editor [MuseScore](https://musescore.org). Please note that the scores have been edited, annotated and tested with
[MuseScore 3.6.2](https://github.com/musescore/MuseScore/releases/tag/v3.6.2). 
MuseScore 4 has since been released which renders them correctly but cannot store them back in the same format.

### Opening TSV files in a spreadsheet

Tab-separated value (TSV) files are like Comma-separated value (CSV) files and can be opened with most modern text
editors. However, for correctly displaying the columns, you might want to use a spreadsheet or an addon for your
favourite text editor. When you use a spreadsheet such as Excel, it might annoy you by interpreting fractions as
dates. This can be circumvented by using `Data --> From Text/CSV` or the free alternative
[LibreOffice Calc](https://www.libreoffice.org/download/download/). Other than that, TSV data can be loaded with
every modern programming language.

### Loading TSV files in Python

Since the TSV files contain null values, lists, fractions, and numbers that are to be treated as strings, you may want
to use this code to load any TSV files related to this repository (provided you're doing it in Python). After a quick
`pip install -U ms3` (requires Python 3.10 or later) you'll be able to load any TSV like this:

```python
import ms3

labels = ms3.load_tsv("harmonies/n01.harmonies.tsv")
notes = ms3.load_tsv("notes/n01.notes.tsv")
```


## Version history

See the [GitHub releases](https://github.com/DCMLab/schubert_winterreise/releases).

## Questions, Suggestions, Corrections, Bug Reports

Please [create an issue](https://github.com/DCMLab/schubert_winterreise/issues) and/or feel free to fork and submit pull requests.

## Cite as

> Johannes Hentschel, Yannis Rammos, Markus Neuwirth, & Martin Rohrmeier. (2025). Franz Schubert – Winterreise (A corpus of annotated scores) [Data set]. Zenodo. https://doi.org/10.5281/zenodo.14997095

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)).

![cc-by-nc-sa-image](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)

## Overview
|file_name|measures|labels|standard|   annotators    |    reviewers     |
|---------|-------:|-----:|--------|-----------------|------------------|
|n01      |     105|   214|2.1.0   |Alexander Faschon|Johannes Hentschel|
|n02      |      51|    70|2.1.0   |Alexander Faschon|Johannes Hentschel|
|n03      |      55|   141|2.1.0   |Alexander Faschon|Johannes Hentschel|
|n04      |     109|   187|2.1.0   |Alexander Faschon|Johannes Hentschel|
|n05      |      83|   245|2.1.0   |Alexander Faschon|Adrian Nagel      |
|n06      |      32|    44|2.1.0   |Alexander Faschon|Adrian Nagel      |
|n07      |      74|   176|2.1.0   |Alexander Faschon|Adrian Nagel      |
|n08      |      69|   353|2.1.0   |Alexander Faschon|Adrian Nagel      |
|n09      |      43|    72|2.1.0   |Alexander Faschon|Adrian Nagel      |
|n10      |      67|   105|2.1.0   |Alexander Faschon|Adrian Nagel      |
|n11      |      88|   168|2.1.0   |Alexander Faschon|Adrian Nagel      |
|n12      |      48|    82|2.1.0   |Alexander Faschon|Adrian Nagel      |
|n13      |      94|   111|2.1.0   |Alexander Faschon|Adrian Nagel      |
|n14      |      44|    57|2.1.0   |Alexander Faschon|Adrian Nagel      |
|n15      |      43|   169|2.1.0   |Alexander Faschon|Adrian Nagel      |
|n16      |      47|   101|2.1.0   |Alexander Faschon|Adrian Nagel      |
|n17      |      49|   112|2.1.0   |Alexander Faschon|Adrian Nagel      |
|n18      |      19|    61|2.1.0   |Alexander Faschon|Adrian Nagel      |
|n19      |      43|    66|2.1.0   |Alexander Faschon|Adrian Nagel      |
|n20      |      83|   167|2.1.0   |Alexander Faschon|Adrian Nagel      |
|n21      |      32|   153|2.1.0   |Alexander Faschon|Adrian Nagel      |
|n22      |      46|    80|2.1.0   |Alexander Faschon|Adrian Nagel      |
|n23      |      32|    87|2.1.0   |Alexander Faschon|Adrian Nagel      |
|n24      |      61|    79|2.1.0   |Alexander Faschon|Adrian Nagel      |


*Overview table automatically updated using [ms3](https://ms3.readthedocs.io/).*
