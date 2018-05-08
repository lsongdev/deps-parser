es6-deps
-------

A simple util to get dependency list of a es6/jsx file.

Install
-----

```
npm install es6-deps
```

Example
-----

Suppose you have 2 files, one is `a.js` with content:

```
var b = require('./b')
```
another is `b.js` whose content is:

```
var c = require('./c');
```

Below is how we get the dependencies list of `a.js`:

```
var Deps = require('es6-deps');
var analyzer = new Deps();
var deps = analyzer.getDeps(__dirname + "/a.js");
console.log(deps); 
// output
[
  '{__dirname}/c.js'
  '{__dirname}/b.js'
]
```

please refer to `test/index.spec.js` for more advance usage.

License
-----

MIT
