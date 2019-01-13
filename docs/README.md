# MDDatasetBuilder
[![python3.6](https://img.shields.io/badge/python-3.6-blue.svg)](https://badge.fury.io/py/MDDatasetBuilder)

MDDatasetBuilder is a script to build molecular dynamics (MD) datasets for neural networks from given LAMMPS trajectories automatically.

**Author**: Jinzhe Zeng

**Email**: jzzeng@stu.ecnu.edu.cn

[Research Group](http://computchem.cn)

## Requirements
* [numpy](https://github.com/numpy/numpy)
* [scikit-learn](https://github.com/scikit-learn/scikit-learn)
* [ASE](https://gitlab.com/ase/ase)

## Installation

```sh
$ git clone https://github.com/njzjz/MDDatasetMaker.git
$ cd MDDatasetMaker/
$ python3 setup.py install
```

## Simple example

A [LAMMPS bond file](http://lammps.sandia.gov/doc/fix_reax_bonds.html) and a [LAMMPS dump file](https://lammps.sandia.gov/doc/dump.html) should be prepared.

```python
>>> from MDDatasetMaker import DatasetMaker
>>> DatasetMaker(bondfilename='bonds.reaxc.ch4_new',dumpfilename='dump.ch4',dataset_dir='dataset_ch4',xyzfilename='ch4',stepinterval=25).makedataset()
```
Then you can calculate generated Gaussian files by [GaussianRunner](https://github.com/njzjz/GaussianRunner).