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

const Route = require('lesswork-framework/src/Route');

const Basic = require('lesswork-framework/Authentication/Basic');

module.exports = {
  auth: function () {
    return Route(arguments, function () {
      new Basic().auth('test', 'test');
    });
  },

  serverless: {
    Authentication<%= name %>Basic: {
      handler: 'app/Http/Authentication/<%= name %>Basic.auth',
      documentation: {
        description: 'Basic Auth.'
      }
    }
};
```

## Using an authorizer
You can restirct routes with your newly created providers by editing your `app/Http/Routes` file and adjusting its serverless configuration.

```js
Route(arguments, 'App/Http/Controllers/HelloWorldController@get', {
  authorizer: AuthenticationBasic
});
```