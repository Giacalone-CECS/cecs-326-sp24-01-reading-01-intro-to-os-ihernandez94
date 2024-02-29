[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/SqkZA8g-)

# CECS 326 Reading Assignment: Introduction to Operating Systems

## Ivan Hernandez 010757940

### Assignment Description

Answer the following questions from the Chapter 1 reading from your text- book. Be through and complete with your answers. You may work on these questions with one or two other partners, but *all* students must submit the document individually in their own repositories along with each student's name documented with the submission.

1. What are the two main functions of an operating system?
    An **operating system** is a layer of software that sits above the hardware and that runs in kernel mode.
    **Kernel mode** is what allows the OS complete access to all of the hardware and execute any instructions that hardware can execute.

    The two main functions of an operating system are to be an **extended machine** and to be **resource manager**.
    By extended machine, I mean that an operating system provide application programs with good abstractions that can create and manage a clean abstract set of resources without having to deal with the architecure of the hardware. This in turns allows the users to deal with these abstractions with a **user interface**, such as command-line shell or a GUI. This is the top-down view of the complex system. Examples include: *disk drivers* for I/O devices and *files*.

    The operating system is also a resource manager, which means it provides an orderly and controlled allocation of hardware resouces such as: processors, memories, and I/O devices. This is also seen as the bottom-up view of the complex system. This view shows that the operating system is in charge of tracking program resources and handling any conflict requests through **multiplexing**. The multiplexing of hardware resources is either done through: space or time. Examples include: *print queues* and *allocating disk space*.

2. What is the difference between timesharing and multiprogramming systems?
    With the popularization of the IBM 360, came the introduction of **multiprogramming** systems, and then **timesharing**.

    Multiprogramming is the concept to have multiple jobs including the operating system inside memory partitions. This would allow jobs to rotate from waiting on I/O to using the CPU. This was done through jumping with a program counter that would loop forever. This was achievable with the concept of spooling, loading new jobs from cards on the disk into any empty memory partitions.

    As multiprogramming became ubiquitous, there was an issue with slow response times. So programmers turned to timesharing, a variant of multiprogramming. Timesharing is the concept of allocating the CPU among different tasks that need service by users taking turns using online terminals. This allowed fast service to a number of users, while big batch jobs could be worked in the background while the CPU is idle. The operating system is in charge of what programs next and for how long. Timesharing didn't become popular until necessary protection hardware was mainstream.

3. The family-of-computers idea was introduced in the 1960s with the IBM System/360 mainframes. Is this idea now dead as a doornail or does it live on?
    The idea of a single family of compatible computers that all run on the same architecture and instruction set is still alive and kicking as seen in the growth of personal computers and smartphones. Huge examples in the personal computer space are Windows and MacOS. Windows is based on the x86 architecture which allows software made for Windows XP to still run on an Windows 11 computer no matter the price or performance. The same can be said the iPhone and Macs, both share the ARM architecture which allows apps built for the iPhone to be able to run on any Apple silicon Macs or iPad tablets with no issues.

4. What is the difference between kernel and user mode? Explain how having two distinct modes aids in designing an operating system.
    The difference between kernel mode and user mode is that the operating system resides in the kernel mode and the application programs and the user interface programs reside in the user mode. The user interface programs are the lowest level of user mode and they allow the user to start other programs. A key detail in the differences between both modes, that only a subset of machine instructions are available for user mode. This means that instructions that change I/O or hardware resources are off limits. For example, you can modify the browser, but you cannot mess with the clock interrupt handler.
    Having two different modes is important in designing an operating system, so as to not only protect the hardware from users/programs but to also provide the application programmers a cleaner and nicer way of acesssing the hardware. This abstraction creates Kernel Mode programs, such as drivers, to allow User Mode programs to work on any hardware with a lower complex knowledge.

5. On early computers, every byte of data read or written was handled by the CPU (i.e., there was no DMA). What implications does this have for multiprogramming?
    Multiprogramming was an evolution of the batch systems of old. While older computers wasted their CPU time trying to read or write the next byte of data from memory, this meant that the CPU sat on idle, which would hold up the current job. Multiprogramming was able to separate the memory and CPU so that one job could do I/O and another could keep the CPU busy.But the CPU still had to read or write every byte of date sequentially.

6. There are several design goals in building an operating system, for example, resource utilization, timeliness, robustness, and so on. Give an example of two design goals that may contradict one another.
    Two huge goals in designing and building an operating system are resource utilization and robustness. These two design goals may be able to interfere with one another. There needs to be a balance in robustness when designing an operating system, or you will have unchecked user-mode programs that will over utilize hardware resources such as memory or disks. That is why it's important that drivers are coded properly, or you will end up with an unstable system.

7. Which of the following instructions should be allowed only in kernel mode?
    (a) Disable all interrupts.
    (b) Read the time-of-day clock.
    (c) Set the time-of-day clock. (d) Change the memory map.

    Both instructions A (disable all interrupts) and D (change memory map) should only be allowed in kernel mode since they both affect the hardware. Instructions B and C are user mode since they only affect the clock for the operating system.

8. Consider a system that has two CPUs, each CPU having two threads (hyperthreading). Suppose three programs, P0, P1, and P2, are started with run times of 5, 10 and 20 msec, respectively. How long will it take to complete the execution of these programs? Assume that all three programs are 100% CPU bound, do not block during execution, and do not change CPUs once assigned.

    According to the hyperthreading, the operating system sees the two CPUS with the two threads as four CPUs since hypertreading allows the CPU to hold the state of different threads. Each program, P0, P1, and P2, will be running on their own individual thread. EVen though the CPU switches from each thread in a nanosecond, it will take 20 msec to finish executing all three programs. This is due to the fact that each program cannot switch CPUs and each CPU can only do process at a time.

9. What is a trap instruction? Explain its use in operating systems.
    The *TRAP* instruction is an interrupt in the operating system that is caused either by a system-call or an eror like dividing by 0 or a floating point overflow. It allows the CPU to switch from user mode to kernel mode and starts the operating system. The operating system then decides what to do with the program. Control is then passed back to the user program.
    When the trap instruction is done through a system-call, the calling progams pushes the parameters to the stack, in user space. The trap instruction is then read from a fixed address in the operating system. The return address is saved on the stack, which is based on a single fixed location or there is an 8-bit field that determines the jummp address through index table in memory. The operating system is in charge of handling the system-call number and running the correct system-call handler based on a table of pointers. Once the system call handler is done, control is then returned to the user program.

10. Modern operating systems decouple a process address space from the machine’s physical memory. List two advantages of this design.
    Modern operating systems, such as Windows, decouple the process address space from the physical memory. This is to allow Microsoft to able to able to change the system calls at any point in time without invalidating any existing programs. Another advantage to this design is the introduction of virtual memory. Virtual memory is where the operating system splits the address space into the main memory and the disk. This allows processes to take up less address space in the main memory and this in turn lets main memory be able to hold more processes. 

### Deliverables

Commit the answers to the questions in a readable file to your git repository by the due date and time indicated with your repository. Approved file submission formats are: .txt, .md, .pdf. .html (renderable) or anything that is web-readable on Github. Other formats will only be accepted with explicit approval.
