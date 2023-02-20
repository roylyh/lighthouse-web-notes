# Roy's Note

## What is a protocol?
A defined standard for how requests and responses are sent between network devices

## TCP/IP Model
- Network Access - physical devices and how they connect to the network
- Internetwork - communication between devices on the network
- Transport - splits up the network communication into ports
- Application - clients and servers/applications and services/sessions and encryption

## Transport Layer Protocols
- Break data into packets to be sent over the network layer
- Give each packet a header with origin and destination
- UDP: User Datagram Protocol
  - Smaller header size (8 bytes) which results in smaller packet sizes
  - Connectionless ie. there is no need to establish or maintain a connection
  - No error recovery (any corrupted packets are discarded)
  - Packets can arrive in any order
  - Useful for streaming/low latency applications
- TCP: Transportation Control Protocol
  - Larger header size (20 bytes)
  - Requires a connection (3-way handshake)
  - Corrupted packets are reported to the server and are re-sent
  - Packets arrive in order
  - Useful when guaranteed communication is needed

## Useful Links
[OSI Model](https://en.wikipedia.org/wiki/OSI_model)  
[Net Package documentation](https://nodejs.org/api/net.html)
**readline**
```javascript
const readline = require('readline');
  
const rl = readline.createInterface(
     process.stdin, process.stdout);
rl.question('What is your age? ', (age) => {
    console.log('Your age is: ' + age);
    rl.close();
});
```

*Net Module*
```javascript
// Server.js
const net = require('net');
const server = net.createServer();
const port = 3001;
server.on('connection',(connection)=>{
  connection.setEncoding('utf-8');
  connection.write('Thanks for connecting to the server');
  connection.on('data',(msgFromClient)=>{

  });
});
server.listen(port, ()=>{
  console.log('tcp server listening on port ', port);
});

// client.js
const net = require('net');
const config = {
  host: 'localhost',
  port: '3001',
};
const connection = net.createConnection(config);
connection.setEncoding('utf-8');
connection.on('data', (msgFromServer)=>{

});
process.stdin.setEncoding('utf-8');
// process.stdin.setRawMode(true);// true means event by one character
process.stdin.on('data', (messageFromStdIn) => {
  // console.log(messageFromStdIn);
  connection.write(messageFromStdIn);
});
```

[**snake games**](https://github.com/roylyh/snake-client)

/r redrawing line (How could we use? I could not find the example.)