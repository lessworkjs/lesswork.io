# Authorization
> WIP 

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

const Kernel = require('lesswork-framework/src/Route/Kernel');

const Basic = require('lesswork-framework/src/Authentication/Basic');

module.exports = {
  auth: function () {
    Kernel(arguments, function () {
      new Basic().auth('test', 'test');
    });
  },

  serverless: {
    AuthenticationBasic: {
      handler: 'app/Http/Authentication/Basic.auth',
      documentation: {
        description: 'Basic Auth.'
      }
    }
  }
};
```

## Using an authorizer
You can autorize routes with your newly created providers by editing your `routes` file and adjusting its serverless configuration.

```js
...
return Route(arguments).auth('AuthenticationBasic').get('helloWorld', 'App/Http/Controllers/testController@get');
# Is the same as
return Route(arguments).get('helloWorld', 'App/Http/Controllers/testController@get', {
  authorizer: 'AuthenticationBasic'
});
...
```