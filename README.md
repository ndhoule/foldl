# foldl [![Circle CI][circleci-badge]][circleci-link]

Apply a function to each value in a collection, accumulating the results into a single return value.

## Installation

Browser:

```sh
component install ndhoule/foldl
```

Node:

```sh
$ npm install foldl
```

## API

### `reduce(iterator : Function, accumulator : *, collection : Array|Object)`

Reduces all the values in a collection down into a single value. Does so by iterating through the collection from left to right, repeatedly calling an `iterator` function and passing to it four arguments: `(accumulator, value, index, collection)`.

```javascript
foldl(function(total, n) {
  return total + n;
}, 0, [1, 2, 3]);
//=> 6

var phonebook = { bob: '555-111-2345', tim: '655-222-6789', sheila: '655-333-1298' };

foldl(function(results, phoneNumber) {
 if (phoneNumber[0] === '6') {
   return results.concat(phoneNumber);
 }
 return results;
}, [], phonebook);
// => ['655-222-6789', '655-333-1298']
```

## License

Released under the [MIT license](LICENSE.md).

[circleci-link]: https://circleci.com/gh/ndhoule/foldl
[circleci-badge]: https://circleci.com/gh/ndhoule/foldl.svg?style=svg&circle-token=861d6f06f13892bcdcaf89ac1f00a368c5d63700
