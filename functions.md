# Functions
Functions can be anything that does not require a public route. They can be used in `commands`, on `deploy` or for various other applications.

These files are `autoloaded` as `functions` in your `serverless` configuration.

## Create a function
Functions are created with the `work` command.

```bash
node work make:function HelloWorld
```

This creates the file `app/Http/Functions/HelloWorldFunction.js`.

```js
'use strict';

const app = require('../../../bootstrap/app');

module.exports = {
  handle: function (event, context, callback) {
    app(arguments, function () {
      callback(null, 'success');
    });
  },

  config: `FunctionHelloWorld:
    handler: app/Http/Functions/HelloWorldFunction.handle`
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