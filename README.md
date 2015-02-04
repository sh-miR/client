# shmir_client #
[![GNU License](http://img.shields.io/badge/license-GNU-blue.svg)](http://www.gnu.org/licenses/gpl.html)
[![Documentation Status](https://readthedocs.org/projects/shmir-client/badge/?version=latest)](https://readthedocs.org/projects/shmir-client/)

Client for [sh-miR Designer RESTful API](https://github.com/Nozdi/shmir)

Before usage you need to set up url in settings.py!

Example usage:

Fold sequence via mfold:
```
./shmir_client.py mfold ACTGAUUUGAC
```

Create sh-miR from one siRNA strand (active) or two siRNa strands separated by space.<br>
First strand is active, both are in 5-3 orientation
```
./shmir_client.py from_sirna UUUGUAUUCGCCCUAGCGC CGCUAUGGCGAAUACAAACA
```

Create sh-miR from transcript name.<br>
Optional parameters
* --min_gc : Minimal "GC" content in strand -- default: `40`
* --max_gc : Maximal "GC" content in strand -- default: `60`
* --max_offtarget : Maximal offtarget of strand -- default: `10`
* --mirna_name : The name of miRNA backbone to use -- default: `"all"`
* --immuno : One of `["yes", "no", "no_difference"]` -- default: `"no_difference"`
```
./shmir_client.py from_transcript NM_001618.3 --mirna_name miR-30a --min_gc 22
```
