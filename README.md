# PostCSS NPM Boilerplate

This is a simple boilerplate for using [NPM](https://www.npmjs.com/) and [PostCSS](http://postcss.org/) to handle common front-end development environments.

## Setup

1. Clone the repository
 * `git clone https://github.com/keenanpayne/postcss-npm-boilerplate.git`
2. **(optional)** Install [Yarn Package Manager](https://yarnpkg.com/en/docs/install). Alternatively, you can use NPM as you may already be used to. I recommend Yarn for easier and more expedited package installation.
3. Install dependencies
 * **Using Yarn:** `yarn`
 * **Using NPM:** `npm install`

## Features

This boilerplate features many features similar to [Sass](http://sass-lang.com/) without including the entire feature set. I have hand-picked the functionality that I use most commonly in my projects.

### Variables

```
$display: flex;

.element {
  display: $display;
}
```

Compiles To:

```
.element {
  display: flex;
}
```

### Nested Elements

```
.element {
  &:hover {
    background: white;
  }

  .element-child {
    position: relative;
  }
}
```

Compiles to:

```
.element:hover {
  background: white;
}

.element .element-child {
  position: relative;
}
```

### Loops

```
@each $icon in (foo, bar, baz) {
  .icon-$icon {
    background: url('path/to/$icon.png');
  }
}

@for $index from 1 to 5 by 2 {
  .col-$index {
    width: $(index)0%;
  }
}
```

Compiles to:

```
.icon-foo {
  background: url('path/to/foo.png');
}

.icon-bar {
  background: url('path/to/bar.png');
}

.icon-baz {
  background: url('path/to/baz.png');
}

.col-1 {
  width: 10%;
}

.col-3 {
  width: 30%;
}

.col-5 {
  width: 50%;
}
```

### Custom Breakpoints

```
@custom-media --small-max (max-width: 30em);

@media (--small-max) {
  /* styles for small viewport */
}
```

Compiles to:

```
@media (max-width: 30em) {
  /* styles for small viewport */
}
```

## Scripts

This boilerplate relies only on NPM scripts as the build tool. Included build processes are as follows:

#### `npm start`

Compiles the `/src/css/app.css` file and outputs to `/dist/css/app.css`. This command watches the file tree inside of `/src/css` for changes and recompiles when necessary.

#### `npm run build`

Only compiles the `/src/css/app.css` file and outputs to `/dist/css/app.css` without watching the file tree.

#### `npm run minify`

Uses cssnano to minify the `/dist/css/app.css` file and output a minified version to `/dist/css/app.min.css`.

#### `npm run stylefmt`

Uses a combination of [stylelint](http://stylelint.io/) and [stylemt](https://github.com/morishitter/stylefmt) PostCSS plugins to organize **source** CSS files according to style lint rules (located in `.stylelintrc`).

#### `npm run compile`

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
