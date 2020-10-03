# Computer-System Organization

A very brief overview of the organization of a Computer System. A book such
as [Computer Organization and Design][COaD] would be a much more detailed
exploration of this topic.

## Computer-System Operation

A modern general-purpose computer has one or more CPUs and multiple device
controllers connected through a common bus that provides access to shared
memory.

- Each device driver is responsible for controlling a specific type of
  device (e.g. disk drives, audio devices, displays).
- The CPU and device controller can execute in parallel, but competes for
  memory cycles.
- A memory controller synchronize access to shared memory.

### Bootstrap Phase

A computer needs an **bootstrap program** to start running (e.g. when powered up
or rebooting).

- The bootstrap program is typically stored in **read-only memory (ROM)**, or
  **electrically erasable programmable read-only memory (EEPROM)**. This is
  typically known as **firmware**.
- The bootstrap program initializes all aspects of the system, including CPU
  registers, device controllers, memory contents, etc.
- The bootstrap program must know how to load the OS and how to start executing
  the OS, by locating the kernel and loading it into memory.

### System Initialization Phase

Once the kernel is loaded and begins executing, it can begin providing services
to the rest of the OS and its users.

- Some services might be provided outside the kernel by systems programs that
  are loaded into memory at boot time to become **system processes** or
  **system daemons** that almost has the same lifetime as the kernel.
    - On UNIX, the first system process is `init` which starts many other
      daemons.

Once this phase is completed, the system is fully booted and awaits events
to occur.

### System Operation Phase

When an event occurs, it is typically signalled by an software or hardware
**interrupt**.

- Hardware can trigger interrupts, at any time, by sending a signal to the
  CPU typically via the system bus.
- Software can trigger an interrupt via a **system call** (aka
  **monitor call**).

When the CPU is **interrupted**, it pauses current task and immediately
transfers execution to a designated fixed location, which usually contains
the starting address of the **interrupt service routine (ISR)** which is
responsible for handling the interrupt. Once the ISR finishes execution,
execution control is returned to the CPU and it resumes the interrupted
computation.

[COaD]: https://www.elsevier.com/books/computer-organization-and-design-risc-v-edition/patterson/978-0-12-812275-4
