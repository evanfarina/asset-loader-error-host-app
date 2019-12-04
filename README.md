This app demonstrates a fatal error that is thrown when a host app which contains an engine depends on an external addon that relies on, and extends from, ember-asset-loader.

**Repro steps**

1. Create a local directory called repro-app
2. cd repro-app
3. git clone https://github.com/evanfarina/asset-loader-error-host-app.git (the host app)
4. git clone https://github.com/evanfarina/asset-loader-error-ext-addon.git (the external addon)
5. npm install  - note: The host app's package.json contains a relative path to the external addon's directory.
6. ember serve
7. Click link that is output on page or visit the `basic-engine` route.
