#Introduction

This project is from [Node-Webkit-Server](https://github.com/miksago/node-websocket-server), I would have forked from him but I noticed that repo didn't update for quite a long time so I create this repo rather than fork.

#Bug fixed

- support newer draft
- now you can use server.send(id, json) to send data to the certain client

#Sample


    var ws = require(__dirname + '/lib/ws/server');
    var server = ws.createServer();

    server.addListener("connection", function (conn) {
        console.log(conn.id + 'has been connected to the server');
	    server.send(conn.id, JSON.stringify({"some json here"}));
	    server.broadcast(JSON.stringify({"some json here"}));
    });