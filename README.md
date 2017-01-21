# Static Lite

Static Lite is a minimalist configuration for generating static sites, powered entirely by NPM scripts.

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/BrandonRomano/static-lite)

## Getting Started

Clone down this repo, then run the following inside:

```
npm i && npm run watch
```

## NPM Script Usage

Here is the usage of the NPM scripts, assuming you haven't changed them.

> There are additional lower-level npm scripts that I won't describe here.  You will have to dig into the [NPM Scripts](https://github.com/BrandonRomano/static-lite/blob/master/package.json#L36-L48) to understand their usage.

### watch

To compile, start a server, and watch your files for changes, run the following command:

```sh
npm run watch
```

### compile

To compile your code in `src` to browser friendly html/css/js, run the following command:

```sh
npm run compile
```

### serve

To start a local server displaying the compiled public directory, run the following command:

```sh
npm run serve
```

### cache:clear

To clear the cache that stores the stdout of the `src/data` file, run the following command:

```sh
npm run cache:clear
```

You might want to combine this with watch, so you clear the cache every time you restart the watcher:

```
npm run cache:clear && npm run watch
```

> If this is a common use case for you, you might want to add a new NPM Script that does exactly the above.

## Code Structure

All of the code that you will be interested in is in the `src` directory.

In its most basic form, the `src` directory will look like this:

```
src/
├── assets
├── css
│   └── index.styl
├── data
├── html
│   └── pages
│       └── index.pug
└── js
    └── index.js
```

The `src` directory is the directory that files are pulled from to generate your static site in the `public` directory.

### src/data

The `src/data` file in which you can prepare data to pass to our HTML compiler.

If you note, this file has no extension.  This is intentional, as there is no need mandate this file be written in any specific language.  My example uses Node to prepare the data, and I use a [shebang](https://github.com/BrandonRomano/static-lite/blob/master/src/data#L1) to denote my interpreter.

You _must_ output your final JSON Object to stdout.

### src/assets

The `src/assets` directory is the place where you would want to put your assets (think .jpg, .svg, etc).

You can maintain any subfolder organization in this folder, as assets are [simply copied](https://github.com/BrandonRomano/static-lite/blob/master/package.json#L45) into the `public/assets` directory when compiled.

### src/css

The `src/css` directory is the place where we are going to store our stylus files.

There must be an `index.styl` file present in this directory, as we are [specifically compiling that file](https://github.com/BrandonRomano/static-lite/blob/master/package.json#L43).  To have multiple stylus files, you must take advantage of Stylus's [@import or @require](http://stylus-lang.com/docs/import.html) feature.

The `src/css/index.styl` file is compiled down to `public/index.css`.

### src/html

The `src/html` directory is the place where we will store our Pug files.

There must be a `pages` directory present inside of this directory, as we are [compiling the src/html/pages directory](https://github.com/BrandonRomano/static-lite/blob/master/package.json#L44).  We are specifically compiling the `pages` directory, so you are safe to use templates / utility files outside of the `pages` directory.

The `src/html/pages/` directory is compiled directly into the `public/` directory.  You must be mindful of this fact when referencing assets in your HTML, as there is no magic that goes and updates your local references during the compile process.

### src/js

The `src/js` directory is the place where we will store our Javascript ([es2015, stage-2](https://github.com/BrandonRomano/static-lite/blob/master/package.json#L13-L16)) files.

There must be an `index.js` file present in this directory, as we are [specifically compiling that file](https://github.com/BrandonRomano/static-lite/blob/master/package.json#L42).  To have multiple Javascript files, you must take advantage of Javascripts `require` or `import`.

## License

[MIT](./LICENSE.md)
