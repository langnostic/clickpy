# clickpy

Automated mouse clicker script.

## Installation

I've only tested this packag with Python 3.9. You'll need to download and install it, or use pyenv and set your local version with this command:

```bash
pyenv local 3.9
```

I also recommend using pipx for installing standalone packages, as it will add a layer of isolation to your installation. But pip will work too:

```bash
pipx install clickpy
# -- or --
pip install clickpy
```

## Development

Using [Poetry][1] to manage the virtual environment and packages. I also highly recommend using [Pyenv][2] to install and manage your python interpreters.

This script uses [pyautogui][3] for clicking and [Typer][4] for CLI parsing.

### Testing

This project utilizes [pytest][5] and [pytest-mock][6]. Both should be included in pyproject.toml dev dependencies, and `.vscode/settings.json` should already be setup to use these libraries.

Please type annotate any mocks used, which should be `MockerFixture` if you use pytest-mock.

### Scripts

The following is for developers. You don't need to run these scripts to install and run from pip.


```bash
# define your local python version
pyenv local 3.9.6
```

```bash
# install all deps from pyproject.toml
poetry install
```

```bash
# activate virtual environment first
poetry shell
# run tests, also outputs code coverage
python -m pytest -v --cov=clickpy --capture=sys tests/
```

```bash
# run this to generate report
coverage html
```

Open coverage report in bash. This should also work with Windows Git Bash

```bash
# open html coverage doc, windows doesn't have open.
[ -x "$(command -v open)" ] && open htmlcov/index.html || start htmlcov/index.html
```

Here's a Powershell version:

```powershell
start htmlcov\index.html
```

And also a fish version.

```sh
# same command for fish shell
[ -x (command -v open) ] && open htmlcov/index.html || start htmlcov/index.html
```

[1]: https://github.com/python-poetry/poetry
[2]: https://github.com/pyenv/pyenv
[3]: https://github.com/asweigart/pyautogui
[4]: https://github.com/tiangolo/typer
[5]: https://github.com/pytest-dev/pytest
[6]: https://github.com/pytest-dev/pytest-mock
