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
    return new Route(arguments).get('helloWorld', 'App/Http/Controllers/HelloWorldController@get');
  },
};
```

You can define multiple methods per route file.
```js
...
  get: function () {
    return new Route(arguments).get('helloWorld', 'App/Http/Controllers/HelloWorldController@get');
  },
  post: function () {
    return new Route(arguments).post('helloWorld', 'App/Http/Controllers/HelloWorldController@post');
  }
...
```

## Route options
You can your routes middleware and authorizer.

### auth(authorizer)
```js 
Route(arguments).auth('AuthenticationBasic').get(...);
```

### middleware(middleware)
The paramater can be a `string` or `array` of `strings`.
```js 
Route(arguments).middleware('MyMiddleware').get(...);
```


### Route(arguments).method(path, callback, options = {})
`path` is the route you will access, ie: / or /welcome.

`callback` can be named based, a function, or required.

`options` changes your serverless `events[0].http` configuration.

#### The following methods are supported:

#### get 
```js 
Route(arguments).get(...);
```

#### post
```js 
Route(arguments).post(...);
```

#### put
```js 
Route(arguments).put(...);
```

#### patch
```js 
Route(arguments).patch(...);
```

#### delete
```js 
Route(arguments).delete(...);
```

#### options
```js 
Route(arguments).options(...);
```

#### connect
```js 
Route(arguments).connect(...);
```



## Kernel Configuration
`functions` and `authorizers` use the Kernel command instead of the Route.


The `Kernel` function has several options.

```js
# Callbacks
Kernel(arguments).handle(function () {

});

# Define the path manually
Kernel(arguments).handle('path', 'App/Http/Controllers/HelloWorldController@get');

# Define configuration
Kernel(arguments).handle('App/Http/Controllers/HelloWorldController@get', {
  documentation: {
    description: 'Oh yeah!
  }
});

# Define configuration and path
Kernel(arguments).handle('path', 'App/Http/Controllers/HelloWorldController@get', {
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