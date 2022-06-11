---
sidebar_position: 4
---

# PluginSystem
The PluginSystem is a extendable class that integrates with mdpkm.

## Methods
### addLoader
**addLoader**(`id: string`, `options:` [LoaderOptions](../interfaces/loaderoptions)): `string`

Adds a custom loader to mdpkm, along with an entry on the loader list.

#### Examples
[Custom Loader example](https://github.com/Blookerss/mdpkm-example-plugin/blob/main/src/custom-loader.js)