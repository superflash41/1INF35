# Killing a Process
> A process is basically a program in execution.

Each process has an **address space** and a **set of resources** like registers, a list of open files, outstanding alarms, lists of related processes and all other information needed to run the program.

A process can **create one or more processes**, who are called **child processes**. This means processes can create process tree structures.

![[process_tree.png]]

After a process has been created, it **starts running** and **does whatever its job is**. However, [nothing lasts forever](https://youtu.be/6ySRE_H-tJs), not even processes. Sooner or later **the new process will terminate**.

One of the reasons for this happens when **another process executes a system call** telling the operating system to **kill the process**. In UNIX this call is `kill` and serves to send a signal to a process.
## SIGKILL
Signal 9, also known as **SIGKILL**, is used to forcefully terminate a process. This signal **cannot be caught, blocked or ignored** by the process. This makes the most reliable way to kill a process, but it does not allows a process to clean up resources or save its sate before dying.

That's why, most times it is recommended to use signal 15 (**SIGTERM**), as it sends a request for the process to terminate gracefully.

![[sigterm_vs_sigkill.png]]


----
# References
- Modern Operating Systems - Tanenbaum
- [SIGTERM vs SIGKILL - turnoff](https://turnoff.us/geek/dont-sigkill/)
- [Hard Links versus Soft Links Explained - MicroNuggets](https://www.youtube.com/watch?v=aO0OkNxDJ3c)