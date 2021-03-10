---
layout: post
title: Operating System Service
---

# Operating System Service
This post was written based on what I studied through the operating system lecture. Also i referred to <a href="https://www.google.com/search?ei=tKpHYPPcJ9vr-Qa66om4Bg&q=Operating+System+Concepts&oq=Operating+System+Concepts&gs_lcp=Cgdnd3Mtd2l6EAMyCggAELEDEIMBEEMyAggAMgIIADICCAAyAggAMgIIADICCAAyAggAMgIIADICCAA6BwgAELADEBM6CQgAELADEB4QEzoLCAAQsAMQCBAeEBNQ7MwHWOzMB2CT0wdoAXAAeACAAZ8BiAGgApIBAzAuMpgBAKABAqABAaoBB2d3cy13aXrIAQrAAQE&sclient=gws-wiz&ved=0ahUKEwjzhozk2KPvAhXbdd4KHTp1AmcQ4dUDCA0&uact=5">Operating system concepts-9th</a>

### *Operating System Services (for user - 6)*
- **User interface** : Almost all operating systems have a UI. (Command-Line(CLI), Graphics User Interface(GUI), Batch)

- **Program execution** : The system must be able to load a program into memory and to run that program, and execution.

- **I/O operation** : A running program may require I/O.

- **File-System manipulation** : Program need to read, write, create and delete files and directories. and also list file information, permission management

- **Communication** : Processes exchange inforamtion.(via shared memory or through message passing)

- **Error detection** : it is needed to constantly aware of possible errors (may occur in CPU, memory, I/O devices, user program). OS should take appropriate action to ensure correct. Debugging facilities can enhance user's abilities to use the system.

### *Operating System Services (for system - 3)*
The operating system provides muliple survices to efficiently operate the system itself. When multiple users or multiple tasks are performed simultaneously, the operating system perform resourse allocation to allocat CPU, memory, file to users to make the system run more efficiently. It also provides **Account Management** which records the used resources of the computer. In addition, controlling system resources to protect each user's resources when multiple users exist within a system is called **Protection**.and preventing access by external users without privileges is called **Security**.

![image_1](/assets/images/OS_view.png)


### *User Operation System Interfaces*
First, **command line interpreter(CLI)** allow ditect command entry. it implemented in Kernel or systems program. somtimes commands built-in, somtimes it call out just names of programs. And **graphics user interface(GUI)** is user-friendly desktop metaphor interface. Icons represent files, programs. Many systems now include both CLI and GUI interfaces. Lastly there is **touchscreen interface**. Touchscreen devices also require interfaces. In this case, mouse is not desired. Actions and selection based on gestures. Virtual keyboard for text entry.

### *System Calls and Implementaion*
System calls are reqired to use operating system services in programs. Mostly accessed by programs via a high-level **applicatinon programming interface(API)** rather than direct system call use. API functinon list is used to expoit system calls. The system call interface has the number of system calls provided by the operating system. The appropriate system call is found according to the user's API function call, and the number is passed to the operating system through a trap. **How system call interface transmit arguments for API functions to system call?** Generally three methods used to pass arguments. **First, pass the parameters in registers**. In this case transferable arguments are limited. **Next, there is a way to store the arguments in memory and pass the addresses into the register.** Finally, there is a way to use the runtime stack. When user programs are used, they have a runtime stack. The arguments are placed in this runtime stack, and when the operating system is called, the operating system takes them out and uses them.

**The services provided by the operating system vary depending on the environment in which which the operating system runs.** MS dos uses single memory to handle single-task. Therefore there is no service required except for the ability to load and execute programs into memory. Besides for FreeBDS, shell works when user log in. when a shell read a command, it creats a new process using fork(), in which it loads a new program throgh an exec() system call. Several programs run simultaneously in memory. In such cases, various system calls are required.

![image_2](/assets/images/MSDOS,FreeBSD.png)

### *System Program*
System programs provide a convenient environment for program development and execution. Most user's view of the operation system is defined ny system programs, not the actual system calls.

![image_3](/assets/images/system_programs.png)