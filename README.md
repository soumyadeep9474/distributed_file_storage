# Distributed File Storage

> **Executive summary:** This repository is currently an **early-stage Go prototype for peer-to-peer TCP transport**, not yet a complete distributed file-storage system. The implemented code starts a TCP listener, accepts concurrent peer connections, runs a pluggable handshake, decodes incoming data into messages, records the remote address, and logs received messages. File persistence, file upload/download operations, replication, metadata management, peer discovery, consistency, authentication, and a public application API are **not implemented in the current repository**.

## Project Overview

`distributed_file_storage` appears to be intended as the networking foundation for a distributed file-storage system. The present implementation focuses on the transport layer: a Go executable starts a TCP server on port `3000`, accepts connections, creates a peer abstraction, applies a handshake function, decodes incoming bytes, and prints received messages.

The repository is small and currently contains the executable entry point, a `p2p` package, a Makefile, Go module files, one test file, and a checked-in compiled binary.

### Repository layout

```text
.
├── Makefile
├── bin/
│   └── fs
├── go.mod
├── go.sum
├── main.go
└── p2p/
    ├── encoding.go
    ├── handshake.go
    ├── message.go
    ├── tcp_transport.go
    ├── tcp_transport_test.go
    └── transport.go
