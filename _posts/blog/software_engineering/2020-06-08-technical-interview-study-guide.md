---
layout: page
title:  "Technical Interview Study Guide"
date:   2020-06-08
categories:
  - blog
  - tech
teaser: "WIP: Building a study guide for when I need to start doing tech interviews again."
---

## Concepts

#### Big O Notation
1. Time
* think about how runtime changes as N gets bigger
* O(1) - constant
* O(N) - linear
* O(logN) - cutting the problem space in half each time (binary search)
* O(NlogN) - merge sort
* O(branches^depth) - recursive functions
* it's possible for O(N) to run faster than O(1) for specific inputs
* do this, then when you're all done, do that - add runtimes
* do this for each time you do that - multiply runtimes
* if there are multiple inputs, don't use N for all of them!

2. Space
* O(N) space - creating array of size n
* O(N^2) space - creating a two-dimensional array of size NxN
* [stack space in recursive calls](https://py3.codeskulptor.org/#user307_IR2jhP5XNx_0.py){:target="_blank"}

#### Compiled vs. Interpreted Language
* compiled language - can optimize, makes the code more efficient
* interpreted - has to go line by line

#### Stack vs. Heap Allocation
* heap used when amount of memory required is not known in advance
* known by the compiler at compile time typically goes on the stack; dynamically allocated at runtime - on the heap

#### Heap
| Operation | Time Complexity | Notes |
|------------|-----------------|-------|
| pop        | O(log n)        | Visualize bubbling down the new root to the last level of the tree. |
| push       | O(log n)        | Visualize bubbling up the new element to the root of the tree. |
| peek       | O(1)            | Access the root of the heap. |
| heapify    | O(n)            | Just memorize this! |

* min-heap: each node has a value <= value of both its children
  * use to find top K largest
* max-heap: each node has a value >= value of both its children
  * use min-heap to find top K smallest

Resources: https://www.hellointerview.com/learn/code

## Data Structures
* arrays
* linked lists
* trees, tries, graphs
* stacks & queues
* heaps
* hashmaps

#### Hashmaps
* simple implementation: array of linked lists + hash code function
* O(1) lookup time

#### Arrays (resizable)
* O(1) insertion time (amortized)

#### Array vs. Linked List
* arrays are good for random access
* linked lists are good for adding or removing items (array has to resize and copy over), or when you're not sure how many items will be in the list

## Algorithms
* BFS - queue (FIFO) to find shortest path; level order traversal
* DFS - stack (LIFO)/recursion (call stack) to explore full paths; post/in/pre order traversals
      - time complexity: O(N) - post-order/bottom-up: visit each node once and do constant amount of work
      - space complexity: O(H) - height of the tree (calls on the call stack)
* binary search - find target value in sorted array; repeatedly divides search range in half
* merge sort - split array and recursively sort each half, then merge two sorted halves
* quick sort - partition array around "pivot"; smaller on left, larger on right; recursively sort partitions in place
* BUD optimization (bottlenecks, unnecessary work, duplicated work)

## Notes
* point out any error checking that you'd do

#### TODO
* DFS vs. BFS
* abstract vs. interface
* dynamic programming
* [longest palindrome](http://www.codeskulptor.org/#user40_9kU6XL8njr_1.py){:target="_blank"}
* [pascal's triangle](http://www.codeskulptor.org/#user40_RUTIiY3yBb_1.py){:target="_blank"}
* [fibonacci](http://www.codeskulptor.org/#user40_5HpDWjI6xF_1.py){:target="_blank"}
* [roman numerals](https://py3.codeskulptor.org/#user305_bZoAtXI4Pd_0.py){:target="_blank"}
* much much more

## Questions
* What are your favorite things about working here?
* How would you describe the company culture?
* What brought you to this company?
* What has been the most challenging for you?
* What does a typical day look like for you?
* What typical meetings would I be expected to attend?
* What is your expectation for a successful candidate to get up to speed?
* Who decides what a team works on? How does project planning happen?
* How do we get feedback?
* How is the current state of documentation and test coverage? Is the codebase healthy? Is there a lot of tech debt being ignored?
* Is communication asynchronous or are there a lot of meetings?
* Pair programming?
* What is your management style? How do you help people grow?


### System Design

#### Non-functional Requirements
* latency, performance
* reliability
* scalability (rps, DAU)
* throughput
* security
* fault tolerance
* CAP theorem
  * can only choose 2/3: consistency, availability, and partition tolerance
  * partition tolerance (system continues operating, even if some parts of the network can't talk to each other) is guaranteed in distributed systems, so choose between consistency and availability
  * do i need strong read after write consistency? does every single read of my system HAVE TO read the latest write? -> choose consistency (banking, ticket booking, etc.)


API Gateway
- routing - determine which BE service should handle each incoming request
- authentication/authorization
- rate limiting
  - fixed window counter (easy to implement, boundary effect/starvation)
  - sliding window log (no boundary effect, implemented with a heap so more memory)
  - sliding window counter (approximation, but less memory with count prev and curr window)
  - token bucket (tokens refilled at steady rate, remove 1 token each request, reject if no tokens in bucket)

DB Indexing
- don't need efficient data access or table size <10k rows -> full table scan
- text search -> inverted index (maps words to documents)
- location data -> geospatial index
- in-memory exact matches -> hash index (or B-Tree, because hash index does not support range queries or sorting efficiently)
- everything else -> B-Tree (logarithmic time complexity for insert/delete/search)


* ACID properties of transactions - ensure DB transactions are reliable, consistent, and safe, even in the presence of errors/crashes
  * Atomicity - prevents partial updates; either all operations go through or rollback
  * Consistency - prevents corrupted data; DB goes from one valid state to another valid state
  * Isolation - prevents race conditions
  * Durability - prevents data loss on crash

HTTP status codes
- 2XX: success
  - 200 ok
  - 201 created
- 3XX: redirection
- 4XX: client error
  - 401 unauthorized
  - 403 forbidden
  - 404 not found
  - 429 too many requests
- 5XX: server error

HTTP methods
- POST: create a new resource
- GET: read an existing resource
- PUT: update (replace) an existing resource
- PATCH: update (modify) an existing resource
- DELETE: delete an existing resource

Cassandra - write optimized, can handle large writes per second
  - batches writes (keeps writes in memory, then flushes and writes to disk)
  - eventual consistency

DynamoDB

Partitioning - splitting data within a single db (e.g. users by region)
Sharding - splitting data across multiple dbs/servers (horizontal scaling)

SSE - server-sent events: one-way, persistent connection from server -> client
  * can be used for "new notifications" indicators, live dashboards, comment streams, etc;
- over HTTP
- built in browser support for reconnection
- just looks like a long running HTTP request
- HTTP headers indicate we'll be sending chunks

Websockets
- bidirectional
- its own protocol (not HTTP)
- all infra needs to support upgrading from HTTP to websocket
  - load balancers, proxies, firewalls, etc all need to negotiate this upgrade

| Feature | SSE (Server-Sent Events) | WebSockets | Long Polling |
|---------|-------------------------|------------|--------------|
| Protocol | HTTP (`text/event-stream`) | Custom over TCP (upgraded via HTTP) | HTTP |
| Connection Type | Persistent | Persistent | Repeated requests |
| Direction of Communication | Server → Client only | Client ↔ Server | Client → Server (request), Server → Client (response) |
| Use Case Examples | Stock tickers, live dashboards, live comments | Chat apps, multiplayer games, collaborative editing | Legacy systems, environments without persistent connections |
| Complexity | Simple | Moderate | Simple but inefficient |



Push notifications - APN or FCM

Load Balancer
  - round robin
  - least connections
  - hashing - consistent hashing helps distribute load evenly when nodes are added or removed
  - client-to-gateway or gateway-to-server
