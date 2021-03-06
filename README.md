# koa-xtpl

[![NPM version][npm-image]][npm-url]
[![NPM download][download-image]][download-url]
[![Build Status][travis-image]][travis-url]
[![Dependency Status][dependency-image]][dependency-url]
[![devDependency Status][devdependency-image]][devdependency-url]
[![Code Style][style-image]][style-url]

[npm-image]: https://badge.fury.io/js/koa-xtpl.svg
[npm-url]: https://npmjs.org/package/koa-xtpl
[download-image]: https://img.shields.io/npm/dm/koa-xtpl.svg
[download-url]: https://npmjs.org/package/koa-xtpl
[travis-image]: https://travis-ci.org/zce/koa-xtpl.svg?branch=v2.x
[travis-url]: https://travis-ci.org/zce/koa-xtpl
[dependency-image]: https://david-dm.org/zce/koa-xtpl/status.svg
[dependency-url]: https://david-dm.org/zce/koa-xtpl
[devdependency-image]: https://david-dm.org/zce/koa-xtpl/dev-status.svg
[devdependency-url]: https://david-dm.org/zce/koa-xtpl?type=dev
[style-image]: https://img.shields.io/badge/code%20style-standard-brightgreen.svg
[style-url]: http://standardjs.com/

> A node.js wrapper around xtemplate engine (easier for Koa 2)

## Install

```sh
# npm
$ npm install koa-xtpl --save
# or yarn
$ yarn add koa-xtpl
```


## Usage

demo.xtpl
```html
<p>{{ title }}</p>
```

demo.js

```js
const path = require('path')
const Koa = require('koa')
const xtpl = require('koa-xtpl')
const app = new Koa()

// root
app.use(xtpl(path.join(__dirname, 'views')))
// or options
app.use(xtpl({
  root: path.join(__dirname, 'views'),
  extname: 'xtpl',
  commands: {}
}))

app.use(async ctx => {
  await ctx.render('demo', { title: new Date() })
})

app.listen(3000)
```


## API

### xtpl(options)

#### options

Type: `object` or `string`

Option or view root directory

##### root

Type: `string`

##### commands

Type: `object`

##### extname

Type: `string`

##### catchError

Type: `boolean`

##### encoding

Type: `string`<br>
Default: `utf-8`

##### strict

Type: `boolean`

##### cache

Type: `boolean`


## License

[MIT](LICENSE) © [汪磊](http://github.com/zce)

