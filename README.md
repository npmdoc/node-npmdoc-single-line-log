# api documentation for  [single-line-log (v1.1.2)](https://github.com/freeall/single-line-log#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-single-line-log.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-single-line-log) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-single-line-log.svg)](https://travis-ci.org/npmdoc/node-npmdoc-single-line-log)
#### Keep writing to the same line in the terminal. Very useful when you write progress bars, or a status message during longer operations

[![NPM](https://nodei.co/npm/single-line-log.png?downloads=true)](https://www.npmjs.com/package/single-line-log)

[![apidoc](https://npmdoc.github.io/node-npmdoc-single-line-log/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-single-line-log_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-single-line-log/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-single-line-log/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-single-line-log/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Tobias Baunbæk",
        "email": "freeall@gmail.com"
    },
    "bugs": {
        "url": "https://github.com/freeall/single-line-log/issues"
    },
    "dependencies": {
        "string-width": "^1.0.1"
    },
    "description": "Keep writing to the same line in the terminal. Very useful when you write progress bars, or a status message during longer operations",
    "devDependencies": {},
    "directories": {},
    "dist": {
        "shasum": "c2f83f273a3e1a16edb0995661da0ed5ef033364",
        "tarball": "https://registry.npmjs.org/single-line-log/-/single-line-log-1.1.2.tgz"
    },
    "gitHead": "515b3b99b699396c2ad5f937e4b490b6f9fbff0e",
    "homepage": "https://github.com/freeall/single-line-log#readme",
    "keywords": [
        "single",
        "line",
        "log",
        "output",
        "overwrite",
        "collapse",
        "stdout",
        "terminal",
        "tty",
        "cli",
        "shell"
    ],
    "license": "MIT",
    "maintainers": [
        {
            "name": "freeall",
            "email": "freeall@gmail.com"
        },
        {
            "name": "mafintosh",
            "email": "mathiasbuus@gmail.com"
        }
    ],
    "name": "single-line-log",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/freeall/single-line-log.git"
    },
    "scripts": {
        "test": "node test.js"
    },
    "version": "1.1.2"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module single-line-log](#apidoc.module.single-line-log)
1.  [function <span class="apidocSignatureSpan">single-line-log.</span>stderr ()](#apidoc.element.single-line-log.stderr)
1.  [function <span class="apidocSignatureSpan">single-line-log.</span>stdout ()](#apidoc.element.single-line-log.stdout)

#### [module single-line-log.stderr](#apidoc.module.single-line-log.stderr)
1.  [function <span class="apidocSignatureSpan">single-line-log.</span>stderr ()](#apidoc.element.single-line-log.stderr.stderr)
1.  [function <span class="apidocSignatureSpan">single-line-log.stderr.</span>clear ()](#apidoc.element.single-line-log.stderr.clear)

#### [module single-line-log.stdout](#apidoc.module.single-line-log.stdout)
1.  [function <span class="apidocSignatureSpan">single-line-log.</span>stdout ()](#apidoc.element.single-line-log.stdout.stdout)
1.  [function <span class="apidocSignatureSpan">single-line-log.stdout.</span>clear ()](#apidoc.element.single-line-log.stdout.clear)



# <a name="apidoc.module.single-line-log"></a>[module single-line-log](#apidoc.module.single-line-log)

#### <a name="apidoc.element.single-line-log.stderr"></a>[function <span class="apidocSignatureSpan">single-line-log.</span>stderr ()](#apidoc.element.single-line-log.stderr)
- description and source-code
```javascript
stderr = function () {
		str = '';
		var nextStr = Array.prototype.join.call(arguments, ' ');

		// Clear screen
		for (var i=0; i<prevLineCount; i++) {
			str += MOVE_LEFT + CLEAR_LINE + (i < prevLineCount-1 ? MOVE_UP : '');
		}

		// Actual log output
		str += nextStr;
		stream.write(str);

		// How many lines to remove on next clear screen
		var prevLines = nextStr.split('\n');
		prevLineCount = 0;
		for (var i=0; i < prevLines.length; i++) {
			prevLineCount += Math.ceil(stringWidth(prevLines[i]) / stream.columns) || 1;
		}
	}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.single-line-log.stdout"></a>[function <span class="apidocSignatureSpan">single-line-log.</span>stdout ()](#apidoc.element.single-line-log.stdout)
- description and source-code
```javascript
stdout = function () {
		str = '';
		var nextStr = Array.prototype.join.call(arguments, ' ');

		// Clear screen
		for (var i=0; i<prevLineCount; i++) {
			str += MOVE_LEFT + CLEAR_LINE + (i < prevLineCount-1 ? MOVE_UP : '');
		}

		// Actual log output
		str += nextStr;
		stream.write(str);

		// How many lines to remove on next clear screen
		var prevLines = nextStr.split('\n');
		prevLineCount = 0;
		for (var i=0; i < prevLines.length; i++) {
			prevLineCount += Math.ceil(stringWidth(prevLines[i]) / stream.columns) || 1;
		}
	}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.single-line-log.stderr"></a>[module single-line-log.stderr](#apidoc.module.single-line-log.stderr)

#### <a name="apidoc.element.single-line-log.stderr.stderr"></a>[function <span class="apidocSignatureSpan">single-line-log.</span>stderr ()](#apidoc.element.single-line-log.stderr.stderr)
- description and source-code
```javascript
stderr = function () {
		str = '';
		var nextStr = Array.prototype.join.call(arguments, ' ');

		// Clear screen
		for (var i=0; i<prevLineCount; i++) {
			str += MOVE_LEFT + CLEAR_LINE + (i < prevLineCount-1 ? MOVE_UP : '');
		}

		// Actual log output
		str += nextStr;
		stream.write(str);

		// How many lines to remove on next clear screen
		var prevLines = nextStr.split('\n');
		prevLineCount = 0;
		for (var i=0; i < prevLines.length; i++) {
			prevLineCount += Math.ceil(stringWidth(prevLines[i]) / stream.columns) || 1;
		}
	}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.single-line-log.stderr.clear"></a>[function <span class="apidocSignatureSpan">single-line-log.stderr.</span>clear ()](#apidoc.element.single-line-log.stderr.clear)
- description and source-code
```javascript
clear = function () {
		stream.write('');
	}
```
- example usage
```shell
...
	var percentage = Math.floor(100*read/size);

	// Keep writing to the same two lines in the console
	log('Writing to super large file\n[' + percentage + '%]', read, 'bytes read');
});
'''

## .clear()

Clears the log (i.e., writes a newline).

''' js
var log = require('single-line-log').stdout;

log('Line 1');
...
```



# <a name="apidoc.module.single-line-log.stdout"></a>[module single-line-log.stdout](#apidoc.module.single-line-log.stdout)

#### <a name="apidoc.element.single-line-log.stdout.stdout"></a>[function <span class="apidocSignatureSpan">single-line-log.</span>stdout ()](#apidoc.element.single-line-log.stdout.stdout)
- description and source-code
```javascript
stdout = function () {
		str = '';
		var nextStr = Array.prototype.join.call(arguments, ' ');

		// Clear screen
		for (var i=0; i<prevLineCount; i++) {
			str += MOVE_LEFT + CLEAR_LINE + (i < prevLineCount-1 ? MOVE_UP : '');
		}

		// Actual log output
		str += nextStr;
		stream.write(str);

		// How many lines to remove on next clear screen
		var prevLines = nextStr.split('\n');
		prevLineCount = 0;
		for (var i=0; i < prevLines.length; i++) {
			prevLineCount += Math.ceil(stringWidth(prevLines[i]) / stream.columns) || 1;
		}
	}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.single-line-log.stdout.clear"></a>[function <span class="apidocSignatureSpan">single-line-log.stdout.</span>clear ()](#apidoc.element.single-line-log.stdout.clear)
- description and source-code
```javascript
clear = function () {
		stream.write('');
	}
```
- example usage
```shell
...
	var percentage = Math.floor(100*read/size);

	// Keep writing to the same two lines in the console
	log('Writing to super large file\n[' + percentage + '%]', read, 'bytes read');
});
'''

## .clear()

Clears the log (i.e., writes a newline).

''' js
var log = require('single-line-log').stdout;

log('Line 1');
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
