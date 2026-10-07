# Sharing Earbuds

## Motivation: 
I created this project to practice my backend API design skills, and learn the tradeoffs between different approaches. 

As a chronically online Spotify user who streams music regularly and uses the platform to listen with others, 
I wanted to challenge myself by recreating the friend activity feature using websockets and restful apis. 

## Techstack:
 
TypeScript 
Next.js
Node.js/Express.js
Redis
PostgreSQL
Docker Compose
Grafana

I kept this techstack minimal and lightweight so I can focus on honing down the fundamentals 
and decide between pros/cons of each approach.

## Engineering Decisions:
While standard HTTP calls are usually sufficient for retrieving updated information, they fall short when a service
requires a constant stream of information, because spamming a server for requests can overwhelm it, causing it to crash
or consume unnecessary resources. On the other hand, if we requests new data from the server sparingly, perhaps once every 10 seconds,
our service will feel laggy and may miss critical updates. 

To overcome this shortcoming, we introduce websockets, which offers bidirectional communication with the service, offering the best of both worlds. 

## Rate Limiting: 
REST and WebSockets need rate-limiting to prevent DoS attacks and keep computing resources safe (CPU - REST, Memory - WebSockets) an error code of 429 will be 

## Alternative Appraoches:
If the problem required it, I would use a gRPC protocol instead of RestAPIs and websockets because the protocol buffers offer more throughput compared to standard JSON for alternative applications. Because setting up a proxy for this issue would be more complicated for web applications, I chose not to to avoid any overhead and setup issues for later. 

