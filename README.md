# serviceworker-webpack-plugin

> Simplifies creation of a service worker to serve your webpack bundles.

## Installation

```sh
npm i serviceworker-webpack-plugin-martiuh
```
It's only compatible with webpack 1, 2, and 3

## The simple truth

First of all, this a simple fork, it only adds a feature necessary for a project I'm doing, which is `scriptURL` it can now be set manually and the service worker will try to be installed from that specific directory.
All the work is to oliviertassinari and the amazing [serviceworker-webpack-plugin](https://github.com/oliviertassinari/serviceworker-webpack-plugin/)

## API

### `ServiceWorkerWebpackPlugin(options)`

- `options`
 - `entry`, **required**, *string*:
Path to the actual service worker implementation.
 - `filename`, *string*, default `'sw.js'`:
Relative (from the webpack's config `output.path`) output path for emitted script.
 - `excludes`, *array*, default `['**/.*', '**/*.map']`:
Exclude matched assets from being added to the `serviceWorkerOption.assets` variable. (Blacklist)
 - `includes`, *array*, default `['**/*']`:
Include matched assets added to the `serviceWorkerOption.assets` variable. (Whitelist)
 - `publicPath`, *string*, default `'/'`:
Specifies the public URL address of the output files when referenced in a browser.
 - `outputDir`: If you want your serviceWorker file to be stored in a aditional folder inside webpack's output path.
 - `template`, *function*, default noop:
This callback function can be used to inject statically generated service worker.
It's taking a `serviceWorkerOption` argument and must return a promise.
- `transformOptions`, *function*:
The `jsonStats` key contains all the webpack build information.

### `runtime(options)`

- `options`: That's forwarded to the `options` argument of the
[`ServiceWorkerContainer.register()`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer/register) function.

## Credit

- The [offline-plugin](https://github.com/NekR/offline-plugin) package
was a great source of inspiration.
- The [html-webpack-plugin](https://github.com/ampedandwired/html-webpack-plugin)
package was also really helpful.

## The specs

- [Service Workers](https://w3c.github.io/ServiceWorker/)

## License

MIT
