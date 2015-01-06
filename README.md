clustered-node
==============
[![Build Status](https://travis-ci.org/ranacseruet/clustered-node.svg)](https://travis-ci.org/ranacseruet/clustered-node)

A Simple library to make your traditional single threaded nodejs server into a multi-process based server, 
so that you can make better utilization of your server cpu.

This project is inspired by [multi-node](https://github.com/kriszyp/multi-node) project, which isn't anymore compatible with latest nodejs version.

Also a large portion of this project implementation idea is taken from [hipache](https://github.com/hipache/hipache)
project's multi-process architecture.

## Install
```
npm install clustered-node
```

## Usage

```
var http    = require("http");
var clustered_node = require("clustered-node");

var server = http.createServer(function(req, res){
     res.end("Hello World");
});

function runServer() {
    return http.createServer(function(req, res){
        res.end("Hello World");
    });
};

clustered_node.listen({port:1337, workers:3}, server);
//or
clustered_node.run(config, runServer);
```

## Development and Testing

```
npm install
npm test
```

# Contribute

Please report any bugs/feature requests via github issue tracking. Pull requests are very much welcome as well.
