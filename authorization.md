# Authorization
There are 2 authentication providers, `basic` and `jwt`.

These files are `autoloaded` as `functions` in your `serverless` configuration.

## Create the authorizer

The default authentication providers are created with the `lesswork` command.


```bash
lesswork make:auth
```

This creates the files `app/Http/Authentication/Basic.js` and `app/Http/Authentication/Jwt.js`.

```js
'use strict';

const app = require('../../../app');

const Basic = require('lesswork-framework/Authentication/Basic');

module.exports = {
  auth: function () {
    app(arguments, function () {
      new Basic().auth('test', 'test');
    });
  },

  config: {
    Authentication<%= name %>Basic: {
      handler: 'app/Http/Authentication/<%= name %>Basic.auth',
      documentation: {
        description: 'Basic Auth.'
      }
    }
};
```

## Using an authorizer
You can restirct routes with your newly created providers by editing your `app/Http/Routes` file and adding the following to its `config` setting under the `http` `event`.:

```js
config: {
      ...
      events: [{
        http: {
          ...
          authorizer: AuthenticationBasic
        }
      }]
    }
  }
```

You can also set it with the `defs` property:
```js
defs: {
  get: {
    authorizer: ‘AuthenticationBasic’
  }
},
```
