# Errors & Exceptions
> WIP: needs updating for node 8 version.

This feature is provided by [adonis exceptions](https://adonisjs.com/docs/4.1/exceptions) that uses [node-exceptions](https://www.npmjs.com/package/node-exceptions).

Throw a new exception:
```js
throw new EXP.HttpException('Page not found', 404);
```


## Error Event
By default all exceptions will return a response.failure() to ensure your route properly terminates.

Catch your own exceptions to control their response.

## 500
500 errors will log to the console in order to show up in your AWS logs.
