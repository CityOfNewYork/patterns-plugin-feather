# Patterns CLI Feather Plugin

This command plugin will compile a SVG icon sprite from the [Feather Icon](https://feathericons.com/) set.

## Usage

Install as a development dependency in a project that uses the [Patterns CLI](https://github.com/CityOfNewYork/patterns-cli).

```shell
$ npm install @nycopportunity/pttrn-plugin-feather -D
```

Add a proxy command script in the **./bin/** directory:

```shell
$ touch bin/feather.js
$ echo "module.exports = require('@nycopportunity/pttrn-plugin-feather');"
```

This will make the command available to the CLI. Compile the sprite by running:

```shell
$ npx pttrn feather
$ ✨ Feather sprite written to ./dist/svg/feather.svg
```

An optional config file can be added with the following options:

Option   | Description
---------|-
`src`    | The source directory for Feather icons.
`dist`   | The distribution path and file name for the compiled sprite.
`ext`    | The extension name for the icons files (this shouldn't change).
`prefix` | The prefix to add to the `<svg>` element ID attribute.

**Config Sample**

```JavaScript
const path = require('path');

module.exports = {
  'src': path.join(process.env.PWD, 'node_modules/feather-icons/dist/icons'),
  'dist': path.join(process.env.PWD, 'dist', 'svg', 'feather.svg'),
  'ext': '.svg',
  'prefix': 'feather-'
};
```

