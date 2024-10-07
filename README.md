To reproduce [the bug](https://github.com/pre-commit/pre-commit/issues/3321), assuming you have pre-commit installed:

```sh
# Pull this repo
git clone https://github.com/alexerson/pre-commit-3321
cd pre-commit-3321

# Install pre-commit in this repo
pre-commit install

# Run pre-commit on all files will fail
pre-commit run --all-files

# Removing the eslint.config.js file, to force eslint to use the commonJS file
mv eslint.config.js eslint.config.js.bak
mv eslint.config.cjs.bak eslint.config.cjs

# Now pre-commit works fine
pre-commit run --all-files

# Restoring init state
mv eslint.config.js.bak eslint.config.js
mv eslint.config.cjs eslint.config.cjs.bak
```

Note that even though I specified a `package.json` to prove that a `npm install` is another way to work around the issue, it is not used or required by pre-commit.
