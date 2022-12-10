---
layout: post
title:  "API311 Event Driven Architectures"
categories: reinvent2022 application
permalink: /:categories/:title
---

# API311 Event Driven Architectures

Eric Johnson @edjgeek

[Resources](https://serverlessland.com/reinvent2022/api311) 

## Session Recording

[Link to session recording](https://www.youtube.com/watch?v=SbL3a9YOW7s)

Event-driven architectures can solve many difficult problems in modern enterprise workloads. For example, it can be challenging to work with large amounts of data in different data stores and locations. Teams building microservices architecture often find that integration with other applications and external services can make their workloads more monolithic and tightly coupled. In this chalk talk, learn how to use event-based architecture to decouple and decentralize application components. Discover how you can use AWS messaging services to connect microservices and coordinate data flow using minimal custom code.

## Topics

- Integration Patterns
- Event Driven Architectures
- Event Duplication → Idempotency

## Patterns

- Coupling - measure of independent variability between connected systems
- Decoupling comes at a cost
- Coupling isn’t binary or one dimensional

## Facets of Coupling

- Tons, all about dependencies

> The appropriate level of coupling depends on the level of control you have over the endpoints
> 

## Sync Request-Response Model

- Is a blocking call
- Advantages
    - low latency
    - simple
    - fast fail
- Disadvantages
    - Receiver failures
    - Receiver throttles

## Async Point to Point (queue)

Always bias towards asynchronous

- Advantages
    - Decreases temporal coupling
    - Resilient to receiver failures
    - Receiver controls consumption rate
    - Only one receiver can consume each message
- Disadvantages
    - Response correlation
    - Backlog recovery time
    - Fairness in multi-tenent systems

## SQS

- FIFO available
- Dead letter queues

## Async Router

- Disadvantages
    - increases location coupling
    - Sender maintains routing logic
    - Send complexity increases over time - as new routes are added

> Only code when you have to - use services
> 

## Use a Bus!

- Advantages
    - Reduces location complexity
    - Efficient for senders and receivers

## Eventbridge

- Fully managed service
- Rules
    - pattern matching expressed as JSON objects
- Default & custom eventbridges
- 20+ target & destination services

# Event Driven Architecture

> All serverless is event driven
> 

Event driven defined: Something happens, and we respond

## Properties of Events

- Signals that a system’s state has changed
- events occur in the past
    - e.g., Order created
- Events cannot be changed (immutable)
- Decrease coupling by restricting to key data only

## Sparse Events vs. Full State

Look up sparse events

### Full state

- event schemas should be backwards compatible
- may increase duplication
- cost to calculate values can increase over time

## Choreograph events between Domains using subscriptions

- Orchestrate a business process within a domain resulting in a published event
- Orchestrate with Step Functions

## Step Functions

- SDK integrations → call services directly
- JSON, CDK, Juypter SDK

### Step Function Request Response Service Integration Pattern

- Synchronous
- Asynchronous
- Wait for a callback (.waitForTaskToken)
    - Use lambda to process failures
- Run a Job (.sync)
    - Does not work with SDK
- Orchestration + Choreography: better together

## Handling Event Duplication - using idempotency

> No matter how many times I send a request, my system will produce the same effect no matter how many times that request is received
> 

## Duplication

- Problem sending ACKs
    - time-outs
    - at least once delivery
- Solve with Idempotency tokens
    - Client generated
    - Client retries - use same token!!
    - Use DynamoDB table for inflight transactions
- Warning: EventBridge is not idempotent
    - Create a key to examine on the back end.