---
sidebar_position: 5
---

# PluginAPI
no description

## Methods
### getPath
**getPath**(`id: string`, `fullPath: string`): `string`

Converts a file path to a path useable in the mdpkm interface, used for images and such.

### addLocaleBundle
**addLocaleBundle**(`lang: string`, `namespace: string`, `resources: Object`): `void`

Adds translation resources to the specified language and namespace.

#### Example
```js
// Adds a single translation string to the common namespace in English.
PluginAPI.addLocaleBundle('en', 'app.mdpkm.common', {
    'loaders.best_loader_ever': 'Best Loader Ever'
});
```