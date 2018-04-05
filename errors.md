# Errors & Exceptions

## Generic Exceptions
This feature uses [adonis-generic-exceptions](https://github.com/adonisjs/adonis-generic-exceptions).

Throw a new exception:
```js
const { InvalidArgumentException } = require('@adonisjs/generic-exceptions')

const message = 'Model.create requires an object'
const status = 400
const code = 'E_INVALID_ARGUMENT'

throw new InvalidArgumentException(message, status, code)
```

## Custom exceptions
Create `app/Exceptions/CustomException.js`

```js
const GE = require('@adonisjs/generic-exceptions')

class CustomException extends GE.LogicalException {
}

module.exports = CustomException
```

Use it

```js
const CustomException = use('App/Exceptions/CustomException')

throw new CustomException(message, status, code)
```


## Error Event
By default all exceptions will return a response.failure() to ensure your route properly terminates.

Catch your own exceptions to control their response.

## 500
500 errors will log to the console in order to show up in your AWS logs.
