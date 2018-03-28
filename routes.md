# Routes
Routes contain the `serverless` configuration and logic required to execute. By default routes will run your `controller` within the frameworks application.

You are not limited to using this framework since you can define any logic for your route.

These files are `autoloaded` as `functions` in your `serverless` configuration.

`serverless` is a reserved variable. 

## Create a route

Routes are created with the `lesswork` command.

```bash
lesswork make:route HelloWorld
```

This creates the file `app/Http/Routes/HelloWorld.js`.

```js
'use strict';

const Route = require('lesswork-framework/src/Route');

module.exports = {
  get: function () {
    return Route(arguments).get('helloWorld', 'App/Http/Controllers/HelloWorldController@get');
  },
};
```

You can define multiple methods per route file.
```js
...
  get: function () {
    return Route(arguments).get('helloWorld', 'App/Http/Controllers/HelloWorldController@get');
  },
  post: function () {
    return Route(arguments).post('helloWorld', 'App/Http/Controllers/HelloWorldController@post');
  }
...
```

## Route options

### auth
### middleware 


### get 
### post 
### put
### patch
### delete 
### options
### connect



## Kernel Configuration
`functions` and `authorizers` use the Kernel command instead of the Route.


The `Kernel` function has several options.

```js
# Callbacks
Kernel(arguments, function () {

});

# Define the path manually
Kernel(arguments, 'path', 'App/Http/Controllers/HelloWorldController@get');

# Define configuration
Kernel(arguments, 'App/Http/Controllers/HelloWorldController@get', {
  documentation: {
    description: 'Oh yeah!
  }
});

# Define configuration and path
Kernel(arguments, 'path', 'App/Http/Controllers/HelloWorldController@get', {
  documentation: {
    description: 'Oh yeah!
  }
});
```


 ###  Provide your own config
  You can define the entire config with the `serverless` option.

  This is used for `authentication` and `function` routes.

  > Each route will need to be defined.

  ```js
  serverless: {
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