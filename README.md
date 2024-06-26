# Tinkoff Utils [![Build status](https://img.shields.io/github/actions/workflow/status/devtea2026/placeat-repellat-earum-hic/build.yml?branch=master)](https://img.shields.io/github/actions/workflow/status/devtea2026/placeat-repellat-earum-hic/build.yml?branch=master) [![Coverage Status](https://coveralls.io/repos/github/devtea2026/placeat-repellat-earum-hic/badge.svg?branch=master&t=CdowK8)](https://coveralls.io/github/devtea2026/placeat-repellat-earum-hic?branch=master)

> Fast, small and purely functional utility library

## Install
```
$ npm install @devtea2026/placeat-repellat-earum-hic
```

## Features
- [Fast](#benchmarks)
- [Small](#bundle-size)
- [Fully tested](https://coveralls.io/github/devtea2026/placeat-repellat-earum-hic)
- [Documented](https://Tinkoff.github.io/utils.js)
- Purely functional
- Modern codebase

## Structure of the library
* [`/object`](https://github.com/devtea2026/placeat-repellat-earum-hic/tree/master/src/object) – for objects
* [`/string`](https://github.com/devtea2026/placeat-repellat-earum-hic/tree/master/src/string) – for strings
* [`/promise`](https://github.com/devtea2026/placeat-repellat-earum-hic/tree/master/src/promise) – for promises
* [`/array`](https://github.com/devtea2026/placeat-repellat-earum-hic/tree/master/src/array) – for arrays or array-like objects
* [`/function`](https://github.com/devtea2026/placeat-repellat-earum-hic/tree/master/src/function) – for functions – composition, currying and so on, also a set of simple functions (noop, T, F)
* [`/is`](https://github.com/devtea2026/placeat-repellat-earum-hic/tree/master/src/is) – set of type checking methods
* [`/`](https://github.com/devtea2026/placeat-repellat-earum-hic/tree/master/src) – root contains utilities which don't satisfy any of the above categories or are universal

## Usage
```js
import pathOr from '@devtea2026/placeat-repellat-earum-hic/object/pathOr';
import compose from '@devtea2026/placeat-repellat-earum-hic/function/compose';
import toLower from '@devtea2026/placeat-repellat-earum-hic/string/toLower';
import map from '@devtea2026/placeat-repellat-earum-hic/array/map'

const toLowerName = compose(
    toLower,
    pathOr(['name'], '')
);
const result = map(toLowerName)([{name: 'testA'}, {name: 'testb'}])
```

## Benchmarks
```bash
$ npm run benchmark
```

| Utility | Lodash | Ramda | Utils |
| --- | --- | --- | --- |
| clone | 120,807 ops/sec | 112,053 ops/sec | 293,572 ops/sec |
| array/filter | 2,080,728 ops/sec | 1,849,633 ops/sec | 2,046,113 ops/sec |
| is/empty | 1,506,963 ops/sec | 474,177 ops/sec | 3,731,564 ops/sec |
| function/flip | 7,528,745 ops/sec | 3,735,143 ops/sec | 3,490,207 ops/sec |
| object/path | 12,023,128 ops/sec | 8,894,639 ops/sec | 7,587,076 ops/sec |
| string/trim | 4,215,928 ops/sec | 1,034,655 ops/sec | 6,029,794 ops/sec |

## Browser support

- Chrome >= 40
- Firefox >= 52
- Edge >= 14
- IE >= 11
- Safari >= 10
- iOS >= 10
- Android >= 4.4

## Node support
- 6.4.0 and higher

## Bundle size
| Library | Bundle size |
| --- | --- |
| import _ from 'lodash' | 70.1 kb |
| import ... from 'lodash/...' | 21.8 kb |
| import R from 'ramda' | 41.3 kb |
| import ... from 'ramda/src/...' | 10 kb |
| import ... from '@devtea2026/placeat-repellat-earum-hic/...' | 2.32 kb |

For detailed comparison with specific libraries see [COMPARE.md](https://github.com/devtea2026/placeat-repellat-earum-hic/tree/master/COMPARE.md)
