# Functions
Functions are anything that do not require a public route. They can be used in `commands`, on `deploy`, or for various other applications.

These files are `autoloaded` as `functions` in your `serverless` configuration.

## Create a function
Functions are created with the `lesswork` command.

```bash
lesswork make:function HelloWorld
```

This creates the file `app/Http/Functions/HelloWorldFunction.js`.

```js
'use strict';

const Route = require('lesswork-framework/src/Route');

module.exports = {
  handle: function ()) {
    Route(arguments, function () {
      state.callback(null, 'success');
    });
  },

  serverless: {
    FunctionHelloWorld: {
      handler: 'app/Http/Functions/HelloWorldFunction.handle',
    }
  }
};
```

## Executing a function
You can execute functions with the `serverless` command.
```bash 
sls invoke -f <function>
# or locally
sls invoke local -f <function>
```

Example:
```bash
sls invoke local -f FunctionHelloWorld
```