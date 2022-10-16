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
    entry: './src/index.js',
    output: {
        path: '',
        filename: ''
    }
}
```


