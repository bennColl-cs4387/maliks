# Open Source Contributions

This document provides an overview of three 
open-source projects I'm interested in : **Ethpreneur**, **Fast Music Remover**, and 
**Seata**. Below are the descriptions of these projects and the tasks I 
will be working on.

## 1. Ethpreneur 🌐

**Project Overview**  
Ethpreneur is a decentralized platform for listing companies as NFTs and 
enabling users to trade company stocks as digital assets. It is built 
using Next.js, TypeScript, and Thirdweb, providing a secure and 
user-friendly interface for decentralized ownership and trading of company 
shares.


### My Contribution: Dark Mode Implementation
- **Task**: Implement a dark mode feature to enhance the user experience 
for users who prefer a dark theme, especially when interacting with 
blockchain platforms.
- **Tools**: Tailwind CSS, Next.js
- **Details**:
  - Add dark mode styles using Tailwind CSS.
  - Provide a toggle switch in the navigation bar for users to switch 
between light and dark modes.
  - Ensure that all UI elements (buttons, text, cards) adapt properly to 
dark mode.

[GitHub Issue 
Link](https://github.com/SpandanM110/Ethpreneur/issues/9#event-14445753676)

---

## 2. Fast Music Remover 🎵

**Project Overview**  
Fast Music Remover aims to provide a fast and lightweight tool for 
removing music, sound effects, and noise from any media. Currently, it 
supports offline processing but aims to support live feeds in the future. 


### My Contribution: Command-Line Interface (CLI)
- **Task**: Implement a basic CLI for Fast Music Remover that will allow 
users to process media files via command line.
- **Language**: C++
- **Details**:
  - Accept a file path as an argument for media processing.
  - Default to the "process" operation if no subcommand is provided.
  - Structure the CLI for easy addition of subcommands and options in the 
future.
- **Goal**: Create a functional CLI that is lightweight and flexible for 
future extensions.

[GitHub Issue 
Link](https://github.com/omeryusufyagci/fast-music-remover/issues/10#event-14446148603)

---

## 3. Seata: Simple Extensible Autonomous Transaction Architecture 🛠️

**Project Overview**  
Seata is a distributed transaction solution for microservices 
architectures. It addresses the complexity of ensuring data consistency 
across distributed systems by offering a high-performance and 
user-friendly transaction management system. Seata helps to coordinate 
transactions across multiple microservices to maintain consistency in case 
of failures or distributed database issues.


### My Contribution: Issue Resolution for Concurrent Modification 
Exception
- **Task**: Investigate and resolve a `ConcurrentModificationException` 
error that occurs during session conversion in the Seata backend.
- **Details**:
  - Trace the exception in the log to find its root cause.
  - Modify the session handling logic to prevent concurrent modification 
errors.
- **Goal**: Ensure smooth operation of session management to avoid service 
disruption due to this exception.

[GitHub Issue Link](https://github.com/seata/seata/issues/4217)


