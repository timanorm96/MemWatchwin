# MemWatch (Windows Edition)

A lightweight CLI memory monitoring utility for Windows written in pure C. It utilizes the native Windows API (`WinAPI`) to retrieve precise physical memory metrics in real-time.

---

## Features

* **Low Overhead:** Written in native C without any heavy third-party dependencies.
* **WinAPI Integration:** Uses `GlobalMemoryStatusEx` to fetch extended physical memory states, ensuring full support for modern systems with >4GB RAM.
* **Accurate Metrics:** Tracks and displays total vs. available RAM directly from the Windows kernel.

---

## Technical Details

The core of the application relies on the `SysSnap` structure, designed to store system performance snapshots:

```c
typedef struct {
    unsigned long long total_mem; // Total physical memory in KB
    unsigned long long free_mem;  // Free physical memory in KB
    double cpu_usage;             // Reserved for CPU metrics
} SysSnap;


Requirements

    OS: Windows 7 / 8 / 10 / 11

    Compiler: GCC (MinGW-w64), MSVC, or Clang

