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
    The difference between kernel mode and user mode is that the operating system resides in the kernel mode and the application programs and the user interface programs reside in the user mode. 

5. On early computers, every byte of data read or written was handled by the CPU (i.e., there was no DMA). What implications does this have for multiprogramming?

6. There are several design goals in building an operating system, for example, resource utilization, timeliness, robustness, and so on. Give an example of two design goals that may contradict one another.

7. Which of the following instructions should be allowed only in kernel mode?
    (a) Disable all interrupts.
    (b) Read the time-of-day clock.
    (c) Set the time-of-day clock. (d) Change the memory map.

8. Consider a system that has two CPUs, each CPU having two threads (hyperthreading). Suppose three programs, P0, P1, and P2, are started with run times of 5, 10 and 20 msec, respectively. How long will it take to complete the execution of these programs? Assume that all three programs are 100% CPU bound, do not block during execution, and do not change CPUs once assigned.

9. What is a trap instruction? Explain its use in operating systems.

10. Modern operating systems decouple a process address space from the machine’s physical memory. List two advantages of this design.

### Deliverables
Commit the answers to the questions in a readable file to your git repository by the due date and time indicated with your repository. Approved file submission formats are: .txt, .md, .pdf. .html (renderable) or anything that is web-readable on Github. Other formats will only be accepted with explicit approval.
