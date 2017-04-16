# api documentation for  [image-size (v0.5.1)](https://github.com/image-size/image-size#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-image-size.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-image-size) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-image-size.svg)](https://travis-ci.org/npmdoc/node-npmdoc-image-size)
#### get dimensions of any image file

[![NPM](https://nodei.co/npm/image-size.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/image-size)

[![apidoc](https://npmdoc.github.io/node-npmdoc-image-size/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-image-size/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-image-size/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-image-size/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "netroy",
        "url": "http://netroy.in/"
    },
    "bin": {
        "image-size": "bin/image-size.js"
    },
    "bugs": {
        "url": "https://github.com/image-size/image-size/issues"
    },
    "dependencies": {},
    "description": "get dimensions of any image file",
    "devDependencies": {
        "escomplex-js": "^1.2.0",
        "expect.js": "^0.3.1",
        "glob": "^7.1.1",
        "istanbul": "^0.4.0",
        "jshint": "^2.8.0",
        "mocha": "^3.2.0",
        "sinon": "^1.17.2"
    },
    "directories": {},
    "dist": {
        "shasum": "28eea8548a4b1443480ddddc1e083ae54652439f",
        "tarball": "https://registry.npmjs.org/image-size/-/image-size-0.5.1.tgz"
    },
    "engines": {
        "node": ">=0.10.0"
    },
    "files": [
        "bin",
        "lib"
    ],
    "gitHead": "05fd80685ea70b2b7a27e76b16bc614f0949b4f4",
    "homepage": "https://github.com/image-size/image-size#readme",
    "keywords": [
        "image",
        "size",
        "dimensions",
        "resolution",
        "width",
        "height",
        "png",
        "jpeg",
        "bmp",
        "gif",
        "psd",
        "tiff",
        "webp",
        "svg"
    ],
    "license": "MIT",
    "main": "lib/index.js",
    "maintainers": [
        {
            "name": "netroy"
        },
        {
            "name": "shinnn"
        },
        {
            "name": "zeke"
        }
    ],
    "name": "image-size",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git+https://github.com/image-size/image-size.git"
    },
    "scripts": {
        "coverage": "istanbul cover _mocha specs",
        "pretest": "jshint",
        "test": "mocha specs"
    },
    "version": "0.5.1"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module image-size](#apidoc.module.image-size)
1.  [function <span class="apidocSignatureSpan"></span>image-size (input, callback)](#apidoc.element.image-size.image-size)
1.  [function <span class="apidocSignatureSpan">image-size.</span>toString ()](#apidoc.element.image-size.toString)
1.  object <span class="apidocSignatureSpan">image-size.</span>types



# <a name="apidoc.module.image-size"></a>[module image-size](#apidoc.module.image-size)

#### <a name="apidoc.element.image-size.image-size"></a>[function <span class="apidocSignatureSpan"></span>image-size (input, callback)](#apidoc.element.image-size.image-size)
- description and source-code
```javascript
image-size = function (input, callback) {

  // Handle buffer input
  if (Buffer.isBuffer(input)) {
    return lookup(input);
  }

  // input should be a string at this point
  if (typeof input !== 'string') {
    throw new TypeError('invalid invocation');
  }

  // resolve the file path
  var filepath = path.resolve(input);

  if (typeof callback === 'function') {
    asyncFileToBuffer(filepath, function (err, buffer) {
      if (err) { return callback(err); }

      // return the dimensions
      var dimensions;
      try {
        dimensions = lookup(buffer, filepath);
      } catch (e) {
        err = e;
      }
      callback(err, dimensions);
    });
  } else {
    var buffer = syncFileToBuffer(filepath);
    return lookup(buffer, filepath);
  }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.image-size.toString"></a>[function <span class="apidocSignatureSpan">image-size.</span>toString ()](#apidoc.element.image-size.toString)
- description and source-code
```javascript
toString = function () {
    return toString;
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
