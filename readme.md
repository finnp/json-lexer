# json-lexer

This is a JSON lexer based on the implementation in [json3](https://github.com/bestiejs/json3).
It can split a JSON String into a list of annotated tokens. It will list whitespace
as well, so it can used in-place editing of JSON documents.

Note that this doesn't check the validity of your JSON, so it will tokenize something
like `"token"}:` happily.

```js
var lexer = require('json-lexer')
lexer('{"hello": "world"}')
// results in
[ { type: 'punctuator', value: '{' },
  { type: 'string', value: 'hello' },
  { type: 'punctuator', value: ':' },
  { type: 'whitespace', value: ' ' },
  { type: 'string', value: 'world' },
  { type: 'punctuator', value: '}' } ]
```
