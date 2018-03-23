# Authorization
There are 2 authentication providers, `basic` and `jwt`.

These files are `autoloaded` as `functions` in your `serverless` configuration.

## Create the authorizer

The default authentication providers are created with the `work` command.


```bash
node work make:auth
```

This creates the files `app/Http/Authentication/Basic.js` and `app/Http/Authentication/Jwt.js`.

```js
'use strict';

const app = require('../../../app');

const Basic = require('lesswork-framework/Authentication/Basic');

module.exports = {
  auth: function (event, context, callback) {
    app(arguments, function () {
      new Basic().auth('test', 'test');
    });
  },

  config: `AuthenticationBasic:
    handler: app/Http/Authentication/Basic.auth
    documentation:
      description: "Basic Auth Handler"`
};
```

## Using a authorizer
You can restirct routes with your newly created providers by editing your `app/Http/Routes` file and adding the following to its `config` setting:

```js
authorizer: AuthenticationBasic
```

Example:
```js
...
 - http:
    path: HelloWorld
    method: get
    cors: true
    authorizer: AuthenticationBasic
    ...
```
