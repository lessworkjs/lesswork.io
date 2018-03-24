# Routes
Routes contain the `serverless` configuration and logic required to execute. By default routes will run your `controller` within the frameworks application.

You are not limited to using this framework since you can define any logic for your route.

These files are `autoloaded` as `functions` in your `serverless` configuration.


## Create a route

Routes are created with the `work` command.

```bash
node work make:route HelloWorld
```

This creates the file `app/Http/Routes/HelloWorldRoute.js`.

```js
'use strict';

const app = require('../../../bootstrap/app');

module.exports = {
  get: function () {
    app(arguments, 'App/Http/Controllers/HelloWorldController@get');
  },

  // OPTIONAL CONFIG
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
  },
...
```

You would also need to add the OPTIONAL configuration required for the additional route.
```js
...
  config: {
    HelloWorldGet: {
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
    },
    HelloWorldPost: {
      handler: 'app/Http/Routes/HelloWorldRoute.post',
      events: [{
        http: {
          path: 'HelloWorld',
          method: 'post',
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
  ...            
```