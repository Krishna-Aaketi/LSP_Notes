# Linux System Programming – Complete Deep Topic Tree

## 1. File I/O (Low-Level Programming)
### 1.1 File Operations
- open(), close(), read(), write()
- pread(), pwrite(), lseek()
- File creation flags: O_CREAT, O_APPEND, O_TRUNC
- O_RDONLY, O_WRONLY, O_RDWR

### 1.2 File Descriptors
- Standard FDs: STDIN_FILENO, STDOUT_FILENO
- dup(), dup2(), fcntl()
- Inheritance during fork
- Close-on-exec flag (FD_CLOEXEC)

### 1.3 File Metadata
- stat(), fstat(), lstat()
- File types: regular, directory, socket, FIFO
- File permissions: S_IRWXU, S_IRWXG, S_IRWXO
- File timestamps: atime, mtime, ctime

### 1.4 File System Attributes
- chmod(), chown(), umask()
- access()
- Extended attributes (xattr)
- File capabilities (getcap, setcap)

## 2. Directory & Path Management
### 2.1 Directory Functions
- opendir(), readdir(), closedir()
- mkdir(), rmdir(), unlink(), rename()
- getcwd(), chdir()

### 2.2 Path Handling
- realpath(), basename(), dirname()
- symlink(), readlink(), link()

### 2.3 Directory Traversal
- Recursive traversal
- ftw(), nftw()

## 3. Process Management
### 3.1 Creation & Termination
- fork(), vfork(), clone()
- exit(), _exit(), abort()

### 3.2 Replacement
- exec family: execl(), execv(), execve(), execvp(), execle()

### 3.3 Synchronization
- wait(), waitpid()
- WIFEXITED, WEXITSTATUS, etc.
- WNOHANG, WUNTRACED flags

### 3.4 Identity
- getpid(), getppid()
- getuid(), geteuid(), setuid(), setgid()
- setsid(), setpgid()

## 4. Memory Management
### 4.1 Dynamic Memory
- malloc(), calloc(), realloc(), free()

### 4.2 System Allocation
- brk(), sbrk()
- mmap(), munmap(), mremap()
- mprotect(), msync()

### 4.3 Layout
- Text, Data, BSS, Heap, Stack
- Virtual vs physical memory
- Page size, alignment

### 4.4 Tools
- valgrind, gdb, ASan

## 5. Threads & Concurrency
### 5.1 POSIX Threads
- pthread_create(), pthread_join()
- pthread_exit(), pthread_self()

### 5.2 Attributes
- Stack size, scheduling
- Detached vs joinable

### 5.3 Synchronization
- pthread_mutex_t, pthread_cond_t
- pthread_rwlock_t, pthread_barrier_t

### 5.4 Advanced
- pthread_key_create()
- Priority inversion
- Race conditions, deadlocks

## 6. Signals
### 6.1 Basics
- signal(), sigaction()
- kill(), raise()

### 6.2 Masking & Handling
- sigemptyset(), sigfillset()
- sigprocmask(), sigpending()

### 6.3 Asynchronous
- SA_SIGINFO
- Reentrancy

### 6.4 Timers
- alarm(), setitimer()
- SIGALRM, SIGCHLD, etc.

## 7. Inter-Process Communication (IPC)
### 7.1 Pipes
- pipe(), popen(), pclose()

### 7.2 FIFOs
- mkfifo(), open(), read(), write()

### 7.3 System V IPC
- msgget(), msgsnd(), msgrcv()
- shmget(), shmat(), shmdt(), shmctl()
- semget(), semop(), semctl()

### 7.4 POSIX IPC
- shm_open(), mmap()
- sem_init(), sem_wait(), sem_post()
- mq_open(), mq_send(), mq_receive()

### 7.5 Sockets
- socket(), bind(), listen(), accept()
- UNIX domain sockets
- socketpair()

## 8. File Locking
### 8.1 Mechanisms
- fcntl(), flock(), lockf()

### 8.2 Conflicts
- Deadlocks
- Shared/exclusive
- Record locking

## 9. Timers & Clocks
### 9.1 Clock Functions
- time(), gettimeofday()
- clock_gettime(), clock_nanosleep()

### 9.2 Interval Timers
- setitimer(), getitimer()

### 9.3 POSIX Timers
- timer_create(), timer_settime()

## 10. Advanced I/O
### 10.1 Blocking
- O_NONBLOCK
- EINTR, EAGAIN

### 10.2 Multiplexing
- select(), poll(), epoll()

### 10.3 Async I/O
- aio_read(), aio_write()
- SIGIO, F_SETOWN

## 11. Daemon Programming
### 11.1 Creation
- setsid(), double fork, chdir(), umask()

### 11.2 Logging
- syslog(), openlog(), closelog()

### 11.3 PID Files
- Write/lock

## 12. Libraries & Linking
### 12.1 Shared Libraries
- gcc -fPIC -shared

### 12.2 Dynamic Linking
- dlopen(), dlsym(), dlerror(), dlclose()

### 12.3 Static vs Dynamic
- Performance, portability

## 13. /proc and /sys
### 13.1 /proc
- /proc/[pid]/, /proc/stat
- /proc/meminfo

### 13.2 /sys
- sysfs overview

## 14. Devices & ioctl
### 14.1 Device Files
- mknod(), major/minor

### 14.2 ioctl()
- User-defined commands
- Custom structs

## 15. Security & Privileges
### 15.1 UID/GID
- setuid(), seteuid()
- setgid(), setegid()

### 15.2 Capabilities
- getcap, setcap

### 15.3 Secure Coding
- Buffer overflows
- TOCTOU
- Format strings

## 16. Build & Debug
### 16.1 Makefiles
- Dependencies

### 16.2 Debugging Tools
- gdb, valgrind, strace, ltrace

### 16.3 Profiling Tools
- perf, gprof, ftrace

## 17. Rare & Advanced Topics
### 17.1 Netlink Sockets
- Kernel-user comms

### 17.2 Real-Time
- SCHED_FIFO, RR, DEADLINE

### 17.3 NUMA
- numactl, mbind()

### 17.4 Memory Barriers
- Atomic ops, sync built-ins

### 17.5 Kernel ABI Interfaces
- `prctl()`, `seccomp()`

### 17.6 Passing Techniques
- Pass-by-value vs reference
- Passing file descriptors via SCM_RIGHTS
- Shared memory object handles

### 17.7 Address Translation
- Virtual ↔ Physical address
- /proc/self/pagemap
- `mmap()` with `MAP_LOCKED`
- DMA, IOMMU (conceptual overview)

### 17.8 Linux Namespaces & Cgroups
- PID, NET, MNT, UTS, IPC, USER namespaces
- Creating containers manually
- `unshare`, `clone`, `setns`
- Resource control with `cgroups`

### 17.9 ELF Binary Internals
- ELF headers
- `readelf`, `objdump`
- Relocations, symbols

### 17.10 Kernel Interaction APIs
- Netlink, ioctl, /proc, sysfs, debugfs
- relayfs, tracepoints

### 17.11 Filesystem Internals
- Superblock, inode, dentry
- VFS layer

### 17.12 Linux Boot Process (for init programmers)
- BIOS/UEFI → GRUB → Kernel → init
- Role of /sbin/init or systemd

---

This structure now includes all core, rare, and advanced topics to fully represent Linux System Programming in depth.

