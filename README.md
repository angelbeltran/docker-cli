# Dockernode

This package exports a function, docker, providing access to all of docker's cli commands.

## Examples

### Key Aliasing

```javascript
let docker = require('dockernode')

docker('help')        // docker --help
docker('--help')      // docker --help
docker('h')           // docker -h
docker('-h')          // docker -h
docker('version')     // docker --version
docker('--version')   // docker --version
docker('v')           // docker -v
docker('-v')          // docker -v
```

### Commands
```javascript
// Simple commands
docker('ps')                  // docker ps
docker('ps -a')               // docker ps -a

// Command options
docker('ps', { a: true })     // docker ps -a
docker('ps', { a: false })    // docker ps
docker('ps', { help: true })  // docker ps --help
docker('run', { i: true, '-t': true, args: ['hello-world'] })   // docker run -i -t hello-world
docker('run', { it: true, args: ['hello-world', 'ping'] })      // docker run -it hello-world ping

// Docker options
docker('inspect', { docker: { debug: true, host: '10.123.45.67:3141' }, args: ['hello-world'] }   // docker --debug --host 10.123.45.67:3141 inspect hello-world
```
