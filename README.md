# rtek-os: A Virtual Operating System Experiment

## Introduction

rtek-os is an experiment in virtual operating system design. Instead of constructing a complete OS from the ground up, it leverages a host operating system's kernel and other APIs to create a virtual environment. The virtual environment consists of host OS processes, each representing a virtual process within rtek-os. Communication between these virtual processes is achieved by redirecting standard input/output (stdin/stdout), effectively creating a message-passing "network" protocol. This innovative approach enables developers to replace the native OS programming interface within their binaries.

## Goals and Objectives

The primary goal of rtek-os is to enable "write once, run anywhere" functionality, allowing software to be developed on one platform and executed seamlessly on various others.  While binaries still need compilation per instruction set architecture (unless using "fat" or "source" binaries), rtek-os aims to minimize platform-specific dependencies. The project also seeks to optimize performance by leveraging the underlying host OS while offering cross-compilation capabilities. This could enable, for example, MS Windows applications to be developed on Linux, or X11/Wayland applications to be developed on MS Windows.

## Proof of Concept

The initial proof of concept will focus on establishing the core functionality of the virtual kernel. This kernel will provide:

1. Stream Interface: Access to stdin, stdout, and stderr for communication between virtual processes.
2. File API: A simplified file API that utilizes the host file system.
3. VNC-like Interface: A virtual network computing (VNC)-like interface to facilitate graphical windowing environments.

## Future Development

As rtek-os evolves, future development may include:

* Expanded APIs: A broader range of APIs for various system functionalities.
* Performance Optimization: Continuous refinement to enhance performance and resource utilization.
* Cross-Compilation Toolchain: Development of robust tools to support cross-compilation across different platforms.
