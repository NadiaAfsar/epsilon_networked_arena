# Epsilon Networked Arena 🎮🌐

[![Java](https://img.shields.io/badge/Java-17+-orange.svg)](https://www.java.com)
[![Networking](https://img.shields.io/badge/Networking-TCP%2FUDP-green.svg)]()
[![Maven](https://img.shields.io/badge/Maven-Build-C71A36.svg)](https://maven.apache.org)
[![Swing](https://img.shields.io/badge/Swing-UI-orange.svg)](https://docs.oracle.com/javase/tutorial/uiswing/)

> **Epsilon Networked Arena** is an advanced, multiplayer game developed in Java across three phases. While the early phases focused on physics-based combat and complex enemy AI, the final phase transforms the game into a fully distributed **Client-Server multiplayer system** with real-time communication, team-based battles, and persistent data storage. This project demonstrates a strong command of **network programming**, **concurrency**, and **clean software architecture**.

## 📖 Project Overview

This project was developed for the **Advanced Programming** course at Sharif University of Technology. It evolves from a single-player geometric combat game into a networked multiplayer experience, where players can form squads, compete in ranked battles, and track their progress on a global leaderboard.

The project's primary technical focus is on **networked architecture**: designing two independent Java applications (Client and Server), managing concurrent connections, synchronizing game state across multiple clients, and persisting data in a relational database.

## 🌐 Networking & Architecture Highlights

- **Client-Server Architecture:**
  Two fully independent Java applications communicate over **TCP/UDP sockets**. The server is capable of handling multiple concurrent clients, processing requests, and broadcasting game state updates without blocking.

- **Concurrency & Thread Safety:**
  The server uses thread-safe data structures and synchronization mechanisms to handle simultaneous requests from multiple clients, ensuring data consistency and avoiding race conditions.

- **Protocol Design:**
  Custom request-response protocols were designed for communication between client and server, including message framing, serialization, and handling of disconnections and reconnections.

- **Offline Mode with Synchronization:**
  Players can play offline; their results are stored locally and synchronized with the server upon the next connection. A cryptographic **hash function** is used as a lightweight integrity check on the synchronized data to detect accidental corruption during storage or transmission.

- **Server CLI:**
  Administrative commands (e.g., `initiateSquadBattle`, `terminateSquadBattle`, and game speed adjustments) are executed at runtime via an integrated CLI.

## ✨ Key Game Features

- **Phase 1 (Core Engine):** Geometric combat with *Epsilon* vs. Trigorath, Squarantine, and dynamic frame shrinkage. Physics-based movement (acceleration/deceleration) and collision detection.
- **Phase 2 (Advanced Mechanics):** Complex enemies (Necropick, Archmire, Black Orb), Boss fights (Smiley), AoE attacks, Global Routing, and a Skill Tree system.
- **Phase 3 (Networked Multiplayer):**
  - **Squad Battles:** Team-based PvP modes including *Monomachia* (1v1) and *Colosseum* (2v2 vs. AI).
  - **Leaderboard:** Global ranking system showing survival time and XP across all players.
  - **Squad Vault:** In-game economy for team-wide buffs (Call of Palioxis, Call of Adonis).
  - **Offline Mode:** Full offline gameplay with automatic synchronization of results to the server.

## 🛠️ Tech Stack & Tools

| Category | Technologies |
|---|---|
| **Language** | Java 17+ |
| **UI/Graphics** | Swing |
| **Networking** | Java Sockets (TCP/UDP) |
| **Build Tool** | Maven |
| **Logging** | SLF4J, Log4j |

## 🏗️ Architecture & Design Patterns

- **MVC (Model-View-Controller):** Applied across all phases to separate game logic, UI, and control flow.
- **Event-Driven Architecture:** Used for handling asynchronous game events (collisions, wave spawns, network packets).
- **SOLID Principles:** Ensured maintainability and scalability of the networked codebase.
- **Reflection & Annotations:** Used for automating wave generation and implementing a centralized exception handler.
- **Design Patterns:** Observer, Factory, Singleton, Request-Response.
