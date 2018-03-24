# Providers
> tmp page

Providers are used to provide functionality to the framework.

More information from the [adonis docs](https://adonisjs.com/docs/3.2/ioc-container).

### Create a provider 

Make a provider in `app/Providers`

```js
'use strict';

const {
  ServiceProvider
} = require('adonis-fold');

class RequestProvider extends ServiceProvider {
  /**
   * Register method called by the Ioc container
   * to register the provider
   *
   * @method register
   *
   * @return {void}
   */
  * register() {
    this.app.bind('Lesswork/Request', function (app) {
      const Request = require('../Request');

      return new Request(use('State'));
    });
  }
}

module.exports = RequestProvider;
```

Register the new provider in `config/app.js` in the `providers` object:
```js
'lesswork-framework/Providers/RequestProvider',
```

And optional `aliases` object:
```js
Request: 'Lesswork/Request',
```

## Using a provider
Once installed you can use the provider with its `namespace` or `alias`.

```js
const request = use('Lesswork/Request');
// do something with request
```