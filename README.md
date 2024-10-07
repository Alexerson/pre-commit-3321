To reproduce [the bug](https://github.com/pre-commit/pre-commit/issues/3321), assuming you have pre-commit installed:

```sh
# Pull this repo
git clone https://github.com/alexerson/pre-commit-3321

# Install pre-commit in this repo
pre-commit install

# Run pre-commit on all files
pre-commit run --all-files
```
