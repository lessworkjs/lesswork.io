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
const Route = require('lesswork-framework/src/Route');

module.exports = {
  get: function () {
    return new Route(arguments).get('helloWorld', 'App/Http/Controllers/HelloWorldController@get').handle();
  },
};
```

You can define multiple methods per route file.
```js
...
  get: function () {
    return new Route(arguments).get('helloWorld', 'App/Http/Controllers/HelloWorldController@get').handle();
  },
  post: function () {
    return new Route(arguments).post('helloWorld', 'App/Http/Controllers/HelloWorldController@post').handle();
  }
...
```

## Route options
You can your routes middleware and authorizer.

### auth(string)
Define the authorizer.
```js 
Route(arguments).get(...).auth('AuthenticationBasic').handle();
```

### middleware(middleware)
The paramater can be a `string` or `array` of `strings`.
```js 
Route(arguments).get(...).middleware('MyMiddleware').handle();
```


## Documentation options
### docs(object)
Define the entire documentation object.
```js 
Route(arguments).get(...).docs({
  description: 'My api rocks!',
  tags: ['tag'],
  ...
}).handle();
```

### description(string)
Define the documentation description.
```js 
Route(arguments).get(...).description('My api rocks!').handle();
```

### requestModels(string|object)
Define the `requestModels` required for the route, if string `application/json` will be used.
```js 
Route(arguments).get(...).requestModels([ 'application/json': 'myRequestModel']).handle();
```


### methodResponses(string|object)
Define the `methodResponses` that the route uses.
```js 
Route(arguments).get(...).methodResponses([ 
  '${self:custom.commonModelSchemaFragments.MethodResponse500Json}',
  '${self:custom.commonModelSchemaFragments.MethodResponse400Json}',  
]).handle();
```


### tags(string|object)
Define the tags to be used.

### Route(arguments).method(path, callback, options = {})
> `.handle()` is required at the end to trigger the route. 

`path` is the route you will access.

`callback` can be named based, a function, or required.

`options` changes your serverless `events[0].http` configuration.

#### The following methods are supported:

#### get 
```js 
Route(arguments).get(...).handle();
```

#### post
```js 
Route(arguments).post(...).handle();
```

#### put
```js 
Route(arguments).put(...).handle();
```

#### patch
```js 
Route(arguments).patch(...).handle();
```

#### delete
```js 
Route(arguments).delete(...).handle();
```

#### options
```js 
Route(arguments).options(...).handle();
```

#### connect
```js 
Route(arguments).connect(...).handle();
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