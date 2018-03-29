# Request
Access with the global `Request` or injected with `use('Request')`.




###  all()
Returns  `body` and `queryStringParameters` mereged into one.
```js
Request.all();
```

### input([hash])
Returns hash from or all `body`.
```js
Request.input();
```

### get([hash])
Returns hash from or all `queryStringParameters`.
```js
Request.get();
```

### headers([hash])
Returns hash from or all `headers`.
```js
Request.headers();
```

### context([hash])
Returns hash from or all `requestContext`.
```js
Request.context();
```

### method()
Returns the states `httpMethod`.
```js
Request.method();
```