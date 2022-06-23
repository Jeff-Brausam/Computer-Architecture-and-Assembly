# Computer-Architecture-and-Assembly
These are my notes from my computer architecture and assembly class.

## Chapter 1 Application Level
## General
Abstraction level structure of a computer system (some don’t have level 2): <br />
7 Application level (games, apps, ect) <br />
6 High-order language level (programming languages, C++, Python, etc.) <br />
5 Assembly level <br />
4 Operating System level <br />
3 Instruction set architecture level <br />
2 Microcode level <br />
1 Logic Gate level (hardware electrical pulses, +3v for 1 (on), 0v for 0 (off)) <br />

*Hardware* - Physical components of your computer. <br />
*Software* - A set of programs that instructs and modifies hardware. <br />
Three basic hardware components in a computer: *Central Processing Unit* (CPU), *Main Memory* (RAM), *Disk* (Storage, SSD, CD-R, CD-RW, CDs Etc) <br />
Information flows through components through a System Bus. <br />
CPU has the smallest storage capacity, followed by Main Memory, then Disk with the largest. <br />
CPU has the fastest speed, followed by Main Memory, then Disk with the slowest. <br />

The three activities of a program are **input > processing > output**. <br />
In software design, you are given an input (a problem), you must then process it (come up with a solution), and have an output (a solved solution.) Another example of this is, you hit a keyboard key, the cpu then processes it, and communicates with RAM and such to figure out that key, then it is displayed (output) to your monitor. 

*Algorithm* - A set of instructions, that when carried out in the proper sequence, solves a problem in a finite amount of time. <br />
*Program* - an Algorithm written for execution on a computer. They can’t be written in English. They must be in a language for one of the seven levels of a computer. <br />
*Software* - A program that controls the computer. There are two types of software: Systems software and Applications Software. <br />
System Software allows the computer to be accessible to application designers. Application software makes a computer system to be accessible to end users (general people). <br />

### CPU
CPU has a small set of memory called registers, the typical number is from 16-64 slots. <br />
CPU has a set of instructions wired into its circuitry. It can do things like, fetch information from the main memory into a register, add, subtract, compare, store information from a register into memory, etc. <br />
In a program like j = i + 1 in a programming language (like Java or C), the program runs like this:
* First fetch the value of i from memory into a CPU register. (Flows from the storage cell in memory, to the system bus, into the register). 
* Second add 1 to the value in the register (Happens entirely in CPU). 
* Third, store the incremented value into memory. <br />

### Main Memory
Main Memory (or RAM) has a set of memory cells to store information (like CPU in a way). It differs by having a far greater number of cells. They can have billions of cells. <br />
It differs from CPU in the sense that it doesn’t have instructions wired into its circuitry to process data in its registers. Even though its capacity of memory is huge, it can’t process the values it stores. Its only function it can perform is to remember the data values stored in its cells and produce them for the CPU or the disk on request. <br />
Main memory stores 4 kinds of information: <br />
    * Data to be processed by the CPU 
    * Program instructions to be executed by the CPU
    * Input connections to receive data from the external environment
    * Output connections to send data to the external environment. 
When you load a program from disk, it goes into Main Memory. From there it can interact with CPU. <br />
Sometimes instead of variables, it needs to fetch an instruction from memory (say for app instructions.) It is similar to how it would store a variable, but it comes from where the instruction is stored. The instruction is copied to a special-purpose register in the CPU called the instruction register. The electronic circuitry in the CPU is designed to analyze the instruction in the instruction register and execute it. <br />

#### Memory-Mapped I/O 
A few locations in memory are reserved for input and output connections. This is called memory-mapped input/output or memory-mapped I/O. <br />
An example of this is your keyboard. When you press a key on the keyboard, it detects which key, and sends information representing that connection to the input connection in main memory. Then the keyboard sends a signal to CPU informing that key was pressed. In response, the CPU fetches the character from the input connection so it can be processed. The only real difference between this and something stored in memory, is that this comes from something like a keyboard connection wired into the storage cell in main memory. <br />
An example of a output device is a monitor. After the computing of the input, it will output the information to the device that is mapped to the output. 

### Disk
Like CPU and main memory, the disk has a set of memory cells to store information. <br />
Disk memory is **nonvloatile**, main memory (RAM) is **Volatile**. This means that when you turn the power off, your information in memory is kept. Unlike with RAM, if power is lost, all of your values in memory are lost. <br />
Disk memory capacity is greater than memory capacity. The number of storage cells on a disk are typically in the trillions. <br />
Although it has high storage capacity, it has lower speed compared to main memory. This is because of the different access methods of the two types of storage. RAM has random access memory, meaning that if you fetch information, you can immediately get it back from the other end without having to pass over the information inbetwen. <br />
Disks have sequential access, meaning you have to go through the information until you find what you are looking for. Even with SSD drives, this makes it slower than main memory. <br />
Thre is one more way to access memory called direct memory access. The disk has its own special-purpose processor, called a DMA controller, whose only function is to transfer information over the system bus between disk and main memory. The CPU initiates a transfer of information through the DMA controller, which talks between those two, and signals back when to the CPU when the transfer is complete. <br />

### Operating Systems
*Operating System* - the systems program that makes hardware useable. <br />
An operating system has three general functions: File management, memory management, and processor management. <br />
Similar to how people in an office store files, things on a computer are stored in directories. <br />
There are three types of information inside files: Documents, programs, and data. <br />
Directories, and files are stored on the disk. To open a file or use it, it has to load into main memory when executed by an input (a click, etc). <br />

A rule of thumb when solving a problem: 
  * First, understand the problem. 
  * Second, outline a solution. 
  * Third, solve each part of your outlined problem. 
  * Lastly, test your solution. 

### Space and Time
Computers store and process information in the form of electrical signals. Each signal is either a high voltage level, represented by the digit 1, or a low level, represented by the digit 0. Because there are only two possible values for each signal, it is called a binary digit, or bit. <br />
A *bit* is the smallest unit of digital information. <br />
Different parts of the computer system can have bit sequences with different lengths. In CPU registers, there are usually 32 or 64 bits. In main memory, it is always a sequence of 8 bits. <br />
A sequence of 8 bits is called a *byte*. On all computer systems, each memory cell in main memory is one byte. <br />

Like how things take up storage (space) there is also the concept of time. The CPU is responsible for this. This is measured in GHz or gigaherz, a unit of frequency. A hertz is one cycle per second, so these can cycle billions of cycles per second. <br />

Another concept of time is moving information from one computer component in the system to another. These are through channels, which can be wires in a system bus in a computer, or between cell phone towers. <br />
*Bandwidth* is the quantity of information that can be carried per unit of time. <br />

### Database Systems
*Database* - A collection of files that contain interrelated information. <br />
*Database system (or database management system, or DBMS)* - A program that allows users to add, delete, or modify records in the database. <br />
*Query* - a request for information, usually in parts of the database. <br />
There are many types of databases, for inventory of a store, banks, etc. <br />
*Relational database systems* - store information in files that appear to have a table structure. That is a structure with a fixed number of columns and a variable number of rows. <br />

## Chapter 2 High-Order Language
High-order languages must be compiled into instruction set architecture level (level 3) before being able to be executed. This book uses C. The class though uses C++, so some terminology is adjusted. 

A program written in C, in a text editor is a source program. <br /> 
The machine language version (compiled) is called an object program. <br /> 
The way this works is **input(source program) > processing(compiler) > Output(Object program)** <br />
Your compiler is software not hardware. <br />
When a program at ISA3 (level 3) it is computer dependent, you can’t run it on two different brands of computers. Languages at high-order though can be executed and will be slightly modified on the other. <br />
If you have a C program, you want it written on both Mac and WIndows, you need to compile it on both systems, to be able to distribute that on both systems. If it only is compiled for one, it won’t work on the other. You only need one C program though. 

### C Memory Model
C has three kinds of variables, global, local, and dynamically allocated variables. The value of a variable is stored in the main memory of a computer, but where is dependent on the variable. <br />
*Global variables* are stored at a fixed location in memory. <br />
*Local variables* and parameters are stored on the run-time stack. <br />
*Dynamically allocated variables* are stored on the heap. These come into existence with the execution of the malloc() function, and cease to exist with the execution of the free() function. <br />

A stack is a container of values that stores values with the push operation and retrieves them with the pop operation. For storage, the retrieval is last in first out (LIFO). When you pop a value, you get the last one that was pushed on. Think of it as a stack of plates, you “stack” items on top of eachother, and remove it by the top. 

Every C statement that executes is part of a function. 

### Global Variables and Assignment Statments
Every C variables has three attributes: A name, type, and value. A name is what a programmer gives it, a type specifies the value it can have. <br />
Variables declared outside of main (where you would declare #include and such) are global variables. 

### Comments
Comments in C begin with two slash characters //.

### Include
The #include keyword allows you to make a library of functions available to a program. In most cases you want one with the standard input/output. To do that at in C++, at the top of your file you would type: #include <iostream>
using namespace std;  (include to use cout and cin without std::) <br />

A standard convention is that if a program returns 0, it indicates that there are no errors that have occurred during the program’s execution. 

### Assignment
The = is the assignment operator. You can assign values and other things just like in other programming languages like this. 

### Variables
Constants are variables that cannot change. You assign it by const <type> <name> = <value> <br />
Like const int bonus = 10; <br />
Global variables are allocated at a fixed position in main memory. <br />
Local variables are allocated on the run-time stack. In C, local variables are declared within the main program. 
Integers = whole numbers. Floating point = decimals. <br />

### Flow of Control
If else statements and loops can take in conditions. Those conditions control the flow of the pogram. Ways to compare or designate that control are with operators. <br />

### Relational operators
   | operator     | meaning            |
| ------------ | --------------- |
| ==        | equal to        |
| <    | less than     |
| > | greater than |
| >=         | greater than or equal to          |
| !=        | not equal to       |

### Boolean operations
   | operator     | meaning            |
| ------------ | --------------- |
| &&       | AND        |
| ||    | OR     |
| ! | NOT |

Switch statements are like if statements. 

### While loop
The while loop checks if a condition is true, then runs until the condition is false.
Do while loop
A do while loop is like a while loop, except it runs a statement first, then checks if a condition is still true after. 

### Arrays
Arrays are declared with brackets. The number inside of the bracket specifies how many elements will be allocated inside of an array. int myArray[4] allocates an array with the variable name myArray with 4 spaces. 

### Functions
In C there are two kinds of functions, those that return void (nothing), and those that return some other type. 

### Call by value functions 
Call by value means you are returning a value from a function (or it is void)

Allocation (in memory) takes place on the run-time stack in the following order when you call a void function:
* Push the actual parameters
* Push the return address 
* Push storage for local variables

A formal parameter is the parameter in the function declaration. <br />
An actual parameter is the parameter in the function call. 

To deallocate from the stack, the program:
* Pops the local variables 
* Returns the return address and use it to determine the next instruction to execute
* Pop the parameters

The program uses this return address to know which statement to execute next in the main program after executing the last statement of the void function. 

In contrast to void functions, nonboid control returns from the function to the calling statement. Void ones return to the statement following the calling statement. 

### Call by reference
If you have the intent to change the value of the actual parameter in the calling program, then call by reference is used instead. The formal parameter gets a reference to the actual parameter. If the procedure changes the value, the corresponding parameter in the calling program changes. To specify a parameter is called by reference, you pass the address of the actual parameter with the *address operator*. <br />
& is the *address operator*. You would type something like int &x <br />
It can also be used to get the memory address of a variable; which is the location of where the variable is stored on the computer. <br />

The corresponding formal parameter is a pointer, and in C use must use a * like above with the & operator. 

A *pointer* however, is a variable that *stores the memory address* as its value.

Struct is an what an object would be in C++. They are a key to data abstraction in C++. You can consolidate different types inside of an struct, whereas an array can only take one type. You first need to create a struct, then “construct” it. 
   
## Chapter 3 Instruction Set Architecture Level
The CPU reads information from memory, and writes information into memory. The information is divided into words. Some computer systems have large sets of words, from a few hundred to few thousand, grouped into pages. 

### Binary Storage
Electronic computers **cannot store numbers and letters directly**. They can **only store electrical signals**. When CPU reads information from memory, it detects a signal whose voltage is equal to that produced by two flashlight batteries (3v).

Computer memories are designed with this property. Each location contains either a high-voltage signal (1) or a low voltage signal (0) and nothing inbetween. 

*Binary* means that only two values are possible in digital computers. This is also known as counting in Base 2. <br />
*Base 10* is decimal, also known as the way we count as humans. <br />
Each individual storage unit is called a *binary digit* or *bit*. A bit can only be 1 or 0. <br />
Bits in a computer system are grouped together in cells. You can think of a cell as a group of boxes, containing a 1 or 0, and nothing else. <br />
An eight bit cell is called a *byte*. <br />
Practically all computers today have eight bits per cell in their main memories and disks. <br />

Information such as numbers and letters must be represented in binary form to be stored in memory. <br />
The representation scheme used to store information is called a *code*.
