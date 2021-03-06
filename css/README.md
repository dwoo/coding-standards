# CSS Guidelines

## Formatting

Use Prettier — see the [JavaScript](../javascript/) guidelines for more details
but the out-of-the-box defaults using our top-level `.editorconfig` are quite
reasonable. The easiest way to start using Prettier is to follow the [official
installation instructions](https://prettier.io/docs/en/install.html) with a
global install using either NPM or Yarn:

    yarn global add prettier
    npm install --global prettier

Once you have it installed, you can reformat JavaScript, CSS, SCSS/LESS, etc.
from the shell using e.g. `yarn run prettier`, `npm run prettier`, or simply
`prettier` if your PATH includes the install directory:

```bash
$ prettier --write example.css
example.css 81ms
✨  Done in 0.32s.
```

[Many editors](https://prettier.io/docs/en/editors.html) and build tools have
integrated support and it's highly recommended that you enable it as a
format-on-save action in your editor or a Git [`pre-commit`
hook](https://prettier.io/docs/en/precommit.html).

## Linting

The provided [`.stylelintrc`](..stylelintrc) configures
[stylelint](https://stylelint.io/) using the Prettier plugin for consistency.
You can enable this using either NPM or yarn:

    npm install --only=dev prettier stylelint-config-prettier stylelint stylelint-config-recommended
    yarn add --dev prettier stylelint-config-prettier stylelint stylelint-config-recommended

This configuration uses [stylelint-config-recommended][scr] and
[stylelint-config-prettier][sc-prettier] to match the Prettier defaults with
very limited modification. Please consider the long-term maintenance cost versus
the benefits of any local variations.

Because coding standards vary more across projects based on the selected
configuration options and differing levels of browser support, it's recommended
that you install both the linters and configurations in your project so they'll
be versioned in `package.json` and can follow a normal release process.

## Preprocessors

Languages such as LESS and SCSS are extremely useful for large projects and are
in daily use at the Library. If you use one on your project, please change the
recommended configuration from [stylelint-config-recommended][scr] to e.g.
[stylelint-config-recommended-scss][scr-scss].

[scr]: https://github.com/stylelint/stylelint-config-recommended
[sc-prettier]: https://github.com/shannonmoeller/stylelint-config-prettier
[scr-scss]: https://github.com/kristerkari/stylelint-config-recommended-scss
