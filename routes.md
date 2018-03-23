# Routes
Routes contain the `serverless` configuration and logic required to execute. By default routes will run your `controller` within the frameworks application.

You are not limited to using this framework since you can define any login for your route.

These files are `autoloaded` as `functions` in your `serverless` configuration.


## Create a route

Routes are created with the `work` command.

```bash
node work make:route HelloWorld
```

This creates the file `app/Http/Routes/HelloWorldRoutes.js`.

```js
'use strict';

const app = require('../../../bootstrap/app');

const HelloWorldController = require('../Controllers/HelloWorldController');

module.exports = {
  get: function (event, context, callback) {
    app(arguments, function () {
      new HelloWorldController().get();
    });
  },

  config: `HelloWorld:
    handler: app/Http/Routes/HelloWorldRoute.get
    events:
      - http:
          path: HelloWorld
          method: get
          cors: true
          documentation:
            description: "Returns Hello World!"
            tags:
              - "HelloWorld"`
};
```

You can define multiple methods per route file.
```js
...
  get: function (event, context, callback) {
    app(arguments, function () {
      new HelloWorldController().get();
    });
  },
  post: function (event, context, callback) {
    app(arguments, function () {
      new HelloWorldController().post();
    });
  },
...
```

You would also need to add the configuration required for the additional route.
```js
...
  config: `
    HelloWorldGet:
        handler: app/Http/Routes/HelloWorldRoute.get
        events:
        - http:
            path: HelloWorld
            method: get
            cors: true
    HelloWorldPost:
        handler: app/Http/Routes/HelloWorldRoute.post
        events:
        - http:
            path: HelloWorld
            method: post
            cors: true
  `
  ...            
```