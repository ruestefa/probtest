# Branch `pyproject`

Stefan Rüdisühli, Meteomatics (sruedisuehli@meteomatics.com)
July 2024

## Changes

Created the branch `pyproject` to turn the project into a properly installable Python project.

- Move `engine/`, `util/` and `visualize/` into `src/probtest/` and add missing `__init__.py` files
- Move `probtest.py` to `src/probtest/cli.py`
- Adapt all imports, e.g., `from util import xyz` to `from probtest.util import xyz`
- Add `pyproject.toml` that defines command `probtest` that calls `probtest.cli:cli` and replaces `python probtest.py`

## Installation

Install the `probtest` package along with its dependencies into a Conda environment:

```bash
conda env create -n probtest requirements/requirements.yml
conda activate probtest
python -m pip install -e .
```

This installs the the package in editable mode.

Test it:

```shell
$ probtest --help
Usage: probtest [OPTIONS] COMMAND [ARGS]...

Options:
  --log-level TEXT
  --log-file TEXT
  --help            Show this message and exit.

Commands:
  cdo-table
  cdo-table-reader
  check
  check-plot
  init
  performance
  performance-check
  performance-meta-data
  performance-plot
  perturb
  run-ensemble
  stats
  tolerance
```
