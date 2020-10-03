# Introduction

An **operating system** (OS) is a piece of systems software that is responsible
for managing the computer's hardware.

- Provides a basis for application programs and act as an abstraction layer
  between the computer user and the hardware.
- OSes come in many flavors, with varying design objectives and prioritization
  that influences how trade-offs are resolved.
    - Some OSes are designed to emphasize *convenience*, while others emphasize
      *efficiency*, or some combination of the two.

## Roles of an Operating System

A Computer System can be roughly partitioned into four components:

1. **Hardware**.
2. **Operating system**.
3. **Application programs**.
4. **Users**.

- The **hardware** consists of:
    - The **Central Processing Unit (CPU)**.
    - The **memory**.
    - The **input/output (I/O) devices**.
- The **application programs** (e.g. word processors, browsers, compilers)
  utilize these resources to solve the users' computing problems.
- The OS *manages* these shared resources and *coordinates* their usage among
  the various application programs and multiple users.

A Computer System can also be viewed as hardware + software + data, which
provides an **environment** for which application programs can perform
useful work for the user.

- It can be viewed from the *user*-side, or the *system*-side.

!!! info "Key Takeaway"

    OSes should be designed with respect to the intended use cases and tasks,
    such that the design goals should be used to drive design decisions and
    resolve trade-offs.

### User View

- From the user's perspective, their view of the computer varies w.r.t. the
  interface deployed.
- A typical Personal Computer (PC) involves a monitor, keyboard, mouse and
  system unit that the user utilizes to do work.
    - This type of system is intended for one user to monopolize the resources.
    - The design goal is to minimize friction and maximize work effiency that
      the user desires to achieve.
    - The OS is primarily designed for ease of use, then effiency, which in
      turn is prioritized over resource utilization.
- Another case could be a terminal to a mainframe or minicomputer where
  multiple users may access the same computer, who may share resources and
  exchange information.
    - The OS applied here should emphasize maximizing resource utilization
      to ensure users have fair share to CPU time, memory and I/O.
- Workstations and servers may have OSes designed to compromise between
  individual usability and resource utilization.
- Mobile phones may have touch screens, but are still computers and run
  mobile-optimized OSes.
- Some embedded computers may have minimal or none user view, but their
  OSes (if any) are designed to be reliable and can run without user
  intervention.

### System View

From the computer's POV, the OS is the systems program that is closest to
the hardware – an OS can be said to be a **resource allocator**.

- A Computer System may have many **resources** that can be utilized to solve
  computing systems, such as CPU time, memory, storage, I/O, etc.
- The OS *manages* these **resources**, where multiple application programs
  and users may wish to access these limited and shared resources. It is
  thus the responsibility of the OS to determine how to allocate these
  shared resources to that application programs and users can access these
  resources efficiently and fairly.
- The OS is also responsible for *managing* the various I/O devices and user
  programs; it is a **control program** that manages the execution of
  user programs to prevent errors and misuse of computer resources.

## Defining Operating System

As OSes are designed to solve various design problems and to satisfying
vastly differentiating design goals, it is difficult to come up with a
universal definition for what an OS is – the best we can do is to try to
extract a smallest common subset.

Typically, the Operating System is defined to be *at least* the **kernel**,
which is the program that must outlive all other **systems programs** and
**application programs**.

- **Systems programs** may be associated with the OS but need not be part of
  the kernel.
- **Application programs** depend on operations provided by the OS.

In mobile OSes, typically they include both a kernel and also **middlewares**
which include software frameworks that provide additional services to
application developers (**Software Development Kits (SDKs)**).
