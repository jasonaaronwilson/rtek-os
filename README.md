# rtek-os

Rather than write a full OS from scratch , rtek-os is a a virtual operating system experiment using a root "kernel" host OS process that can then spawn host OS processes to contain each virtual process. stdin/stdout of these processes are "hijacked" to serve as the message passing based "network" protocol allowing us to replace the native OS programming interface with our virtual one in our binaries. The goal is write once, run everywhere (though binaries will still need to be compiled per instruction set architecture unless using "fat" or "source" binaries) and OS to obtain the best performance though we hope to cross-compile so that MS Windows applications could be developed on Linux, and X11 (or Wayland) applications can be developed on MS Windows, etc.

The initial proof on concept will provide the initial kernel which proides stream interface to stdin/stdout/stderr, a simple file API (the native host file-system is used), as well as a VNC frame-buffer like interface to support graphical windowing.

