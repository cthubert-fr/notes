---
layout: default
title: "Environnement - Typescript"
permalink: /formation/typescript/env/
lang: fr
my_menu: menu-typescript.html
---

## Environnement

* Installer **nodejs**.
* Installer le compiler Typescript : `npm install -g typescript`.

### Vérifier l'installation

```
node -v
tsc -v
```

### Configuration du compilateur

#### Compilation

* Compiler le fichier avec le même nom : `tsc script.ts`
* Compiler le fichier avec un nom différents : `tsc script.ts --out output-script.js`
* Compiler en continu : `tsc script.ts -w`

#### Générer le fichier de configuration de Typescript

```
tsc --init
```

* Modifier le répertoire source et destination du code généré : `rootDir` et `outDir`.
* `exclude` permet d'exclure des fichiers de la compilation.
* `include` permet de cibler les fichiers qui doivent être compilés.
* `lib` par défaut comprend "dom", "es6", "DOM.Iterable" et "ScriptHost".

##### Autres options de configuration

* `allowJs` compile les fichiers Javascript.
* `checkJs` afficher les erreurs des fichiers Javascript.

### npm

#### Initialisation

```
npm init
```

#### Installation de lite-server

```
npm install lite-server --save
```

##### Démarrer lite-server

Dans package.json :

```json
"scripts": {
    "start": "lite-server"
}
```

Pour lancer le serveur il suffit maintenant de faire : `npm start`.

#### Webpack

##### Installation de webpack

`npm install webpack webpack-cli typescript ts-loader --save-dev`

##### Configuration de webpack

Dans webpack.config.js :

```js
var path = require("path");
module.exports = {
    entry: "./src/index.ts",
    output: {
        filename: "bundle.js",
        path: path.resolve(__dirname, "public")
    },
    devtool: "inline-source-map",
    module: {
        rules: [
            {
                test: /.ts$/,
                use: "ts-loarder",
                exclude: /node_modules/,
            },
        ],
    },
    resolve: {
        extensions: [".ts", ".js"]
    }
};
```

Note : pour source map il est nécessaire de l'activer dans tsconfig.json.

Lancer webpack :
```
./node_modules/.bin/webpack --mode development
```

Ou dans package.json :

```json
"scripts": {
    "build": "webpack --config webpack.config.js --mode development"
}
```

Puis : `npm run build`

##### Webpack dev server

```
npm install webpack-dev-server --save-dev
```

Dans package.json :

```json
"scripts": {
    "build": "webpack serve --mode development --open"
}
```

Dans webpack.config.js :

```js
var path = require("path");
module.exports = {
    mode: "development",
    entry: "./src/index.ts",
    output: {
        filename: "bundle.js",
        path: path.resolve(__dirname, "public")
    },
    devServer: {
        contentBase: path.resolve(__dirname, "public"),
        compress: true,
        port: 8080
    },
    devtool: "inline-source-map",
    module: {
        rules: [
            {
                test: /.ts$/,
                use: "ts-loarder",
                exclude: /node_modules/,
            },
        ],
    },
    resolve: {
        extensions: [".ts", ".js"]
    }
};
```

##### Webpack en production

Installer clean-webpack-plugin : `npm install --save-dev clean-webpack-plugin`

Dupliquer le fichier webpack.config.js et le nommer par exemple : webpack.config.prod.js.

Dans webpack.config.prod.js :

```js
var path = require("path");
var cleanPlugin = require("clean-webpack-plugin");
module.exports = {
    mode: "production",
    entry: "./src/index.ts",
    output: {
        filename: "bundle.js",
        path: path.resolve(__dirname, "public")
    },
    devtool: false,
    module: {
        rules: [
            {
                test: /.ts$/,
                use: "ts-loarder",
                exclude: /node_modules/,
            },
        ],
    },
    resolve: {
        extensions: [".ts", ".js"]
    },
    plugins: [new cleanPlugin.CleanWebpackPlugin{
        dry: true,
        verbose: true,
        cleanOnceBeforeBuildPatterns: ['**/*', '!static-files*'],
    })],
};
```

Dans package.json :

```json
"scripts": {
    "build": "webpack --config webpack.config.prod.js --mode production"
}
```
