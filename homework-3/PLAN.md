# Open Source Contributions

The three open-source projects which I'm interested in: **Ethpreneur**, **Fast Music Remover**, and 
**Seata**. Below are the descriptions of these projects and the tasks I 
will be working on.

## 1. Ethpreneur 🌐

**Project Overview**  
Ethpreneur is a decentralized platform for listing companies as NFTs and 
enabling users to trade company stocks as digital assets. It is built 
using Next.js, TypeScript, and Thirdweb, providing a secure and 
user-friendly interface for decentralized ownership and trading of company 
shares.

### Key Features:
- 🏢 **Company Listings**: Decentralized companies listed and represented 
as NFTs.
- 💼 **NFT Stocks**: Trade company shares as NFTs.
- 🔐 **Wallet Authentication**: Secure login via crypto wallets like 
MetaMask.
- 📊 **Dashboard for Company Owners**: Manage company performance, issue 
new shares, and track ownership.
- 💻 **Cross-chain Support**: Supports multiple blockchain networks for 
seamless transactions.
- 🎨 **Dark Mode**: Toggle between light and dark themes for a 
personalized user experience.

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
The project is known for its near-realtime processing capability, making 
it efficient for a variety of use cases such as interview editing, social 
media content preparation, and more.

### Key Features:
- 🚀 **Fast Processing**: Processes media at 8% of its original length, 
making it highly efficient.
- 🎧 **Noise Removal**: Designed to remove background music, sound 
effects, and other noise while preserving voice tracks.
- 🌐 **Offline Media Processing**: Focused on offline analysis but has 
future plans for live feed support.

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

### Key Features:
- **Distributed Transaction Management**: Provides a solution to the 
problem of managing distributed transactions across microservices.
- **High Performance**: Optimized for speed and scalability.
- **Extensible Architecture**: Designed to be easily extended for various 
use cases.

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


