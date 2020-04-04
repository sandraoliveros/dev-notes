
# Babel 7 🧙‍♂️✨


In order to use Babel we'll need to install at least 4 Babel components:

- `@babel/cli`: It is the Babel CLI and we use it to send commands to Babel. So it is a **development** dependency.
- `@babel/core`: It is needed for Babel CLI to work. Also a **development** dependency.
- `@babel/preset-env`: Babel needs plugins to transpile ES6 code. Given that installing the needed plugins one by one can take a lot of time, there are some collections of plugins available, they are called **presets**. This `preset-env` can be considered the basic preset for using ES6 in browsers. Also a **development** dependency.
- `@babel/polyfill`: **Production** dependency.

## Configuration

We'll need a configuration file called `babel.config.js`.

