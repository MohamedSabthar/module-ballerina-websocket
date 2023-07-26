# Chat Application

[![Star on Github](https://img.shields.io/badge/-Star%20on%20Github-blue?style=social&logo=github)](https://github.com/ballerina-platform/module-ballerina-websocket)

_Authors_: @shafreenAnfar @Bhashinee \
_Reviewers_: @shafreenAnfar \
_Created_: 2021/07/29 \
_Updated_: 2021/08/16

## Overview

This application shows how to use the Ballerina WebSocket package to implement a simple chat application.

## Implementation

### The WebSocket Server
The WebSocket server is in charge of registering users to the chat application and broadcasting the messages received by the users.

### Users - WebSocket Clients
Clients can register for the chat application by sending requests to the WebSocket server. When the application starts it will request a username. Once a non-empty username is entered, the user will get registered.

After getting registered, the users can send messages to the chat group by typing messages on the console and pressing `Enter`. Then, the server will broadcast messages by looping over the registered clients.
If a user wants to exit from the chat, he/she can type in `exit` and `Enter` so that the connection will get closed, and the client gets unregistered from the chat.

The client will have one Ballerina strand writing the messages to the WebSocket connection and one for reading.

## Run the Example

First, clone this repository, and then run the following commands to run this example in your local machine.

```sh
// Run the WebSocket server
$ cd examples/chat-application/server
$ bal run
```

In another terminal, run the client as follows.
```sh
// Run the WebSocket client
$ cd examples/chat-application/client
$ bal run
```