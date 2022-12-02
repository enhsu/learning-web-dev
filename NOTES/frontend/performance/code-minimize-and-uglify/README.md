# Code Minimize & Uglify

Webpack minimize

```js
// webpack.config.js
var path = require("path");
var webpack = require("webpack");

module.exports = {
  entry: ["./src/index"],
  output: {
    path: path.join(__dirname, "dist"),
    filename: "bundle.js",
  },
  plugins: [
    new webpack.optimize.UglifyJsPlugin({
      compressor: {
        warnings: false,
      },
    }),
    new webpack.optimize.OccurenceOrderPlugin(),
  ],
};
```

## How to debug - sourcemap

A.K.A .map file

## Reference

- [webpack UglifyJsPlugin](https://v4.webpack.js.org/plugins/uglifyjs-webpack-plugin/)
