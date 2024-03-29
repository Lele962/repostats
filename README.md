# PYSTATS

Pygount is a command line tool to scan folders for source code files and
count the number of source code lines in it. It is similar to tools like
[sloccount](https://www.dwheeler.com/sloccount/) and
[cloc](https://github.com/AlDanial/cloc) 

Pystats is open source and distributed under the
[BSD license](https://opensource.org/licenses/BSD-3-Clause). The source
code is available from [https://github.com/roskakori/pygount](https://github.com/Lele962/repostats).

## Quickstart

For installation run

```bash
$ pip install pygount
```

To get a list of line counts for a projects stored in a certain folder run for
example:

```bash
$ pygount ~/projects/example
```

To limit the analysis to certain file types identified by their suffix:

```bash
$ pygount --suffix=cfg,py,yml ~/projects/example
```

To get a summary of each programming language with sum counts and percentage:

```bash
$ pygount --format=summary ~/projects/example
```

To analyze a remote git repository directly without having to clone it first:

```bash
$ pygount --format=summary https://github.com/roskakori/pygount.git
```

You can pass a specific revision at the end of the remote URL:

```bash
$ pygount --format=summary https://github.com/roskakori/pygount.git/v1.5.1
```

This example results in the following summary output:

```
┏━━━━━━━━━━━━━━━━━━┳━━━━━━━┳━━━━━━━┳━━━━━━┳━━━━━━┳━━━━━━━━━┳━━━━━━┓
┃ Language         ┃ Files ┃     % ┃ Code ┃    % ┃ Comment ┃    % ┃
┡━━━━━━━━━━━━━━━━━━╇━━━━━━━╇━━━━━━━╇━━━━━━╇━━━━━━╇━━━━━━━━━╇━━━━━━┩
│ Python           │    18 │  47.4 │ 2132 │ 63.6 │     418 │ 12.5 │
│ TOML             │     2 │   5.3 │ 1204 │ 82.7 │       1 │  0.1 │
│ reStructuredText │     9 │  23.7 │  566 │ 64.8 │       1 │  0.1 │
│ Markdown         │     3 │   7.9 │   53 │ 49.1 │       0 │  0.0 │
│ Batchfile        │     1 │   2.6 │   24 │ 68.6 │       1 │  2.9 │
│ Text only        │     2 │   5.3 │   24 │ 82.8 │       0 │  0.0 │
│ Bash             │     2 │   5.3 │   12 │ 80.0 │       3 │ 20.0 │
│ Makefile         │     1 │   2.6 │    9 │ 45.0 │       7 │ 35.0 │
├──────────────────┼───────┼───────┼──────┼──────┼─────────┼──────┤
│ Sum              │    38 │ 100.0 │ 4024 │ 68.4 │     431 │  7.3 │
└──────────────────┴───────┴───────┴──────┴──────┴─────────┴──────┘
```

Plenty of tools can post process SLOC information, for example the
[SLOCCount plug-in](https://wiki.jenkins-ci.org/display/JENKINS/SLOCCount+Plugin)
for the [Jenkins](https://jenkins.io/) continuous integration server.

A popular format for such tools is the XML format used by cloc, which pygount
also supports and can store in an output file:

```bash
$ pygount --format=cloc-xml --out=cloc.xml ~/projects/example
```

To get a short description of all available command line options use:

```bash
$ pygount --help
```

For more information and examples read the documentation chapter on
[Usage](https://pygount.readthedocs.io/en/latest/usage.html).

## Contributions

To report bugs, visit the
[issue tracker][https://github.com/roskakori/pygount/issue](https://github.com/Lele962/repostats/issues).

In case you want to play with the source code or contribute improvements, see
[CONTRIBUTING](https://pygount.readthedocs.io/en/latest/contributing.html).

## Version history

See [CHANGES](https://pygount.readthedocs.io/en/latest/changes.html).
