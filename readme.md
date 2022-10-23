## Javascript tooling

### webpack

#### why?

1. buldles the code
2. it supports the module structure

#### how to use?

```
npm install --save-dev webpack webpack-cli
```

package.json

```json
"scripts": {
    ...scripts,
    "build": "webpack"
}
```

```
npm run build -- --mode development
```

#### how to configure ?

webpack.config.js

```js
module.exports = {
  entry: "./src/index.js",
  output: {
    path: "",
    filename: "",
  },
};
```

### Babel

#### why?

1. Make modern javascript features run on the older browsers

#### how to use?

```
npm install --save-dev webpack webpack-cli
```

#### configure webpack to load javascript files through babel with Babel-loader

```
npm i -D @babel/cli @babel/core @babel/preset-env babel-loader
```

webpack.config.js
```javascript
module.exports = {
  mode: 'production',
  entry: './src/index.js',
  output: {
    path: path.join(__dirname, 'dist'),
    filename: 'app.bundle.js'
  },
  module: {
    rules: [
      {
        test: /\.js$/,
        loader: 'babel-loader',
        exclude: /node_modules/,
        options: {
          presets: ['@babel/preset-env']
        }
      }
    ]
  }
}
```

### Using Babel with React

```
npm i -D @babel/preset-react
```

webpack.config.js

```javascript
module.exports = {
  ...module.exports,
  module: {
    rules: [
      {
        ...rules,
        options: {
          presets: ["@babel/preset-env", "@babel/preset-react"],
        },
      },
    ],
  },
};
```

#### using HTML Webpack plugin which will create a index.html and inject the app.buldel.js init

```
npm i -D html-webpack-plugin
```

webpack.config.js

```javascript
const HtmlWebpackPlugin = require("html-webpack-plugin");

module.exports = {
  ...module.exports.module,
  plugins: [new HtmlWebpackPlugin()],
};
```

### separate webpack configuration for prod and dev using webpack-merge 

```
npm i -D webpack-merge
```

### using webpack-dev-serve to serve the bundle in development

```
npm i -D webpack-dev-server
```

package.json
```javascript
scripts: {
     "dev": "webpack-dev-server --config webpack.config.dev.js",
}
```

setting port 
webpack.config.js
```javascript
{
  mode: 'development',
  devServer: {
    port: 9000
  }
}
```
