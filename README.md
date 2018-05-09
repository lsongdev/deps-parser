# deps-parser

A simple way to get module dependencies

## Install


```bash
~$ npm install deps-parser
```

## Example

Suppose you have 2 files, one is `a.js` with content:

```js
var b = require('./b')
```
another is `b.js` whose content is:

```js
var c = require('./c');
```

Below is how we get the dependencies list of `a.js`:

```js
var Deps = require('deps-parser');
var analyzer = new Deps();
var deps = analyzer.getDeps(__dirname + "/a.js");
console.log(deps); 
// output
[
  '{__dirname}/c.js'
  '{__dirname}/b.js'
]
```

## License

This project is under MIT licence.
