## importlab - https://github.com/google/importlab/

Importlab is a library for Python that automatically infers dependencies and
calculates a dependency graph. It can perform dependency ordering of a set of
files, including cycle detection.

Importlab's main use case is to work with static analysis tools that process one
file at a time, ensuring that a file's dependencies are analysed before it is.

(This is not an official Google product.)

## License
Apache 2.0

## Installation

```
git clone https://github.com/google/importlab.git
cd importlab
python setup.py install
```

## Usage

Importlab is primarily intended to be used as a library. It takes one or more
python files as arguments, and generates an import graph, typically used to
process files in dependency order.

It is currently integrated into [pytype](https://github.com/google/pytype) as
part of the `pytype-all` tool.

## Command-line tool

Importlab ships with a small command-line tool, also called `importlab`, which
can display some information about a project's import graph.

```
usage: importlab [-h] [--tree] [--unresolved] [filename [filename ...]]

positional arguments:
  filename              input file(s)

optional arguments:
  -h, --help            show this help message and exit
  --tree                Display import tree.
  --unresolved          Display unresolved dependencies.
```


## Roadmap

* `Makefile` generation, to take advantage of `make`'s incremental update and
  parallel execution features

* Integration with other static analysis tools
