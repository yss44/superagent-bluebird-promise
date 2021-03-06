superagent-bluebird-promise
===========================

Add promise support to
[Superagent](http://visionmedia.github.io/superagent/) using
[Bluebird](https://github.com/petkaantonov/bluebird).

## Install
`npm install superagent-bluebird-promise`

## Usage
Simply require this package instead of `superagent`. Then you can call `.promise()` instead of `.end()` to get a promise for your requests.

```javascript

var request = require('superagent-bluebird-promise');

request.get('/an-endpoint').promise()
  .then(function(res) {
    console.log(res);
  })
  .catch(function(error) {
    console.log(error);
  })
  ```

An error is thrown for all HTTP errors and responses that have a response code of 400 or above.

The `error` parameter always has a key `error` and for 4xx and 5xx responses, will also have a `status` and `res` key.
