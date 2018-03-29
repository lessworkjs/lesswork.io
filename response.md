# Response
Access with the globals `Response` and `response`, or injected with `use('Response')`.

```js
response.success() // 204 ok 

# is the same as 

Response.success() // 204 ok 
```

## success([message], [code])
If no argurments are provided a default 204 ok will be returned.

```js
response.success(); // 204 ok 
```

Provide the optional message and code to adjust the output.

```js
response.success({ works: true}, 401); // 204: ok 
```


## error([message], [code])
If no message or code is defined a 500 Internal Server Error will be thrown.

Errors are transformed with the `ErrorTransformer`.

```js
response.error('fail'); // 500: fail
```


## successOrError(failure, [message], [code])
If `failure` is `null` or `false` a success will be returned.

```js
response.successOrError('fail'); // 500: fail

response.successOrError(null); // 204: ok
```