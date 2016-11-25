# PostCSS NPM Boilerplate

This is a simple boilerplate for using [NPM](https://www.npmjs.com/) and [PostCSS](http://postcss.org/) to handle common front-end development environments.

## Setup

1. Clone the repository
 * `git clone https://github.com/keenanpayne/postcss-npm-boilerplate.git`
2. Install [Yarn Package Manager](https://yarnpkg.com/en/docs/install). You may alternatively use NPM as you may already be used to. I recommend Yarn for easier and more expedited package installation.
3. Install dependencies
 * **Using Yarn:** `yarn`
 * **Using NPM:** `npm install`

## Features

This boilerplate features many features similar to [Sass](http://sass-lang.com/).

## Scripts

This boilerplate relies only on NPM scripts as the build tool. Included build processes are as follows:

### `npm start`

Compiles the `/src/css/app.css` file and outputs to `/dist/css/app.css`. This command watches the file tree inside of `/src/css` for changes and recompiles when necessary.

### `npm run build`

Only compiles the `/src/css/app.css` file and outputs to `/dist/css/app.css` without watching the file tree.

### `npm run stylefmt`

Uses a combination of [stylelint](http://stylelint.io/) and [stylemt](https://github.com/morishitter/stylefmt) PostCSS plugins to organize **source** CSS files according to style lint rules (located in `.stylelintrc`).

### `npm run compile`

Runs both the `build` and `stylefmt` commands to build distribution files and format source files.

## Plugins

This boilerplate relies on the following PostCSS plugins:

- [autoprefixer](https://github.com/postcss/autoprefixer)
- [cssnano](http://cssnano.co/)
- [postcss-advanced-variables](https://github.com/jonathantneal/postcss-advanced-variables)
- [postcss-custom-media](https://github.com/postcss/postcss-custom-media)
- [postcss-import](https://github.com/postcss/postcss-import)
- [postcss-mixins](https://github.com/postcss/postcss-mixins)
- [postcss-nested](https://github.com/postcss/postcss-nested)
- [stylefmt](https://github.com/morishitter/stylefmt)
- [stylelint](http://stylelint.io/)
