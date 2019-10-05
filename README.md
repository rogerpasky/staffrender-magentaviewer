# staffrender-magentaviewer
An example of `magenta-js/music/src/core/viewer` derived Visualizer using [staffrender](https://github.com/rogerpasky/staffrender) library to display music score on browsers through SVG.

This is an *alpha version* which will serve to two purposses:

* To teach how to develop and compile some other `magenta-js/music/src/core/viewer` derived classes with different technologies (like `three.js` and the like).
* To act as stage to test the contribution of `staff_svg_visualizer.ts` to `magenta-js/music/src/core/viewer` as a first class citizen of the Magenta ecosystem. This will allow testing it avoiding circular dependencies.

## Installing and running
To try it out, you must follow this four simple steps:

1. Clone the repo and `mv` to the root directory where `package.json` is.
2. Do `yarn install` to install all `npm` dependencies. Do install yarn through `brew install yarn` (in Mac), or similar, if you didn't it before.
3. Do `yarn build` to compile the TypeScript code to JavaScript.
4. Do `yarn serve` to launch a local web server you can access with your browser in `localhost:8080`

## Limitations and known issues

* Due `VisualizerConfig` has not been exported from @magenta package it has been needed to be re-declared it until exportation PR gets accepted in master.
* `tsconfig.json` and `webpack.config.js` could have extra parameters which will be excluded in future versions.
* `tsconfig.json` forces the compilation to the `ES6`version (ECMAScript 2015, a precise variant of javascript), avoiding `ES5` for simplicity sake. Magenta currently deals with several compiling versions.
* `webpack.config.js` forces the creation of reference maps linking original .ts to compiled .js versions in order to allow debugging (for instance through Chrome inspector). If you want to avoid it in final version, remove line `devtool: 'inline-source-map'`.
* There are no known issues, but the uncompleted features of [staffrender](https://github.com/rogerpasky/staffrender). They are all welcome in the repo's issue placeholder.
