# Linux-THREADS-vs-Light-Weight-Process-LWP-

Linux Threads vs Light Weight Processes

Threads in Linux are nothing but a flow of execution of the process. A process containing multiple execution flows is known as multi-threaded process.

For a non multi-threaded process there is only execution flow that is the main execution flow and hence it is also known as single threaded process. For Linux kernel , there is no concept of thread. Each thread is viewed by kernel as a separate process but these processes are somewhat different from other normal processes. I will explain the difference in following paragraphs.

Threads are often mixed with the term Light Weight Processes or LWPs. The reason dates back to those times when Linux supported threads at user level only. This means that even a multi-threaded application was viewed by kernel as a single process only. This posed big challenges for the library that managed these user level threads because it had to take care of cases that a thread execution did not hinder if any other thread issued a blocking call.

Later on the implementation changed and processes were attached to each thread so that kernel can take care of them. But, as discussed earlier, Linux kernel does not see them as threads, each thread is viewed as a process inside kernel. These processes are known as light weight processes.

The main difference between a light weight process (LWP) and a normal process is that LWPs share same address space and other resources like open files etc. As some resources are shared so these processes are considered to be light weight as compared to other normal processes and hence the name light weight processes.

So, effectively we can say that threads and light weight processes are same. It’s just that thread is a term that is used at user level while light weight process is a term used at kernel level.
