exp-angular-skeleton
===

Expansive Angular skeleton plugin.

This provides:

 * Angular
 * Configuration for Expansive plugins:
    * [exp-css](https://github.com/embedthis/exp-css) for CSS files
    * [exp-less](https://github.com/embedthis/exp-less) for Less files
    * [exp-js](https://github.com/embedthis/exp-js) for script files
    * [exp-html](https://github.com/embedthis/exp-html) for HTML minification
 * Default layout 
 * Default partials 
 * Starter home page

### To install:

    pak install exp-angular-skeleton

### Description

The Angular skeleton is a starter skeleton for Expansive using [Angular](http://angularjs.org). It provides a default layout, partial pages and is configured to use Less stylesheets. Extensions are installed to process less stylesheets and minify scripts.

The skeleton is configured for a "debug" and "release" mode of operation via the "pak.mode" property in package.json. By default, debug mode will disable minification and optimization of scripts.

### Configure

#### expansive.json

* less.dependencies &mdash; Explicit map of dependencies if not using "stylesheet". 
* less.enable &mdash; Enable the less service to process less files.
* less.files &mdash; Array of less files to compile.
* less.stylesheets &mdash; Primary stylesheet to update if any less file changes.
    If specified, the "dependencies" map will be automatically created. 
* css.prefix &mdash; Enable running autoprefixer on CSS files to handle browser specific extensions.
* css.minify &mdash; Enable minifying CSS files.
* js.compress &mdash; Enable compression of script files.
* js.dotmin &mdash; Set '.min.js' as the output file extension after minification. Otherwise will be '.js'.
* js.enable &mdash; Enable minifying script files.
* js.files &mdash; Array of files to minify. Files are relative to 'source'.
* js.mangle &mdash; Enable optimization by mangling of Javascript variable and function names.
* js.minify &mdash; Enable minification of Javascript variable and function names.
* js.usemin &mdash; Enable pre-minified scripts if available.

```
{
    services: {
        'less': {
            enable: true,
            stylesheets:  [ 'css/all.css' ],
            dependencies: { 'css/all.css.less' : '**.less' },
            files: [ '!**.less', '**.css.less' ]
        },
        'css': {
            prefix: true,
            minify: true,
        },
        'js': {
            enable:     true,
            files:      null,
            compress:   true,
            mangle:     true,
            dotmin:     false,
        }
    }
}
```
### Get Pak from

[https://embedthis.com/pak/](https://embedthis.com/pak/)
