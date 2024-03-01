https://www.pubnub.com/guides/websockets/

A WebSocket is a communication protocol that provides full-duplex communication channels over a single TCP connect connection. It enables real-time, event-driven communication between a client and a server. 

Unlike traditional HTTP, which follows a request-response model, WebSockets allow bi-directional communication. This means that the client and the server can send data to each other anytime without continuous polling.

## What are WebSockets used for?
WebSockets are used for real-time, event-driven communication between clients and servers. They are useful for building applications requiring instant updates, such as real-time chat, messaging, and multiplayer games.

In HTTP, the client sends a request to the server, and the server responds with the requested data. This request-response model requires a continuous polling from the client to the server, which can result in increased latency and decrease efficiency.

**Polling is a method in which a client frequently asks the server for new data.**

On the other hand, WebSocket establish establish a persistent connection between the client and the server. This means that once the connection is established, the client an the server can send data to each other at any time without continuous polling. 

WebSockets also allow for bi-directional communication, meaning that both the client and server can send data to each other. This opens up possibilities for more interactive and engaging applications, where the server can push updates or notifications to the client without the client explicitly requesting them.

## Cons
- [c]  Stateful Nature: Unlike traditional HTTP, which is stateless, WebSockets are stateful. This means that the server needs to maintain the connection state for each client, leading to increased memory usage and potential scalability challenges.