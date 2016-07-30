# json-lexer

[![Build Status](https://travis-ci.org/finnp/json-lexer.svg?branch=master)](https://travis-ci.org/finnp/json-lexer)
[![Coverage Status](https://coveralls.io/repos/finnp/json-lexer/badge.svg?branch=master&service=github)](https://coveralls.io/github/finnp/json-lexer?branch=master)
[![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg?style=flat)](https://github.com/feross/standard)
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)

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
