# OVERVIEW

Create a React web app with a webpack bundler.

## Get started

Fork and clone the repo and then download all dependancies:

```
npm install
```

---

# REACT

npm set-up used:

```
npm install react react-dom react-router-dom
```

[React Router](https://reactrouter.com/en/main) is included for convenience.

---

# BABEL

npm set-up used:

```
npm install --save-dev @babel/core @babel/cli @babel/preset-react @babel/preset-env
```

[Babel](https://babeljs.io/) will be used by webpack's babel-loader to transpile our .js and .jsx files during the build.

## babel.config.json

Configuration file for Babel where we tell Babel which [presets](https://babeljs.io/docs/presets) we want to use.

---

# WEBPACK

npm set-up used:

```
npm install --save-dev webpack webpack-cli style-loader css-loader babel-loader html-webpack-plugin copy-webpack-plugin webpack-dev-server
```

[Webpack is used to produce a static module from your code](https://webpack.js.org/concepts/)

[Webpack guides and documentation](https://webpack.js.org/guides/)

## webpack.config.js

- mode: set to development. For production see [webpack production guide](https://webpack.js.org/guides/production/)
- entry: single entry point set to ./src/index.js. If multiple entry points required see [output management guide](https://webpack.js.org/guides/output-management/)
- devtool: inline source map aids with errors finding errors, development only
- plugins:
  - HtmlWebpackPlugin is used for setting the template output html file [options](https://github.com/jantimon/html-webpack-plugin#options)
  - [CopyWebpackPlugin](https://webpack.js.org/plugins/copy-webpack-plugin/) is used to transfer images and fonts from the public folder to the dist folder. Uncomment the respective patterns when files are added to the images and fonts folders.
- output: settings for the filename and location of the build files. clean: true ensures old files from previous builds are deleted.
- module: rules: set up for [Babel](https://webpack.js.org/loaders/babel-loader/), css, images and fonts
- resolve: extensions: allows import of files with specifying (.js, .jsx) file extensions

## package.json

Because we will not be publishing to the npm registry:

- removed "main": "index.js"
- added "private": true

Scripts:

- "build": "webpack",
- "start": "webpack serve --open"

[Using webpack dev server](https://webpack.js.org/guides/development/#using-webpack-dev-server)

```
npm start
```
