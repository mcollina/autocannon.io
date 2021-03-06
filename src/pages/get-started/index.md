---
layout: main.html
---

# Get started

## Install

```
npm i autocannon -g
```

or if you want to use the [API](#api) or as a dependency:

```
npm i autocannon --save
```

### Supported systems

**autocannon** is supported on Linux, Mac OS X and Windows.
If you see any errors during installation, you might need to configure
your system to compile native addons:
follow the instructions at [node-gyp][node-gyp].

## Usage

### Command Line

```
Usage: autocannon [opts] URL

Available options:

  -c/--connections NUM  The number of concurrent connections to use
  -p/--pipelining NUM   The number of pipelined requests to use
  -d/--duration SEC     The number of seconds to run the autocannnon
  -m/--method METHOD    The http method to use
  -b/--body FILE        The body of the request
  -h/--headers K=V      The request headers
  -j/--json             Print the output as json
  -l/--latency          Print all the latency data
  -h/--help             Print this menu
```

### Programmatically

```js
'use strict'

const autocannon = require('autocannon')

autocannon({
  url: 'http://localhost:3000',
  connections: 10,
  pipelining: 1, // default
  duration: 10
}, console.log)
```

## API

### autocannon(opts, cb)

Start autocannon against the given target, options:

* `url`: the given target, mandatory
* `connections`: the number of concurrent connections
* `pipelining`: the number of pipelined requests for each connection,
  see https://en.wikipedia.org/wiki/HTTP_pipelining
* `duration`: the number of seconds to run the autocannon
* `body`: a `Buffer` containing the body of the request
* `method`: the http method to use, `GET` is the default




[node-gyp]: https://github.com/nodejs/node-gyp#installation
[wrk]: https://github.com/wg/wrk
[wrk2]: https://github.com/giltene/wrk2
