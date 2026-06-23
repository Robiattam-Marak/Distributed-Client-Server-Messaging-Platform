# Distributed Client-Server Messaging Platform

A scalable TCP-based chat system built in C++ that uses a load balancer to distribute client connections across multiple backend servers.

## Features

- Client-server communication using TCP sockets
- Load balancing across multiple chat servers
- Concurrent client handling using multithreading
- Real-time message delivery
- Fault-tolerant architecture
- Modular and extensible design

## Architecture

Client
   |
   v
Load Balancer
   |
   +----> Server 1
   |
   +----> Server 2
   |
   +----> Server 3

## Tech Stack

- C++
- POSIX Sockets
- Multithreading
- Linux

## Project Structure

```
.
├── client/
├── load_balancer/
├── server/
├── include/
├── src/
└── README.md
```

## Build

```bash
g++ server.cpp -o server -pthread
g++ client.cpp -o client -pthread
g++ load_balancer.cpp -o load_balancer -pthread
```

## Run

Start servers:

```bash
./server 5001
./server 5002
./server 5003
```

Start load balancer:

```bash
./load_balancer 4000
```

Start clients:

```bash
./client 127.0.0.1 4000
```

## Future Improvements

- User authentication
- Chat rooms
- Message persistence
- Heartbeat monitoring
- Dynamic server scaling

## Author

Robiattam N. Marak  
Electronics & Electrical Communication Engineering  
IIT Kharagpur
