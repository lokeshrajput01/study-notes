# Computer Fundamentals

## 1. What is a Computer?

A computer is an electronic device that accepts data as input, processes it according to instructions, stores data, and produces output.

Basic computer cycle:

**Input → Processing → Output → Storage**

Example:
When I type `10 + 20`, the keyboard provides the input, the CPU processes it, and the result is displayed as output.

---

## 2. Hardware and Software

### Hardware

Hardware refers to the physical components of a computer that can be physically touched.

Examples:
- CPU
- RAM
- SSD
- Motherboard
- Keyboard
- Mouse
- Monitor

### Software

Software is a collection of programs and instructions that tells a computer what tasks to perform.

Examples:
- Windows
- Linux
- Google Chrome
- Discord
- VS Code
- Python

### Hardware vs Software

**Hardware = physical components**

**Software = programs and instructions**

---

## 3. CPU

CPU stands for **Central Processing Unit**.

The CPU executes instructions and performs calculations and operations required by programs.

Important CPU concepts include:
- Cores
- Clock speed
- Instructions
- Cache

A CPU can have multiple cores, which allow it to handle multiple tasks concurrently.

---

## 4. RAM

RAM stands for **Random Access Memory**.

RAM is the computer's working memory. It temporarily stores data and programs that are currently being used.

RAM is **volatile memory**, which means the data stored in RAM is generally lost when power is removed.

Example:

When I open Google Chrome, the operating system loads the required program data into RAM so it can be used while Chrome is running.

---

## 5. Storage

Storage is used to store data for long-term use.

Examples:
- HDD
- SSD
- NVMe SSD

Storage can contain:
- Operating systems
- Applications
- Documents
- Photos
- Videos
- Logs

Storage is **non-volatile**, meaning data remains stored even when the computer is turned off.

### RAM vs Storage

| RAM | Storage |
|---|---|
| Working memory | Long-term storage |
| Volatile | Non-volatile |
| Used by running programs | Stores programs and files |
| Usually faster | Usually slower than RAM |

Simple analogy:

**RAM = working desk**

**Storage = cupboard**

---

## 6. Operating System

An operating system (OS) is system software that manages computer hardware and provides an environment for applications to run.

Examples:
- Windows
- Linux
- macOS
- Android

An operating system manages things such as:
- Processes
- Memory
- Files
- Devices
- Users
- Permissions
- Networking

Basic relationship:

**User → Application → Operating System → Hardware**

---

## 7. Program and Process

### Program

A program is a set of instructions stored on a computer.

### Process

A process is a program that is currently being executed by the operating system.

Basic flow:

**Program → Loaded by OS → Process → Uses CPU and RAM**

For example, Google Chrome is a program installed on the computer. When I start Chrome, the operating system creates and manages processes for it.

---

## 8. Users and Permissions

Operating systems have different users and accounts.

Users can have different levels of permissions.

Permissions control what a user or program is allowed to access or modify.

This is important in cybersecurity because giving unnecessary permissions can increase security risks.

### Least Privilege

The principle of least privilege means giving a user or program only the permissions required to perform its necessary tasks.

---

## 9. Client and Server

A **client** is a device or application that requests a service or resource.

A **server** is a system that provides a service or resource.

Examples:

- Web browser → Web server
- Email client → Mail server
- SSH client → SSH server

Basic communication:

**Client → Request → Server**

**Client ← Response ← Server**

---

## 10. Virtualization

Virtualization allows a virtual computer to run inside a physical computer.

The physical computer is called the **host** and the virtual machine is called the **guest**.

Example:

**Physical Laptop → VirtualBox → Linux Virtual Machine**

Virtual machines are useful in cybersecurity because they can be used to create separate environments for learning and testing.

---

# Practical Observation

I used Windows Task Manager to observe running processes and system resources.

### Processes observed

| Process | CPU | Memory |
|---|---:|---:|
| Google Chrome | 0.1% | 604.4 MB |
| Discord | 0.5% | 259.4 MB |
| Notion | 0.2% | 219.9 MB |

### My System

- **CPU:** Intel Core Ultra 225H
- **Cores:** 14
- **Logical processors:** 14
- **RAM:** 16 GB DDR5
- **Storage:** NVMe SSD
- **GPU:** Intel Arc 140T

### What I learned from the practical observation

CPU usage and memory usage are different resources.

For example, Chrome was using very little CPU at the time of observation but was using around 604 MB of RAM.

I also observed running processes through Windows Task Manager, which helped me connect the concepts of processes, CPU, and memory with a real computer.

---

# Key Takeaways

- A computer accepts input, processes data, stores data, and produces output.
- Hardware is the physical part of a computer.
- Software consists of programs and instructions.
- The CPU executes instructions.
- RAM is temporary and volatile working memory.
- Storage is long-term and non-volatile.
- The operating system manages hardware and provides an environment for applications.
- A running program becomes a process managed by the operating system.
- Users and permissions control access to system resources.
- A client requests services and a server provides them.
- Virtualization allows virtual machines to run on physical computers.
