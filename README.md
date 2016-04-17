# lzfjs

Compress and decompress data using LZF with no native dependencies. Naively ported directly from 
liblzf, specfically `lzf_c.c` and `lzf_d.c` by Marc Alexander Lehmann. If pure JS is not important 
to you, use the `lzf` npm package.

This module can be used in a browser or in Node.

## License

BSD 2 Clause

## Compress data

```
var lzf = require('lzfjs');
var data = new Buffer('Hello world');
console.log(lzf.compress(data).toString('base64')); // "CkhlbGxvIHdvcmxk"
```

## Decompress data

```
var lzf = require('lzfjs');
var data = new Buffer('CkhlbGxvIHdvcmxk', 'base64');
console.log(lzf.decompress(data).toString('utf8')); // "Hello world"
```

## Use in browser

Instead of passing a node `Buffer` to `compress` and `decompress`, pass in a `TypedArray` like a
`Uint8Array`, or pass in an `ArrayBuffer`. The functions will return a `Uint8Array`.
