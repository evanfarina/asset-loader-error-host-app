This app demonstrates a fatal error that is thrown when a host app which contains an engine depends on an external addon that relies on, and extends from, ember-asset-loader.

**Repro steps**

1. Create a local directory called repro-app
2. cd repro-app
3. git clone https://github.com/evanfarina/asset-loader-error-host-app.git (the host app)
4. git clone https://github.com/evanfarina/asset-loader-error-ext-addon.git (the external addon)
5. npm install  - note: The host app's package.json contains a relative path to the external addon's directory.
6. ember serve
7. Click link that is output on page or visit the `basic-engine` route.


**Error**

You will see the below error in your console.

```
rsvp.js:26 Uncaught Error: Failed to load asset manifest. For browser environments, verify the meta tag with name "basic-engine/config/asset-manifest" is present. For non-browser environments, verify that you included the node-asset-manifest module.
    at Module.callback (asset-manifest.js:23)
    at Module.exports (loader.js:106)
    at Module._reify (loader.js:143)
    at Module.reify (loader.js:130)
    at Module.exports (loader.js:104)
    at requireModule (loader.js:27)
    at r (loader.js:176)
    at resolveInitializer (index.js:10)
    at registerInstanceInitializers (index.js:33)
    at loadInitializers (index.js:69)
```
