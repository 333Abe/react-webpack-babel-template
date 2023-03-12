# OVERVIEW

Create a React web app with a webpack bundler.

Assumes use of VScode with [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) plugin. If your set-up is different use [webpack-dev-server](https://webpack.js.org/guides/development/#using-webpack-dev-server) instead of watch mode.

---

# REACT

npm set-up used:

```
npm install react react-router-dom
```

If routing is required consider installing [React Router](https://reactrouter.com/en/main):

```
npm react-router-dom
```

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
npm install --save-dev webpack webpack-cli style-loader css-loader html-webpack-plugin babel-loader
```

[Webpack is used to produce a static module from your code](https://webpack.js.org/concepts/)

[Webpack guides and documentation](https://webpack.js.org/guides/)

## webpack.config.js

- mode: set to development. For production see [webpack production guide](https://webpack.js.org/guides/production/)
- entry: single entry point set to ./src/index.js. If multiple entry points required see [output management guide](https://webpack.js.org/guides/output-management/)
- devtool: inline source map aids with errors finding errors, development only
- plugins: HtmlWebpackPlugin is used for setting the template output html file [options](https://github.com/jantimon/html-webpack-plugin#options)
- output: settings for the filename and location of the build files. clean: true ensures old files from previous builds are deleted.
- module: rules: set up for [Babel](https://webpack.js.org/loaders/babel-loader/), css, images and fonts

## package.json

Because we will not be publishing to the npm registry:

- removed "main": "index.js"
- added "private": true

Scripts:

- "build": "webpack",
- "watch": "webpack --watch"

[Using Watch Mode](https://webpack.js.org/guides/development/#using-watch-mode)

```
run npm watch
```

Used in conjuction with the VScode add-on '[Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)' will automatically refresh the browser with any changes made to watched files. Alternatively you can use [webpack-dev-server](https://webpack.js.org/guides/development/#using-webpack-dev-server)
