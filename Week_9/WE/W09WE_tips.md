# Socket.IO topic

-- socketio

## Client-side events for socket.io object
eventname could be defined by users but there are some event triggered automatically
- connect. Fired upon a successful connection.

- connect_error. Fired upon a connection error.
Parameters:
Object error object

- connect_timeout. Fired upon a connection timeout.

- reconnect. Fired upon a successful reconnection.
Parameters:
Number reconnection attempt number

- reconnect_attempt. Fired upon an attempt to reconnect.

- reconnecting. Fired upon an attempt to reconnect.
Parameters:
Number reconnection attempt number

- reconnect_error. Fired upon a reconnection attempt error.
Parameters:
Object error object

- reconnect_failed. Fired when couldn’t reconnect within reconnectionAttempts

## Client-side events for socket object
- connect. Fired upon connecting.
- error. Fired upon a connection error
Parameters:
Object error data
- disconnect. Fired upon a disconnection.
- reconnect. Fired upon a successful reconnection.
Parameters:
Number reconnection attempt number
- reconnect_attempt. Fired upon an attempt to reconnect.
- reconnecting. Fired upon an attempt to reconnect.
Parameters:
- Number reconnection attempt number
- reconnect_error. Fired upon a reconnection attempt error.
Parameters:
Object error object
- reconnect_failed. Fired when couldn’t reconnect within reconnectionAttempts

## - Server-side events:
- connection / connect. Fired upon a connection.
Parameters:
Socket the incoming socket.

[List of Socket.io Events](https://stackoverflow.com/questions/24224287/list-of-socket-io-events)