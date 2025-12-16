# Minimal TCP Server Framework (C, Process-Based)

This project is a **lightweight TCP server framework written in C** that provides a simple abstraction over low-level socket APIs while demonstrating core UNIX network programming concepts.

The server supports **callback-based connection handling**, **process isolation using `fork()`**, and a minimal `server` / `connection` interface for sending and receiving data.

---

## ✨ Features

- TCP server built directly on POSIX sockets
- Callback-driven connection handling
- Process-per-connection model using `fork()`
- Simple `server` and `connection` abstractions
- Built-in error and status handling
- Supports concurrent clients
- Minimal dependencies, pure C

---

## 🧠 Architecture Overview

### Server Lifecycle
1. Create socket
2. Bind to port
3. Listen for incoming connections
4. Accept client connections
5. Fork a child process per client
6. Invoke user-defined callback
7. Clean up and terminate child process

### Connection Model
- Each client connection is handled in a **separate process**
- The parent continues accepting new clients
- Child processes isolate failures and simplify concurrency
