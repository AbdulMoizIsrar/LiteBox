# LiteBox 🐳
### Lightweight Linux Container Runtime

> A mini Docker built from scratch in C++ — CSC322 Operating Systems Project

**Abdul Moiz Israr | SP24-BCS-002 | BCS-5A**

---

## What is LiteBox?

LiteBox is a lightweight Linux container runtime built in C++.
In simple words — it creates small, isolated "mini computers" 
(containers) inside your Linux machine where programs can run 
independently without affecting each other.

Just like Docker, each container gets:
- Its own filesystem
- Its own IP address
- Its own memory limit
- Its own CPU limit
- Full process isolation

---

## Features

- Container spawn with full Linux namespace isolation
- Memory & CPU resource limits via cgroups v2
- Virtual networking with automatic IP assignment
- Real-time resource monitoring dashboard
- Container registry with persistent logs
- Filesystem snapshot & restore
- IPC messaging between containers
- Simple Bash CLI frontend

---

## Tech Stack

| Component | Technology |
|---|---|
| Language | C++17 |
| Isolation | Linux Namespaces (pid, mnt, uts, ipc, net) |
| Resources | cgroups v2 |
| Threading | POSIX threads & shared memory |
| CLI | Bash shell script |
| Test Image | Alpine Linux rootfs |

---

## Installation & Usage

### Requirements
- Linux kernel 5.10+
- g++, make, iproute2, iptables, rsync

### Build & Install
```bash

litebox/
├── src/
│   ├── engine.cpp      # Main container engine
│   ├── container.h     # Container config & lifecycle
│   ├── cgroups.h       # Resource limits (RAM/CPU)
│   ├── network.h       # Virtual networking
│   ├── snapshot.h      # Snapshot & restore
│   ├── monitor.h       # Real-time stats dashboard
│   ├── ipc.h           # Inter-process communication
│   ├── registry.h      # Container registry
│   └── utils.h         # Utility functions
├── scripts/
│   └── litebox         # Bash CLI frontend
└── Makefile

---

## How It Works
litebox run /opt/alpine
│
▼
Clone process with namespaces
(pid + mnt + uts + ipc + net)
│
▼
Apply cgroup limits
(memory + CPU quota)
│
▼
Setup virtual network
(assign IP address)
│
▼
pivot_root into rootfs
(isolated filesystem)
│
▼
Execute /bin/sh
(container is running!)



## License

MIT License — free to use and modify.



*Built with ❤️ for CSC322 Operating Systems*
