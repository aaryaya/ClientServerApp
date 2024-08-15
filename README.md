
## Java Client-Server Application

## Overview

This project implements a multi-client server application in Java using socket programming. The system features client-server communication with support for multiple clients, where one client is designated as the coordinator. Clients can communicate with the server and other clients, and the server handles client disconnection gracefully.

## Features

- **Multi-client support:** The server can handle multiple clients simultaneously.
- **Coordinator assignment:** The first connected client is designated as the coordinator. If the coordinator disconnects, a new coordinator is automatically selected.
- **Private messaging:** Clients can send private messages to other clients using their client IDs.
- **Member details retrieval:** Coordinators can retrieve the details of all connected clients, including IP addresses and ports.
- **Graceful disconnection handling:** The server manages both graceful and abrupt client disconnections, updating all clients accordingly.

## How It Works

1. **Server Setup:**
   - The server listens on port `6000`.
   - When a client connects, the server checks if the client ID is unique.
   - The first client to connect becomes the coordinator.
   - The server broadcasts messages to all connected clients.
   - When a client disconnects, the server removes the client from the list and reassigns the coordinator if necessary.

2. **Client Setup:**
   - Clients connect to the server by providing the server's IP address, port (`6000`), and a unique client ID.
   - Clients can send messages to all clients or private messages to specific clients.
   - The `/quit` command disconnects the client from the server.

## Commands

- **/quit:** Disconnect from the server.
- **@<clientId> <message>:** Send a private message to a client.
- **/memberdetails (Coordinator only):** Retrieve information about all connected clients.

## Getting Started

### Prerequisites

- **Java Development Kit (JDK):** Ensure that JDK is installed on both the server and client machines.

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/aaryaya/ClientServerApp.git
   cd ClientServerApp
   ```
2. **Compile the Java files:**
   ```bash
   Server.java
   client.java
   client2.java
   client3.java
   ```

### Running the Server

1. Start the server:
   ```bash
   java Server
   ```
   - The server will start and listen for incoming client connections on port `6000`.

### Running the Clients

1. Start a client:
   ```bash
   java client
   ```
   - Enter the server's IP address and port when prompted.
   - Provide a unique client ID.

## Project Structure

```bash
ClientServerApp/
├── Server.java            # Server implementation
├── client.java            # Client implementation
├── client2.java           # Client implementation
├── client3.java           # Client implementation
├── connection_info.txt    # Connection information
└── README.md              # Project documentation

```

## Future Enhancements

- Implement SSL/TLS for secure communication between clients and the server.
- Add more sophisticated error handling and logging.
- Extend the client to support a graphical user interface (GUI) for better user experience.

## License

This project is open-source and free to use.

## Author
Aarya Shirbhate

