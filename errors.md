# Errors & Exceptions
This feature is provided by [adonis errors](https://adonisjs.com/docs/3.2/error-and-exceptions) that uses [node-exceptions](https://www.npmjs.com/package/node-exceptions).

Throw a new exception:
```js
throw new EXP.HttpException('Page not found', 404);
```


## Error Event
By default all exceptions will return a response.failure() to ensure your route properly terminates.

Catch your own exceptions to control their response.

## 500
500 errors will log to the console in order to show up in your AWS logs.
