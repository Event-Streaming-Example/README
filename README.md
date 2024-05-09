# Event-Streaming Example

Getting started with the ESE Project

## What is ESE?

ESE is a small project which aims to help one understand how Kafka came into existance, what usecase it solved and how.

## Why is this required?

Kafka forms the backbone of nearly every major organization. All of them use some sort of streaming applications. Be it live updates, implementing event-driven architecture, for analytical purposes, anything. When it is so much in abundance, why not try to learn a bit about it and give ourselves an edge :)

## So will we tackle the internals of Kafka?

No. We will not be dissecting Kafka and its components. Rather we shall be creating a project and try to implement it; both with and without using Kafka. Not only will this better help us understand what component of Kafka is used where and why (we won't be tackling "how") and more importantly help us appreciate it.

## What is this project we are talking about?

We shall be trying to solve the usecase of getting live updates from a web app! In order to "relay" these updates from our web-app to some destination, we shall be using 2 sources- One is the traditional client-server architecture where we shall have a 'microservice' written in Go that handles these events. And in other source, we shall be using Kafka. By the end, we will compare and see where one is better/worse over the other.

## What are the major components here?

This project primarily has:
- A client (which will produce events)
- A server (which will try to 'store' these events)
- A consumer (which will run some business logic on top of these events)

Rest all components are there mainly to facilitate these 3. For example the ese-mailer doesn't necessarily partake in getting events from the web-app to the destination BE, but is rather used as a trigger for our consumer (when it has finished running the business usecase).

## How can I get started?

The repos are detailed enough to make one understand what each component does. However, still a few guidlines to help:

1. The code in all the repos follow the clean code architecture (with domain layer, data layer, etc) as much as possible.
2. All the code in the repos can be run via docker. Hence setup should be fairly easy. There are also instructions as to how to run the project without docker.
3. To understand the big picture, I would recommend going over the [ese-orchestration](https://github.com/Event-Streaming-Example/ese-orchestration) repo first. This will help understand the overall architecture and also how to run the entire project on your machines.
