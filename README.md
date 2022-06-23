# Computer-Architecture-and-Assembly
These are my notes from my computer architecture and assembly class.
<pre>
## Chapter 1 Application Level
## General
Abstraction level structure of a computer system (some don’t have level 2): 
7 Application level (games, apps, ect)
6 High-order language level (programming languages)
5 Assembly level
4 Operating System level
3 Instruction set architecture level
2 Microcode level (I think binary is here or level 3?)
1 Logic Gate level (hardware electrical pulses, +3v for 1 (on), 0v for 0 (off)

*Hardware* - Physical components of your computer.
*Software* - A set of programs that instructs and modifies hardware. 
Three basic hardware components in a computer: Central Processing Unit (CPU), Main Memory (RAM), Disk (Storage, SSD, CD-R, CD-RW, CDs Etc)
Information flows through components through a System Bus.
CPU has the smallest storage capacity, followed by Main Memory, then Disk with the largest. 
CPU has the fastest speed, followed by Main Memory, then Disk with the slowest. 

The three activities of a program are **input > processing > output**. 
In software design, you are given an input (a problem), you must then process it (come up with a solution), and have an output (a solved solution.)
Another example of it in a program, you hit a keyboard key, the cpu then processes it, and communicates with RAM and such to figure out that key, then it is displayed (output) to your monitor. 

*Algorithm* - A set of instructions, that when carried out in the proper sequence, solves a problem in a finite amount of time.
*Program* - an Algorithm written for execution on a computer. They can’t be written in English. They must be in a language for one of the seven levels of a computer.
*Software* - A program that controls the computer. There are two types of software: Systems software and Applications Software. 
System Software allows the computer to be accessible to application designers. Application software makes a computer system to be accessible to end users (general people).

### CPU
CPU has a small set of memory called registers, the typical number is from 16-64 slots. 
CPU has a set of instructions wired into its circuitry. It can do things like, fetch information from the main memory into a register, add, subtract, compare, store information from a register into memory, etc. 
In a program like j = i + 1 in a programming language (like Java or C), the program runs like this:
First fetch the value of i from memory into a CPU register. (Flows from the storage cell in memory, to the system bus, into the register). Second add 1 to the value in the register (Happens entirely in CPU). Third, store the incremented value into memory. 

### Main Memory
Main Memory (or RAM) has a set of memory cells to store information (like CPU in a way). It differs by having a far greater number of cells. They can have billions of cells. 
It differs from CPU in the sense that it doesn’t have instructions wired into its circuitry to process data in its registers. Even though its capacity of memory is huge, it can’t process the values it stores. Its only function it can perform is to remember the data values stored in its cells and produce them for the CPU or the disk on request. 
Main memory stores 4 kinds of information:
    * Data to be processed by the CPU
    * Program instructions to be executed by the CPU
    * Input connections to receive data from the external environment
    * Output connections to send data to the external environment. 
When you load a program from disk, it goes into Main Memory. From there it can interact with CPU.
Sometimes instead of variables, it needs to fetch an instruction from memory (say for app instructions.) It is similar to how it would store a variable, but it comes from where the instruction is stored. The instruction is copied to a special-purpose register in the CPU called the instruction register. The electronic circuitry in the CPU is designed to analyze the instruction in the instruction register and execute it. 

#### Memory-Mapped I/O 
A few locations in memory are reserved for input and output connections. This is called memory-mapped input/output or memory-mapped I/O 
An example of this is your keyboard. When you press a key on the keyboard, it detects which key, and sends information representing that connection to the input connection in main memory. Then the keyboard sends a signal to CPU informing that key was pressed. In response, the CPU fetches the character from the input connection so it can be processed. The only real difference between this and something stored in memory, is that this comes from something like a keyboard connection wired into the storage cell in main memory. 
An example of a output device is a monitor. After the computing of the input, it will output the information to the device that is mapped to the output. 

### Disk
Like CPU and main memory, the disk has a set of memory cells to store information.
Disk memory is nonvloatile, main memory (RAM) is Volatile. This means that when you turn the power off, your information in memory is kept. Unlike with RAM, if power is lost, all of your values in memory are lost. 
Disk memory capacity is greater than memory capacity. The number of storage cells on a disk are typically in the trillions. 
Although it has high storage capacity, it has lower speed compared to main memory. This is because of the different access methods of the two types of storage. RAM has random access memory, meaning that if you fetch information, you can immediately get it back from the other end without having to pass over the information inbetwen. 
Disks have sequential access, meaning you have to go through the information until you find what you are looking for. Even with SSD drives, this makes it slower than main memory. 
Thre is one more way to access memory called direct memory access. The disk has its own special-purpose processor, called a DMA controller, whose only function is to transfer information over the system bus between disk and main memory. The CPU initiates a transfer of information through the DMA controller, which talks between those two, and signals back when to the CPU when the transfer is complete. 

### Operating Systems
*Operating System* - the systems program that makes hardware useable. 
An operating system has three general functions: File management, memory management, and processor management. 
Similar to how people in an office store files, things on a computer are stored in directories.
There are three types of information inside files: Documents, programs, and data.
Directories, and files are stored on the disk. To open a file or use it, it has to load into main memory when executed by an input (a click, etc).

A rule of thumb when solving a problem: 
  * First, understand the problem. 
  * Second, outline a solution. 
  * Third, solve each part of your outlined problem. 
  * Lastly, test your solution. 

### Space and Time
Computers store and process information in the form of electrical signals. Each signal is either a high voltage level, represented by the digit 1, or a low level, represented by the digit 0. Because there are only two possible values for each signal, it is called a binary digit, or bit. A bit is the smallest unit of digital information. 
Different parts of the computer system can have bit sequences with different lengths. In CPU registers, there are usually 32 or 64 bits. In main memory, it is always a sequence of 8 bits. 
A sequence of 8 bits is called a byte. On all computer systems, each memory cell in main memory is one byte. 

Like how things take up storage (space) there is also the concept of time. The CPU is responsible for this. This is measured in GHz or gigaherz, a unit of frequency. A hertz is one cycle per second, so these can cycle billions of cycles per second.

Another concept of time is moving information from one computer component in the system to another. These are through channels, which can be wires in a system bus in a computer, or between cell phone towers. 
Bandwidth is the quantity of information that can be carried per unit of time. 

### Database Systems
*Database* - A collection of files that contain interrelated information. 
*Database system (or database management system, or DBMS)* - A program that allows users to add, delete, or modify records in the database.
*Query* - a request for information, usually in parts of the database. 
There are many types of databases, for inventory of a store, banks, etc. 
*Relational database systems* - store information in files that appear to have a table structure. That is a structure with a fixed number of columns and a variable number of rows. 
</pre>
