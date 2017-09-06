# fastify-static
Plugin for serving static file

## Install

`npm install --save fastify-static`

## Usage

```js
const fastify = require('fastify')
const path = require('path')

fastify.register(require('fastify-static'), {
  root: path.join(__dirname, 'public'),
  prefix: '/public/' // optional: default '/'
  page404Path: path.join(__dirname, 'public', '404.html'), // optional
  page403Path: path.join(__dirname, 'public', '403.html'), // optional
  page500Path: path.join(__dirname, 'public', '500.html')  // optional
})

fastify.get('/another/path', function (req, reply) {
  reply.sendFile('myHtml.html') // serving path.join(__dirname, 'public', 'myHtml.html') directly
})

```

## License

Licensed under [MIT](./LICENSE)
