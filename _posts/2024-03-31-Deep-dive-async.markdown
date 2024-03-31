---
layout: post
title:  "A deep dive into Async patterns"
date:   2024-03-31 01:45:00 +0530
comments: True
share: True
categories: Engineering
---

In the recent times I have been trying to understand a bit more about asynchronous communication between services and real time streaming. For real time streaming the Pub sub pattern seems the most important architectural pattern.

In this post I will go on a journey where we assume that we know about synchronous client server interaction to various async patterns and how each of them solve the problem of scale.

## Client Server Architecture

In the world of application development which involves internet, there are basically two components one is the frontend/Client which is accessible through a browser or app where people can click or enter data and perform some actions, which is then sent across to the server (some form of a computer) that performs the logical operations on it. The data is relayed from client to server through a secure network connection.


![A simple example of Client Server Model](../assets/CSarch.webp)

As consumer we would want our actions also technically known as requests to be executed as fast as possible which is the right of the customer.

### Synchronous Communication
While simple to implement, synchronous communication in client-server systems suffers from several limitations that impact scalability and responsiveness. Each request blocks the server, occupying resources (like RAM) until the entire logic executes. This creates a single thread of execution, meaning the server can only handle one request at a time. In multi-process systems, this forces you to allocate a dedicated machine for each customer, even if their requests take minimal processing time.

This is why Synchronous communication can be disadvantageous for dynamic and scalable systems. This also brings in

- Inefficient use of compute power
- Scalability bottlenecks — There is only so much machines that can be provisioned at a time

### Asynchronous Communication
In an asynchronous communication pattern, the server does not immediately return a response. Instead, it initiates the request and allows the client to continue execution without waiting. The processing can then happen concurrently on the server, and the client receives a notification or the processed information at a later date.

The detail lies in the implementation and if incorrectly implemented async await operations can be slower than synchronous communication patterns.

## Patterns of Asynchronous Communication
Now that we understand that asynchronous patterns are essential for building a scalable system let us try and understand different patterns of communication.

- Request Reply Pattern
- Publish Subscribe
- Fire and Forget
- Event Driven
- Websockets

### Request Reply pattern
The request-reply asynchronous pattern allows a client to send a request to a server without waiting for an immediate response. This is the pattern that is closest to the synchronous request reply pattern. This frees the client to continue execution on other tasks while the server processes the request concurrently. Once processing is complete, the server sends a response back to the client, often through a callback function or message queue. This pattern is particularly beneficial for tasks involving network calls, database interactions, or any scenario where the client doesn’t need to wait for the server’s response to proceed. It improves responsiveness and throughput by allowing the client and server to work independently. However, it introduces additional complexity compared to synchronous communication, as the client needs a mechanism to handle the eventual response.

This pattern is generally implemented using async/await framework and the coroutines in languages such as python.


![Source: https://learn.microsoft.com/en-us/azure/architecture/patterns/async-request-reply](../assets/reqrep_pattern.webp)

### Publish Subscribe Pattern
The Publish-Subscribe pattern also known as pub sub is an alternative pattern of asynchronous communication. The advantage of pub sub over request reply is that pub sub patterns allows for a loose coupling between publishers and subscribers.

The loose coupling is established by using a message broker component which uses topics to establish connection. The message broker efficiently routes the message to all interested subscribers. This pattern forms the backbone of microservices architecture.

Some common implementations are message queues and event buses. Some of the open source implementations for usage is the RabbitMQ, Apache Kafka.


![Source: https://learn.microsoft.com/en-us/azure/architecture/patterns/publisher-subscriber](../assets/pubsub_pattern.webp)

### Fire and Forget Pattern
The fire-and-forget pattern is a simple approach to asynchronous communication where a sender transmits a message without waiting for a response or confirmation. This pattern prioritizes sending the message quickly and efficiently, and the sender does not track its delivery status.

It’s often used for one-way tasks like sending logs, notifications, or initiating background processes. While fire-and-forget offers simplicity and speed, it lacks the guarantee of message delivery.

Common implementations include message queues, email clients, or any system that allows sending messages without requiring feedback. However, it’s crucial to consider the potential for lost messages and design your system accordingly, especially if reliable delivery is critical.

### Event Driven Pattern
The event-driven pattern structures applications around the concept of events — significant occurrences within the system. Producers (components that trigger events) publish these events, carrying relevant data about the happenings. Consumers (components interested in these events) subscribe to specific events or categories.

When an event is published, the event broker efficiently routes it to all interested consumers. Consumers then process the event information to perform their designated tasks.

This loose coupling and asynchronous nature make event-driven systems highly scalable, responsive, and adaptable to changes. Common implementations include message brokers, event buses, and pub-sub systems configured to handle event routing and delivery.

The event-driven pattern is well-suited for microservices architectures, real-time applications, and scenarios where components need to react to changes in the system without tight dependencies on each other.


![An example of event driven architecture Source: https://learn.microsoft.com/en-us/archive/msdn-magazine/2018/february/azure-event-driven-architecture-in-the-cloud-with-azure-event-grid](../assets/event_driven_pattern.webp)

### Websockets
WebSockets, the persistent two-way communication channels for web applications, thrive alongside asynchronous programming patterns. Here’s how they work together:

- Persistent Connection: Unlike traditional HTTP requests, WebSockets establish a long-lived connection between the client and server. This eliminates the need for repeated connection setup, improving efficiency.
- Asynchronous Communication: Both client and server can send and receive messages asynchronously, meaning they don’t have to wait for a response before sending the next message. This allows for real-time data exchange without blocking the main application flow.
- Event-Driven Model: WebSockets often leverage an event-driven approach. The server can push messages to the client, triggering event handlers on the client-side to react to the received data. This enables real-time updates and interactive experiences.

## Conclusion
While sync patterns are easy to implement async patterns bring real scalability to code that is written to bring software products to users.

If readers notice any mistake please do mention in the comments and it will be corrected. 