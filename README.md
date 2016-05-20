# Validate Commit

[![NPM version][npm-image]][npm-url]
[![Build Status][travis-image]][travis-url]
[![Coveralls Status][coveralls-image]][coveralls-url]
[![Dependency Status][depstat-image]][depstat-url]
[![Downloads][download-badge]][npm-url]

> Validate commit messages according to various presets

![example](./example.gif)

## Install

```sh
npm install validate-commit --save-dev
```

## Features

Even though there are a couple of other packages that do this, this one has a few quality of life changes.

- **Lets you decide how to validate** the commit messages (see [here](#usage))
- It validate commit files coming from both strings and files
- Supports the following **presets**:
  + [angular](./conventions/angular.md)
  + [atom](./conventions/atom.md)
  + [eslint](./conventions/eslint.md)
  + [ember](./conventions/ember.md)
  + [jquery](./conventions/jquery.md)
  + [jshint](./conventions/jshint.md)
- Supports **ignore patterns**
- Uses [chalk][chalk-url] module to color messages
- Logging can be disabled via environment variable

## Usage

### With git hooks

E.g., using [git-scripts][git-scripts-url].

```json
"git": {
    "scripts": {
        "commit-msg": "./node_modules/.bin/validate-commit-msg $1"
    }
}
```

### From CLI

```bash
$ validate-commit-msg 'chore(package): some message'
```

### Within node

```javascript
var validateCommit = require('validate-commit').validateMessage;
validateCommit('chore(package): some message'); // true
```

## API

### JavaScript

```
validateMessage(message: string, ?options: object)
```

```
validateMessageFromFile(file: string, ?options: object)
```

### CLI

This module, like many others, installs an executable in **./node_modules/.bin**.

```bash
~./node_modules/.bin$ ./validate-commit-msg
```

```
  Usage: validate-commit-msg [options] [command]


  Commands:

    validate-commit-msg <message>  validate a message
    help [cmd]                     display help for [cmd]

  Validate commit messages according to various presets

  Options:

    -h, --help             output usage information
    -V, --version          output the version number
    -p, --preset <preset>  specify a preset (angular|atom|eslint|ember|jquery|jshint) [angular]
```

### Development

`npm i && typings install`

## License

Apache-2.0 © [Will Soto](http://github.com/paradox41)

[npm-url]: https://npmjs.org/package/validate-commit
[npm-image]: https://img.shields.io/npm/v/validate-commit.svg?style=flat-square

[travis-url]: https://travis-ci.org/paradox41/validate-commit
[travis-image]: https://img.shields.io/travis/paradox41/validate-commit.svg?style=flat-square

[coveralls-url]: https://coveralls.io/r/paradox41/validate-commit
[coveralls-image]: https://img.shields.io/coveralls/paradox41/validate-commit.svg?style=flat-square

[depstat-url]: https://david-dm.org/paradox41/validate-commit
[depstat-image]: https://david-dm.org/paradox41/validate-commit.svg?style=flat-square

[download-badge]: http://img.shields.io/npm/dm/validate-commit.svg?style=flat-square

[chalk-url]: https://www.npmjs.com/package/chalk
[git-scripts-url]: https://www.npmjs.com/package/git-scripts
