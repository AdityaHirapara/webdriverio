# eslint-plugin-wdio

ESLint rules for [WebdriverIO](https://webdriver.io)

## Installation

You'll first need to install [ESLint](https://eslint.org):

```sh
npm i eslint --save-dev
```

Next, install `eslint-plugin-wdio`:

```sh
npm install eslint-plugin-wdio --save-dev
```

**Note:** If you installed ESLint globally (using the `-g` flag) then you must also install `eslint-plugin-wdio` globally.

## Recommended configuration

This plugin export a recommended configuration that enforce good practices.

### With Eslint v8 and below

To enable this configuration use the extends property in your `.eslintrc` config file:

```json
{
    "plugins": ["wdio"],
    "extends": [
        "eslint:recommended",
        "plugin:wdio/recommended"
    ]
}
```

### With Eslint v9 and Flat Config

If you are using the latest version of Eslint with the [flat configuration](https://eslint.org/docs/latest/use/configure/migration-guide), you can embed this plugin as follows:

```js
// eslint.config.mjs
import { configs as wdioConfig } from "eslint-plugin-wdio";

export default [
    {
        extends: [
            wdioConfig['flat/recommended'],
            // ...
        ]
    }
];
```

See [ESLint documentation](https://eslint.org/docs/latest/use/configure/configuration-files) for more information about extending configuration files.

## List of supported rules


- [`wdio/await-expect`](./docs/async-methods.md)

`expect` calls must be prefixed with an `await`

- [`wdio/no-debug`](./docs/no-debug.md)

Don't allow `browser.debug()` statements

- [`wdio/no-pause`](./docs/no-pause.md)

Don't allow `browser.pause(<number>)` statements
