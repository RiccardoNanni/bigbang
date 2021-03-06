# BigBang

BigBang is a toolkit for studying communications data from collaborative
projects. It currently supports analyzing mailing lists from Sourceforge,
Mailman, or [.mbox][mbox] files.

[mbox]: http://tools.ietf.org/html/rfc4155

[![Gitter](https://badges.gitter.im/datactive/bigbang.svg)](https://gitter.im/datactive/bigbang?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

## Installation*

You can use [Anaconda](https://www.anaconda.com/). This will also install
the `conda` package management system, which you can use to complete
installation.

[Install Anaconda](https://www.anaconda.com/download/), with Python version
3.*.

If you choose not to use Anaconda, you may run into issues with versioning in
Python. Add the Conda installation directory to your path during installation.

You also need need to have Git and Pip (for Python3) installed.

Run the following commands:

```bash

git clone https://github.com/datactive/bigbang.git
cd bigbang
bash conda-setup.sh
```

## Usage

There are serveral Jupyter notebooks in the `examples/` directory of this
repository. To open them and begin exploring, run the following commands in the root directory of this repository:

```bash
source activate bigbang
ipython notebook examples/
```

### Collecting mail archives

BigBang comes with a script for collecting files from public Mailman web
archives. An example of this is the
[scipy-dev](http://mail.python.org/pipermail/scipy-dev/) mailing list page. To
collect the archives of the scipy-dev mailing list, run the following command
from the root directory of this repository:

```bash
python3 bin/collect_mail.py -u http://mail.python.org/pipermail/scipy-dev/
```

You can also give this command a file with several urls, one per line. One of these is provided in the `examples/` directory.

```bash
python3 bin/collect_mail.py -f examples/urls.txt
```

Once the data has been collected, BigBang has functions to support analysis.

## Collecting IETF draft metadata

BigBang can also be used to analyze data from IETF drafts.

It does this using the Glasgow IPL group's `ietfdata` [tool](https://github.com/glasgow-ipl/ietfdata).

The script takes an argument, the working group acronym

```bash
python3 bin/collect_draft_metadata.py -w httpbis
```


## Git

BigBang can also be used to analyze data from Git repositories.

Documentation on this feature can be found [here](https://github.com/datactive/bigbang/blob/master/git-readme.md).

## Unit tests

We use `unittest` for automated tests.

To run the tests from the command like, use the command `pytest`.

## Community

If you are interested in participating in BigBang development or would like support from the core development team, please subscribe to the [bigbang-dev mailing list](https://lists.ghserv.net/mailman/listinfo/bigbang-dev) and let us know your suggestions, questions, requests and comments. A [development chatroom](https://gitter.im/datactive/bigbang) is also available.

In the interest of fostering an open and welcoming environment, we as contributors and maintainers [pledge to make participation in our project and our community a harassment-free experience for everyone](CODE_OF_CONDUCT.md).

## Troubleshooting 

If the installation described above does not work, you can try to run the installation with Pip:

```bash
git clone https://github.com/datactive/bigbang.git
# optionally create a new virtualenv here
pip3 install -r requirements.txt
python3 setup.py develop
```

## License

AGPL-3.0, see LICENSE for its text. This license may be changed at any time according to the principles of the project [Governance](https://github.com/datactive/bigbang/wiki/Governance).
