# Testing
Tests are located in the `test` folder.

This framework uses [mochajs](https://mochajs.org/) to perform the tests. 

> You can use any testing framework you want.


## Debugging Errors 
> WIP

Enable error reporting with the following:
```
export DEBUG=adonis:framework
```


## Create a test
Functions are created with the `lesswork` command.

```bash
lesswork make:test HelloWorld
```

This creates the file `test/HelloWorldTest.js`.

```js
const mochaPlugin = require('serverless-mocha-plugin');
const expect = mochaPlugin.chai.expect;
const assert = mochaPlugin.chai.assert;

const Test = require('@lessworkjs/framework/src/Test');

let wrapped = mochaPlugin.getWrapper('HelloWorld', '/app/Http/Routes/HelloWorld', 'get');

describe('HelloWorld', () => {
  before((done) => {
    done();
  });

  it('should work', () => {
    return wrapped.run().then((response) => {
      expect(response).to.not.be.empty;
      assert.equal(typeof response, 'object');
      assert.equal(response.statusCode, '200');

      const body = JSON.parse(response.body);
      assert.equal(body.hello, 'world');
    });
  });
});
```

## Executing tests
There are 3 `npm` commands related to testing.

```bash
npm run test # test with serverless 
npm run test:local # test locally
npm run coverage # report code coverage
```