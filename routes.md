# Routes
Routes contain the `serverless` configuration and logic required to execute. By default routes will run your `controller` within the frameworks application.

You are not limited to using this framework since you can define any logic for your route.

These files are `autoloaded` as `functions` in your `serverless` configuration.

`defs` and `config` are reserved variables. 

## Create a route

Routes are created with the `lesswork` command.

```bash
lesswork make:route HelloWorld
```

This creates the file `app/Http/Routes/HelloWorldRoute.js`.

```js
'use strict';

const app = require('../../../bootstrap/app');

module.exports = {
  get: function () {
    app(arguments, 'App/Http/Controllers/HelloWorldController@get');
  }
};
```

You can define multiple methods per route file.
```js
...
  get: function () {
    app(arguments, 'App/Http/Controllers/HelloWorldController@get');
  },
  post: function () {
    app(arguments, 'App/Http/Controllers/HelloWorldController@post');
  }
...
```

## Route Configuration
You can configure routes in 3 ways. 

### Automatically
This is the default method for route configruration.

###  With defs
You can customize the configruration of each method with `defs`:
```js
defs: {
  get: {
    authorizer: 'AuthenticationBasic'
  }
},
  ```

 ###  With config
  You can define the entire config with the `config` option.
  > Each route will need to be defined.

  ```js
  config: {
    HelloWorld: {
      handler: 'app/Http/Routes/HelloWorldRoute.get',
      events: [{
        http: {
          path: 'HelloWorld',
          method: 'get',
          cors: true,
          documentation: {
            description: 'HelloWorld Route.',
            tags: [
              'HelloWorld'
            ]
          }
        }
      }]
    }
  }
  ```