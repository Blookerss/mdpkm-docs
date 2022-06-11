---
sidebar_position: 2
---

# API
Provides useful methods for mdpkm's functionality,
most of this class will not be documented.

Accessible as a global variable in the plugin environment.

## Methods
### get
**get**(`id: string`): Object

Returns a registered API.

#### Examples
```js title="Getting a project from Modrinth"
const data = await API.get('modrinth').getProject('fabric-api');
console.log(data);
```

### makeRequest
**makeRequest**(`url: string`, `options:` [RequestOptions](interfaces/requestoptions)): [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)<[WebResponse](interfaces/webresponse)>

Makes a request to the specified URL with the provided options.

#### Examples
```js title="Sending a GET request"
const data = await API.makeRequest('https://httpbin.org/get');
console.log(data);
```
```js title="Sending a POST request"
const data = await API.makeRequest('https://httpbin.org/get', {
    // https://tauri.studio/v1/api/js/classes/http.Body
    // Yes, http is defined in the plugin environment globally!
    body: http.Body.json({
        message: 'hello!'
    }),
    method: 'POST'
});
console.log(data);
```