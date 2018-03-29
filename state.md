# State
State is used to hold the values provided by serverless when the application starts, `event`, `context`, and `callback`.

Access with the global `State` or injected with `use('State')`.


## callback
`callback()`

> Your application may continue running after, please use `Response` instead.

Returns the callback function provided by serverless.

```js 
State.callback(null 'success');
```


## event
`event([hash])`

Returns the event provided by serverless.

If hash is provided and part of the event it will be returned.

If hash is `body` an object will be returned.

## context
`context([hash])`

Returns the context object.

If hash is provided and part of the context it will be returned.