# pomelo client
pomeol client，base socket.io-client

## Getting Start

```
npm install 
```

## scripts

```
var pomelo = require('pomelo-client');
var pomeloclient = new pomelo({"debug":true});
pomeloclient.init({ "host": host, "port": port,"reconnectionAttempts":3 }, function (socket) {
        pomeloclient.request("chat.userHandler.addUser", args,
            function (data) {
                pomeloclient.disconnect();
                
                console.log(data);
            });
    });

pomeloclient.on("error", function (err) {
    pomeloclient.disconnect();
    console.log(err);
});

```

### API

#### new pomelo(options:Object)
  - `options` _(Object)_
    - `debug` _(Boolean)_ console log
  
#### init(options:Object,cb:Function)

   - `options` _(Object)_
    - `host` _(String)_ host
    - `port` _(Number)_ port
    - `reconnectionAttempts` _(Number)_ number of reconnection attempts before giving up (Infinity)