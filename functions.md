# Functions
Functions are anything that do not require a public route. They can be used in `commands`, on `deploy`, or for various other applications.

These files are `autoloaded` as `functions` in your `serverless` configuration.

## Create a function
Functions are created with the `lesswork` command.

```bash
lesswork make:function example
```

This creates the file `app/Http/Functions/exampleFunction.js`.

```js
const Kernel = require('lesswork-framework/src/Kernel');

module.exports = {
  handle: function () {
    return Kernel(arguments).handle(function () {
      State.callback(null, 'success');
    });
  },

  serverless: {
    exampleFunction: {
      handler: 'app/Http/Functions/exampleFunction.handle',
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
sls invoke local -f exampleFunction
```