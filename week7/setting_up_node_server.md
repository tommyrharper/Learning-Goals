# Setting up a node server

Make sure you have node installed on your computer.
To check you can run
```
node -v
```

If you don't have node run:
```
brew update
brew install node
```


Run these commands in your root folder:
```
$ cd root/of/your-project/
$ npm install http-server --save
// This is obselete in the below scenario
$ node node_modules/http-server/bin/http-server
```

Create server.js and add in the following code
```javascript
var path = require("path");

var pathToHtmlAndJsFiles = path.join(__dirname, "path/from/current/dir/to/html/and/js/files");
var server = httpServer.createServer({ root: pathToHtmlAndJsFiles });
server.listen(3000);
```
Then run
```
node server
```
And visit ```localhost:3000```


--------------------

# Section two

run
```
npm init -y
```