<div align=center>

# typeshed-stats

<img src="https://user-images.githubusercontent.com/66076021/202873196-3af493e6-bca0-4c1a-8853-73635b5c1ca8.png" width="500">

<br><hr>

## A CLI tool and library to gather stats on [typeshed](https://github.com/python/typeshed)

<br>

[![website](https://img.shields.io/website?down_color=red&down_message=Offline&style=for-the-badge&up_color=green&up_message=Running&url=https%3A%2F%2Falexwaygood.github.io%2Ftypeshed-stats%2F)](https://alexwaygood.github.io/typeshed-stats/)[![build status](https://img.shields.io/github/workflow/status/AlexWaygood/typeshed-stats/tests/main?label=Tests&style=for-the-badge)](https://github.com/AlexWaygood/typeshed-stats/actions/workflows/test.yml)[![Coveralls](https://img.shields.io/coverallsCoverage/github/AlexWaygood/typeshed-stats?style=for-the-badge)](https://coveralls.io/github/AlexWaygood/typeshed-stats)
<br>
[![Checked with mypy](https://img.shields.io/badge/mypy-checked-blue?style=for-the-badge)](http://mypy-lang.org/)[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg?style=for-the-badge)](https://github.com/psf/black)[![Imports: isort](https://img.shields.io/badge/%20imports-isort-%231674b1?style=for-the-badge&labelColor=ef8336)](https://pycqa.github.io/isort/)[![license](https://img.shields.io/github/license/AlexWaygood/typeshed-stats?style=for-the-badge)](https://opensource.org/licenses/MIT)
<br>[![PyPI](https://img.shields.io/pypi/v/typeshed-stats?style=for-the-badge)](https://pypi.org/project/typeshed-stats/)![PyPI - Python Version](https://img.shields.io/pypi/pyversions/typeshed-stats?style=for-the-badge)![PyPI - Wheel](https://img.shields.io/pypi/wheel/typeshed-stats?style=for-the-badge)

<hr>
<br>
</div>

## What's this project for?

This project is for easy gathering of statistics relating to [typeshed](https://github.com/python/typeshed)'s stubs. As well as being a CLI tool and library, it also powers [a website](https://alexwaygood.github.io/typeshed-stats/) where stats about typeshed's stubs are uploaded twice a day.

Some examples of things you can do from the command line:

- Create a `.csv` file with stats on all typeshed stubs: `typeshed-stats --typeshed-dir <PATH_TO_TYPESHED_CLONE> --to-file stats.csv` (the `.csv` file extension will be automatically detected by the script to identify the format required).
- Pretty-print stats on typeshed stubs for emoji and redis to the terminal, in JSON format: `typeshed-stats --typeshed-dir <PATH_TO_TYPESHED_CLONE> --to-json emoji redis`
- Generate a MarkDown file detailing stats on typeshed's stubs for protobuf and the stdlib: `typeshed-stats --typeshed-dir <PATH_TO_TYPESHED_CLONE> --to-file stats.md stdlib protobuf`

Example usage of the Python-level API:

```python
from typeshed_stats.gather import tmpdir_typeshed, gather_stats

with tmpdir_typeshed() as typeshed:
    stats = gather_stats(typeshed_dir=typeshed)
```

## How can I use this?

1. Run `pip install typeshed-stats[rich]` to install the package
1. Run `typeshed-stats --help` for information about various options

## Are there any examples of things this script can produce, other than [the website](https://alexwaygood.github.io/typeshed-stats/)?

I'm glad you asked! They're in the `examples/` folder in this repo.
(These examples are generated using the `regenerate_examples.py` script in the `scripts/` directory.)

## How do I run tests/linters?

1. Clone the repo and `cd` into it
1. Create and activate a virtual environment
1. Run `pip install -r requirements/all.txt`
1. Run `pip install -e .[rich]`
1. Either run the linters/tests individually (see the `.github/workflows` directory for details about what's run in CI) or use the `runtests.py` convenience script to run them all in succession.
