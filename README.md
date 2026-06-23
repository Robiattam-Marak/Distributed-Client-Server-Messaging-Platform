# Distributed Client-Server Messaging Platform

## Project Overview

This project implements a distributed chat system consisting of multiple backend chat servers and a load balancer. The load balancer distributes incoming client connections across available servers to ensure efficient resource utilization and improved scalability.

The system is built using TCP sockets in C++ and demonstrates concepts such as network programming, concurrent server design, load balancing, and client-server communication.

---

## Components

The system consists of three main components:

### Chat Servers (S1, S2, ...)

Backend servers responsible for handling client communication.

Responsibilities:

* Accept client connections forwarded by the load balancer.
* Manage message exchange between connected clients.
* Maintain information about active client sessions.
* Report current server load to the load balancer.
* Handle multiple clients concurrently.

### Load Balancer (L)

Acts as the entry point for all client connections.

Responsibilities:

* Accept incoming client connections.
* Periodically monitor backend server load.
* Select the least-loaded server.
* Forward client connections to the selected server.
* Improve system scalability and availability.

### Client (C)

The user-facing application.

Responsibilities:

* Connect to the load balancer.
* Send and receive chat messages.
* Display server responses.
* Gracefully disconnect from the system.

---

## Features

* TCP socket-based communication
* Concurrent client handling
* Dynamic load balancing
* Multi-server architecture
* Real-time messaging
* Scalable design
* Modular implementation

---

## System Architecture

Client
|
v
Load Balancer
|
+----> Chat Server 1
|
+----> Chat Server 2
|
+----> Chat Server N

---

## How It Works

1. A client connects to the load balancer.
2. The load balancer checks the load of all available servers.
3. The least-loaded server is selected.
4. The client is assigned to the selected server.
5. Messages are exchanged between clients through the server.
6. Server load information is periodically updated.

---

## Technologies Used

* C++
* POSIX Sockets
* TCP/IP Networking
* Multithreading
* Linux System Programming

---

## Build

```bash
g++ server.cpp -o server -pthread
g++ load_balancer.cpp -o load_balancer -pthread
g++ client.cpp -o client -pthread
```

## Run

### Start Chat Servers

```bash
./server 5001
./server 5002
```

### Start Load Balancer

```bash
./load_balancer 4000
```

### Start Client

```bash
./client 127.0.0.1 4000
```

---

## Future Improvements

* User authentication
* Chat rooms and channels
* Message persistence
* Server failure recovery
* SSL/TLS encryption
* Distributed server discovery
* Containerized deployment using Docker

---

## Learning Outcomes

This project demonstrates:

* Socket programming
* Network protocols
* Concurrent server architecture
* Load balancing techniques
* Distributed systems fundamentals
* Client-server communication models

---

## Author

Robiattam N. Marak

Electronics and Electrical Communication Engineering

Indian Institute of Technology Kharagpur
