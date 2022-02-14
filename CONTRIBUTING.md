# Contributing

Ensure you have the correct Python version on your system. You can use [pyenv](https://github.com/pyenv/pyenv) to install multiple versions of Python if needed.

```sh
pyenv install 3.9
```

Install the necessary Python packages from the Pipfile in this repo:

```sh
pipenv install
```

The [pre-commit framework](https://pre-commit.com/) is used to maintain code standards. Install the hooks in `.pre-commit-config.yaml` with the command:

```sh
pipenv run pre-commit install
```

You're ready to run! Make your changes, then install and run emojione-picker to test them:

```sh
./install.sh
emojione-picker
```

You can run `./install.sh` again to uninstall, then make more changes, then install and repeat.

PRs are welcome!
