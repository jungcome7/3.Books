# Operating System Concepts
### 지은이 : AbrahamSilberschatz, PeterBaerGalvin, GregGagne
### 출판사 : WILEY
### 읽은 날 : 2020.01.22 ~

<Preface & Contents>

‘Operating systems are an essential part of any computer system. Similarly, a course on operating systems is an essential part of any computer science education.’

Part 1. Overview
1. Introduction
2. Operating-System Structures

Part2. Process Management
3. Processes
4. Threads & Concurrency
5. CPU Scheduling

Part3. Process Synchronization
6. Synchronization Tool
7. Synchronization Examples
8. Deadlocks

Part 4. Memory Management
9. Main Memory
10. Virtual Memory

Part 5. Storage Management
11. Mass-Storage Sturcture
12. I/O Systems

Part6. File System
13. File-system Interface
14. File-System Inplementation
15. File-System Internals

Part 7. Security and Protection
16. Security
17. Protection

Part 8. Advanced Topics
18. Virtual Machines
19. Networks and Distributed Systems

Part 9. Case Studies
20. The Linux System
21. Windows 10

Part 10. Appendices
A. Influential Operating Systems
B. Windows 7
C. BSD UNIX
D. The Mach System

---------------------------------------------------

Chapter1. Introduction

An operating system is software that manages the computer hardware. The hardware must provide appropriate mechanisms to ensure the correct operation of the computer system and to prevent programs from interfering with the proper operation of the system.

A fundamental responsibility of an operating system is to allocate these resources to programs.

The operating system includes the always-running kernel, middleware frameworks that ease application development and provide features, and system programs that aid in managing the system while it is running.

Hardware may trigger an interrupt at any time by sending a signal to the CPU, usually by way of the system bus. (There may be many buses within a computer system, but the system bus is the main communications path between the major components.) Interrupts are used for many other purposes as well and are a key part of how operating systems and hardware interact,

The CPU can load instructions only from memory, so any programs must first be loaded into memory to run.

CPU – The hardware that executes instructions.
Processor – A Physical chip that contains one or more CPUs.
Core – The basic computation unit of the CPU.
Multicore – Including multiple computing cores on the same CPU.
Multiprocessor – Including multiple processors.

Another form of interrupt is a trap(or an exception), which is a software-generated interrupt caused either by and error (for example, division by zero or invalid memory access) or by a specific request from a user program that an operating-system service be performed by executing a special operation called a system call.

The CPU is never idle.

Multitasking is a logical extension of multiprogramming. In multitasking systems, the CPU executes multiple processes by switching among them, but the switches occur frequently, providing the user with a fast response time. Consider that when a process executes, it typically executes for only a short time before it either finishes or needs to perform I/O. I/O may be interactive; that is, output goes to a display for the user, and input comes from a user keyboard, mouse, or touch screen. Since interactive I/O typically runs at “people speeds,” it may take a long time to complete. Input, for example, may be bounded by the user’s typing speed; seven characters per second is fast for people but incredibly slow for computers. Rather than let the CPU sit idle as this interactive input takes place, the operating system will rapidly switch the CPU to another process.

If several processes are ready to run at the same time, the system must choose which process will run next. Making this decision is CPU scheduling.

We must ensure that the operating system maintains control over the CPU. We cannot allow a user program to get stuck in an infinite loop or to fail to call system services and never return control to the operating system. To accomplish this goal, we can use a timer. A timer can be set to interrupt the computer after a specified period. The period may be fixed (for example, 1/60 second) or variable (for example, from 1 millisecond to 1second).