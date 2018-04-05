# Controllers
Controllers contain the code to be executed by your routes.

## Create a controller

Controllers are created with the `lesswork` command.


```bash
lesswork make:controller HelloWorld
```

This creates the file `app/Http/Controllers/HelloWorldController.js`.

```js
class HelloWorldController extends require('lesswork-framework/Controller') {
  get() {
    Response.success({
      hello: 'world'
    });
  }
}

module.exports = HelloWorldController;
```

You can also use injection...
```js
...
  static get inject() {
    return ['Response'];
  }

  constructor(Response) {
    this.Response = Response;
  }

  get() {
    this.Response.success({
      hello: 'world'
    });
  } 
...
```

You can also return to send data to a `Response.success()`.

```js
...
  get() {
    return {
      hello: 'world'
    };
  }
...
```

And with plain ol `response`

```js
...
  get() {
    response({
      hello: 'world'
    });
  }
...
```