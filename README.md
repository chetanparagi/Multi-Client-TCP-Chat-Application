# TCPChatX

A TCP-based multi-client chat application built with Python.

## Introduction

TCPChatX is a simple and lightweight chat application powered by the Python `socket` library, demonstrating client-server communication, TCP sockets, and concurrency with multi-threading.

## Features

* Command support (`/help`, `/online`, `/quit`)
* CLI for both server and client
* Multi-client support with threading
* Real-time message broadcasting
* Graceful connection handling

## Setup

Clone the repository and install the only dependency:

```bash
pip install colorama
```

## Usage

Start the server:

```bash
python pyChat-server.py
```

Start a client:

```bash
python pyChat-client.py
```

By default, the server runs on `localhost:25000`. You can update `host` and `port` in the `.py` scripts if needed.

## How It Works

### Server

* Uses TCP sockets for reliable communication.
* Handles multiple clients concurrently with threading.
* Processes user commands or broadcasts messages to all clients.

### Client

* CLI-based interface with multi-threading.
* Separate threads handle sending and receiving messages.
* Displays timestamps for received messages.

## Networking Logic

1. **Connection Setup** – TCP 3-way handshake.
2. **Message Handling** – Client ⇔ Server communication.
3. **Connection Teardown** – TCP 4-way handshake.

## Debugging & Verification

Verified using **Wireshark** packet captures:

* Successful 3-way handshake on connection.
* Correct broadcast behavior.
* Proper 4-way handshake on disconnection.

## Troubleshooting

If running outside a LAN, configure **port forwarding** on your router to allow external connections to the server.

## Known Issue

* Messages may visually overlap when typing while another message is received. Input buffer remains unaffected.
* Possible fix: use `curses` library for advanced I/O handling (Unix-only).

## Tools & Skills

* **Languages/Tech**: Python, TCP/IP, Socket Programming, Multi-threading
* **Tools**: Wireshark, VS Code
