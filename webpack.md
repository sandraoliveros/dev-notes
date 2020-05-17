# Webpack 4 🕸📦

## Install
```
npm i -D webpack webpack-cli
```

## Default values
- If you run `npx webpack` without any configuration, Webpack will consider that the entry file is `src/index.js` and that the output one is `dist/main.js`.
- Mode: The default mode is the production mode. Webpack 4 minifies the bundle in this mode.

## Configuration file

Its default name is `webpack.config.js`. The simplest one would look like this:
```javascript
const path = require('path');

module.exports = {
  mode:'development',
  entry: './src/index.js',
  output: {
    filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist')
  },
  module: {
    rules: [
      {
        test: /\.css$/,
        use: ['style-loader', 'css-loader']
      }
    ]
  }
};


```
- __entry:__ The URL of the entry point
- __output.filename:__ The name of the bundle
- __output.path:__ It controls the location of the bundle file and its value must be an __absolute URL__.
- __module:__ Configuration for the loaders
- __module.rules:__ Transformation rules for the files
- __module.rules.test:__ Regular expression to match the files where the rule will be applied
- __module.rules.use:__ Array with the loaders that will be used. They will be __applied from the end to the beginning__, so the order is very important here