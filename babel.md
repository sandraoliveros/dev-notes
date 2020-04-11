# Babel 7 🧙‍♂️✨

In order to use Babel we'll need to install at least 4 Babel components:

- `@babel/cli`: It is the Babel CLI and we use it to send commands to Babel. So it is a **development** dependency.
- `@babel/core`: It is needed for Babel CLI to work. Also a **development** dependency.
- `@babel/preset-env`: Babel needs plugins to transpile ES6 code. Given that installing the needed plugins one by one can take a lot of time, there are some collections of plugins available, they are called **presets**. This `preset-env` can be considered the basic preset for using ES6 in browsers. Also a **development** dependency.
- `@babel/polyfill`: **Production** dependency.

## Configuration

We'll need a configuration file called `babel.config.js` or `.babelrc`. The first one will have an JS object that will be exported and the last one a JSON object. `babel.config.js` would look like this:

```javascript
module.exports = {
  "presets": [
    [
      "@babel/env",
      {
        "targets": {
          "edge": "17",
          "firefox": "60",
          "chrome": "67",
          "safari": "11.1",
        },
        "useBuiltIns": "usage",
      }
    ]
  ]
}
```
Each array inside the `presets` array will contain
1. The translating standard, `@babel/preset-env` in this case
2. The configuration for the translating standard. This configuration object, for its part, contains
    - targets: The browsers we need the code to be translated for. If we keep the targets object empty, the target browsers will be all the browsers, so all the ES6 syntax will be translated to ES5. If we add the modern browsers as target, the ES6 syntax that is already set in these browsers won't be translated (e.g. `let` or `const`).
    - useBuiltIns: It is used to tell Babel how to use the polyfills. It has 3 possible values: `false`, `'usage'` or `'entry'`. The first one disables the polyfills, the second one adds to the output those polyfills that are used in the code and the last one needs the developer to import manually `@babel/polyfill` in her file.

### babel.config.js vs .babelrc

`babel.config.js` (or `babel.config.json`) translates any file in any directory and `.babelrc` only translates files inside its directory. That's why Babel docs say that `babel.config.json` is used for __project-wide configuration__ and `.babelrc` is __file-relative configuration__.

## Tips ✏️
- If the output stills the same, take a look at the top of the output file: Babel always adds `"use strict"`
