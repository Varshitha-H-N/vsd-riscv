# VSDSquadron Research Internship
The program is based on the RISC-V architecture and uses open-source tools to teach people about VLSI chip design and RISC-V. The instructor for this internship is Kunal Ghosh Sir.                                                                  

# Basic Details
**Name:** Varshitha H N              
**College:** Vidyavardhaka College of Engineering Mysuru                                                                                                                                                   
**Email ID:** varshithanataraj8@gmail.com          
**GitHub:** [Varshitha H N](https://github.com/Varshitha-H-N)                                                                                                                 
**LinkedIN:** [Varshitha H N](https://www.linkedin.com/in/varshitha-h-n-037a00259/)                                                                                                                   

---

<details>
<summary> <b>task 1 :</b> The objective of this task is to thoroughly review the lab videos on C programming and RISC-V architecture to build a solid understanding of both topics. Afterward, you will apply this knowledge by compiling a C program using two different compilers:                                                              
-C language based LAB                                                                                             
-C and RISC-V based LAB          
</summary>
<br>
Task is to refer to C based and RISCV based lab videos and execute the task of compiling the C code using gcc and riscv compiler.
**C Language based LAB**

**C and RISC-V Based Labs**

This repository demonstrates the processes involved in compiling C programs and generating assembly code using both a standard GCC compiler and a RISC-V GCC compiler. It includes comprehensive steps and explanations to guide users through each stage of the compilation and debugging workflow.

**C Language-Based Lab**

Steps to Compile a .c File on Your Machine:

1. Open the bash terminal and navigate to the directory where you want to create your file.
2. Use the following command to create and edit a new .c file:
   ```sh
   leafpad sum1ton.c


**Steps to Compile a .c File on our Machine:**
 ```sh
 gcc sum1ton.c
 ./a.out
```

 
Compilation and execution complete.

![2](https://github.com/Varshitha-H-N/vsd-riscv/blob/c639c826b389c7dddc5e56f3a84409cddbe00dea/task1/Screenshot%202025-03-23%20112646.png)
)

RISC - V Based lab
**Steps to Compile Using RISC-V GCC Compiler:**
1. Ensure the RISC-V GCC compiler is installed and accessible on your system.
2. Verify the .c file contents using the cat command:
   ```sh
   cat sum1ton.c


3. Compile the C program for RISC-V architecture using 01 option:
 ```sh
riscv64-unknown-elf-gcc -o1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
```
4. Disassemble the object file to view its assembly code using:
 ```sh
riscv64-unknown-elf-objdump -d sum1ton.o
```
5.minimize the assembly by using following code:
```sh
riscv64-unknown-elf-objdump -d sum1ton.o | less
```
 a)we extract main function's assembly code by using:
   ```sh
/main
```
6. Use /main in the terminal to locate the main function in the assembly output.
![4](https://github.com/Varshitha-H-N/vsd-riscv/blob/c639c826b389c7dddc5e56f3a84409cddbe00dea/task1/Screenshot%202025-03-23%20112719.png)
)

7.Compile the C program for RISC-V architecture using ofast option:
```sh
riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
```
8.Disassemble the object file to view its assembly code using:
```sh
riscv64-unknown-elf-objdump -d sum1ton.o
```
9.minimize the assembly by using following code:
```sh
riscv64-unknown-elf-objdump -d sum1ton.o | less
```
 a)we extract main function's assembly code by using:
 ```sh
  /main
```
10. Use /main in the terminal to locate the main function in the assembly output.
![4](https://github.com/Varshitha-H-N/vsd-riscv/blob/c639c826b389c7dddc5e56f3a84409cddbe00dea/task1/Screenshot%202025-03-23%20112749.png)
)

Explanation of Key Commands and Options: 
1. -mabi=lp64: Specifies the Application Binary Interface (ABI) for 64-bit integers, pointers, and long data types, suitable for 64-bit RISC-V architecture.

2. -march=rv64i: Indicates the 64-bit RISC-V base integer instruction set architecture.

3. -O1: Enables basic optimization for better performance without significantly increasing compilation time.

4. -Ofast: Optimize the code aggressively for the best possible speed.

5. riscv64-unknown-elf-objdump: A tool for disassembling RISC-V binaries to examine the code structure and debug it effectively.
 
   </details>

---
<details>
<summary><b>Task2</b>:SPIKE Simulation and Compile the C program using RISC-V GCC/SPIKE with the above optimization options.  </summary></br>

# SPIKE SIMULATION

![spike debug](https://github.com/user-attachments/assets/06d47cef-e727-4e37-9e11-f3a1f57fbc70)


## Steps to Compile and run ./a.out thing in riscv
```sh
riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
```
```sh
spike pk sum1ton.c
```
## Steps to Debug RISC-V architecture
```sh
spike -d pk sum1ton.c
```
//debuger will open as shown above 

//Run untill the starting address of main using the command
```sh
untill pc 0 100b0
//previous value of register
reg 0 a5
//do enter and after the update value of a5 is
reg 0 a5
```
// addi sp,sp,-16 means the address of sp is subtracted by 16 to check that
```sh
until pc 0 100b8
reg 0 sp
q//to quit
```


### The values store in the 64 bits as shown below for the command lui (Load Upper Immediate) "lui a5, 0x376"


### Explanation of Key Commands:
 1. spike: This is the RISC-V ISA simulator (an instruction set simulator). Spike is commonly used for simulating and testing RISC-V programs. It emulates a RISC-V processor, running programs in a controlled environment.
 2. -d: This flag is for debugging mode. It tells Spike to run in debug mode, allowing step-by-step execution, inspecting registers, memory, etc. Useful for identifying issues and analyzing program behavior.
 3. pk: This refers to the proxy kernel, which acts as a lightweight operating system for RISC-V. The proxy kernel handles system calls and facilitates program execution in the simulated environment.
 4. addi (Add Immediate): addi sp,sp,-16
    Adds an immediate value (-16) to the value in register sp and stores the result in register sp.
 5. lui (Load Upper Immediate): lui a2, 0x31
    The value in 31 is shifted left by 12 bits and stored in the upper portion of the destination register.   


</details>
</details>
---
----------------------------------------------------------------------------------------------------------------
<details><summary><b>
Task 3: </b>undestanding the R,I,S,B,U and J Instructions</summary>


  # Introduction to Instruction of RISC-V64
In the realm of computer architecture, RISC-V stands out as a highly flexible and streamlined instruction set architecture (ISA). Within the RISC-V RV64G (64-bit) architecture, various instruction types have been ingeniously designed to optimize different computational tasks. These instruction types—including R-Type, I-Type, S-Type, B-Type, U-Type, and J-Type—each serve unique functions, from arithmetic and logical operations to memory storage and conditional branching. Understanding these instructions provides a key to unleashing the full potential of RISC-V’s modular and efficient architecture.

## Types of RISC-V Instructions
**1. R-Type Instructions:** These are Register-Register operations. They perform arithmetic and logical operations.

**2. I-Type Instructions:** Used for Immediate values typically in data transfer and arithmetic

**3. S-Type Instructions:** Store operations that utilize both a base register and an immediate offset.

**4. U-Type Instructions:** Used for Upper immediate instructions, which load large constants.

**5. B-Type Instructions:** Branch operations that allow conditional jumps.

**6. J-Type Instructions:** Jump instructions for long-range jumps.

```sh
//R-Type Instructions
opcode | rd | funct3 | rs1 | rs2 | funct7

//I-Type Instructions
opcode | rd | funct3 | rs1 | imm[11:0]

//S-Type Instructions
opcode | imm[11:5] | funct3 | rs1 | rs2 | imm[4:0]

//U-Type Instructions
opcode | rd | imm[31:12]

//B-Type Instructions
opcode | imm[12|10:5] | funct3 | rs1 | rs2 | imm[4:1|11]

//J-Type Instructions
opcode | rd | imm[20|10:1|11|19:12]
```

<details>
<summary><b>R-type Instructions</b>
  In the RISC-V architecture, the R-type (Register) instruction format is used for arithmetic and logical operations that involve registers.</summary> 
  
  Let's break down the R-type instruction format for the riscv64 (64-bit RISC-V architecture):

   ## R-type Instruction Format
 The R-type instruction format follows a specific structure consisting of six fields:
1. opcode (7 bits): Specifies the operation to be performed.
2. rd (5 bits): The destination register where the result of the operation will be stored.
3 funct3 (3 bits): Used in combination with the opcode and funct7 fields to define the exact operation.
4. rs1 (5 bits): The first source register operand.
5. rs2 (5 bits): The second source register operand.
6. funct7 (7 bits): Further refines the operation, often used to differentiate between variations of an operation.

  ### Structure
  ```sh
| funct7  | rs2  | rs1  | funct3 | rd   | opcode |
| 7 bits  | 5 bits | 5 bits | 3 bits | 5 bits | 7 bits |
```
### Example (ADD Instruction)
    add x5, x1, x2
### Instruction Breakdown
opcode (7 bits): 0110011 – Identifies the instruction as an R-type.

rd (5 bits): 00101 – Destination register x5 (in binary, register 5 is 00101).

funct3 (3 bits): 000 – Specifies the add operation.

rs1 (5 bits): 00001 – Source register x1 (in binary, register 1 is 00001).

rs2 (5 bits): 00010 – Source register x2 (in binary, register 2 is 00010).

funct7 (7 bits): 0000000 – Defines the basic add operation.
#### Detailed Bit Representation
Here's how each part fits into the 32-bit instruction format:
```sh    
| 31:25 (funct7) | 24:20 (rs2) | 19:15 (rs1) | 14:12 (funct3) | 11:7 (rd) |  6:0  (opcode) |
| 0000000        | 00010       | 00001       | 000            | 00101    | 0110011       |
// The hex representation of this add x5, x1, x2 instruction is
0x002080b3
```
</details>

<details><summary><b>I-type Instruction</b>
In the RISC-V architecture, the I-type (Immediate) instruction format is used for operations involving immediate values (constants) along with registers. This format is often used for load instructions, arithmetic operations with immediate values, and other instructions that require a constant operand.</summary>

## I-type Instruction Format
Similar to the R-type, the I-type format consists of six fields, structured slightly differently to accommodate the immediate value:

opcode (7 bits): Specifies the operation to be performed.

rd (5 bits): The destination register where the result of the operation will be stored.

funct3 (3 bits): Used in combination with the opcode to define the exact operation.

rs1 (5 bits): The source register operand.

imm (12 bits): The immediate value (constant).

### Structure
Here's a breakdown of the bit fields:
```sh
| imm[11:0]     | rs1     | funct3 | rd      | opcode  |
| 12 bits       | 5 bits  | 3 bits | 5 bits  | 7 bits  |

```

### Example (ADDI Instruction)
For instance, an ADDI (add immediate) instruction in RISC-V might look like this:
#### Instruction Breakdown
opcode (7 bits): 0010011 – Identifies this as an I-type immediate instruction.

rd (5 bits): 00101 – The destination register x5 (in binary, register 5 is 00101).

funct3 (3 bits): 000 – Indicates add immediate operation.

rs1 (5 bits): 00001 – The source register x1 (in binary, register 1 is 00001).

imm (12 bits): 000000000010 – The immediate value 10 (in binary, 10 is 000000000010).
#### Detailed Bit Representation
```sh
| 31:20 (imm[11:0]) | 19:15 (rs1) | 14:12 (funct3) | 11:7 (rd) | 6:0 (opcode) |
| 000000000010      | 00001       | 000            | 00101    | 0010011      |
// hex representation
0x00208113
```
</details>

<details><summary><b> S-Type Instruction</b>
The S-type (Store) instruction format in the RISC-V architecture is used for store operations. These instructions move data from a register to memory, using an immediate value as an offset to calculate the address.</summary>
  
## S-type Instruction Format
The S-type format consists of six fields:

opcode (7 bits): Specifies the operation.

imm[4:0] (5 bits): Immediate value (least significant 5 bits).

funct3 (3 bits): Specifies the exact operation.

rs1 (5 bits): Source register (base address).

rs2 (5 bits): Source register (value to be stored).

imm[11:5] (7 bits): Immediate value (most significant 7 bits).

### Structure
Here's the bit layout for an S-type instruction:
```sh
| imm[11:5] | rs2   | rs1   | funct3 | imm[4:0] | opcode  |
| 7 bits    | 5 bits| 5 bits| 3 bits | 5 bits   | 7 bits  |
```

### Example (SW Instruction)
the sw (store word) instruction in RISC-V
sw x5, 10(x1)
This command stores the value from register x5 into the memory address calculated by adding 10 (the immediate) to the base address in x1.

#### Breaking Down the Example:

opcode (7 bits): 0100011 – Indicates an S-type store instruction.

imm[4:0] (5 bits): 01010 – The least significant 5 bits of the immediate value 10.

funct3 (3 bits): 010 – Specifies the store word operation.

rs1 (5 bits): 00001 – The base address register x1.

rs2 (5 bits): 00101 – The source register x5.

imm[11:5] (7 bits): 0000000 – The most significant 7 bits of the immediate value 10.

#### Detailed Bit Representation
```sh
| 31:25 (imm[11:5]) | 24:20 (rs2) | 19:15 (rs1) | 14:12 (funct3) | 11:7 (imm[4:0]) | 6:0 (opcode) |
| 0000000           | 00101       | 00001       | 010            | 01010           | 0100011      |
// hex representation
0x0050a023
```
</details>

<details><summary><b>B-Type Instructions:</b> B-type (Branch) instructions in the RISC-V architecture are used for conditional branching. These instructions compare two registers and, based on the result, adjust the program counter to branch to a different part of the program.</summary>

## B-type Instruction Format
The B-type format consists of six key fields:

opcode (7 bits): Specifies the operation.

imm[12|10:5] (7 bits): Immediate value (most and middle significant bits).

rs1 (5 bits): First source register.

rs2 (5 bits): Second source register.

funct3 (3 bits): Specifies the exact branch condition.
   
imm[4:1|11] (5 bits): Immediate value (least significant and sign bit).

#### Structure
```sh
| imm[12] | imm[10:5] | rs2    | rs1    | funct3 | imm[4:1] | imm[11] | opcode  |
|---------|-----------|--------|--------|--------|----------|---------|---------|
| 1 bit   | 6 bits    | 5 bits | 5 bits | 3 bits | 4 bits   | 1 bit   | 7 bits  |

```

#### Example (BEQ Instruction)
Let's consider the beq (branch if equal) instruction:
##### beq x1, x2, label
This instructs the program to branch to a specific label if the values in registers x1 and x2 are equal.
#### Breaking Down the Example:
 opcode (7 bits): 1100011 – Indicates a B-type branch instruction.

imm[12] (1 bit): Most significant bit of the immediate offset.

imm[10:5] (6 bits): Next part of the immediate.

funct3 (3 bits): 000 – Specifies the branch if equal condition.

rs1 (5 bits): 00001 – The first source register x1.

rs2 (5 bits): 00010 – The second source register x2.

imm[4:1] (4 bits): Least significant bits of the immediate.

imm[11] (1 bit): Sign bit of the immediate.

##### Detailed Bit Representation
```sh
| 31 (imm[12]) | 30:25 (imm[10:5])    | 24:20 (rs2) | 19:15 (rs1) | 14:12 (funct3) | 11:8 (imm[4:1]) | 7 (imm[11]) | 6:0 (opcode) |
| 0            | 000000               | 00010       | 00001       | 000            | 0010            | 0           | 1100011      |
//hex representation
0x00410263

```

</details>
<details><summary><b> U-Type Instruction:</b>The U-type (Upper immediate) format is one of the instruction formats in the RISC-V architecture.</summary>

  ## Important U-Type Instructions in RISC-V:
  ##### 1. LUI (Load Upper Immediate):
  This instruction loads the 20-bit immediate value given in the instruction into the top 20 bits of a register. The lower 12 bits 
  are set to zero.
   
##### Format:

```sh
31-12	                | 11-7	                    | 6-0
20-bit immediate value|	rd (destination register)	| opcode
```
Opcode: 0010111

rd: The destination register to which the result of the addition will be stored.
##### example LUI x5, 0x12345
This instruction will load the immediate value 0x12345 into register x5. The lower 12 bits are set to zero, so effectively 0x12345 << 12 is loaded into x5.
```sh
31-12	                       | 11-7	                      | 6-0
20-bit immediate value       |	rd (destination register)	| opcode
000 0001 0010 0011 0100 0101 | 00101                      | 0110111JAL (Jump and Link) Instruction
```

##### Instruction Breakdown:

Opcode: The LUI instruction has an opcode of 0110111 (binary) which is 0x37 (hexadecimal).

Immediate Value: The immediate value provided in the instruction is 0x12345.

Destination Register: The register to be loaded with the immediate value here is x5

##### 2.AUIPC (Add Upper Immediate to PC): 
This adds the 20-bit immediate value to the program counter and places the result in a register. Essentially, this helps in generating PC-relative addresses.
##### Format:
```sh
31-12                   |	11-7	                      | 6-0
20-bit immediate value	| rd (destination register)	  |   opcode
```
Opcode: 0010111

rd: The destination register to which the result of the addition will be stored.

##### Example: AUIPC x5, 0x12345
This instruction adds the immediate value 0x12345 << 12 to the current value of the PC (Program Counter) and stores the result in register x5. This is useful for generating PC-relative addresses.

</details>
<details>
<summary><b> J-Type Instruction:</b> The J-type (Jump) format is another instruction format in the RISC-V architecture, and it’s used primarily for jump instructions that enable control flow changes.</summary>

  ## JAL (Jump and Link) Instruction
  ### Format:
 ```sh
  31	  | 30-21     |	20      |	19-12       |	11-7 |	6-0
imm[20] |	imm[10:1]	|imm[11]	| imm[19:12]  |	rd	 |  opcode
```
Opcode: 1101111

rd: The destination register where the return address will be stored.

imm: Immediate value representing the offset to jump to, with the final address being the PC plus this offset.
##### Example JAL x1, 2048
This instruction makes the processor jump to the PC plus the offset 2048 bytes and stores the return address (i.e., the address of the next instruction) in the register x1.
 ```sh
  31	     | 30-21      |	20       |	19-12        |	11-7  |	6-0
imm[20]    |	imm[10:1]	| imm[11]	 | imm[19:12]    |	rd	  |  opcode
0000000000 | 0          | 00000001 | 0             | 00001  |      1101111

```
Opcode (7 bits): 1101111

Destination Register (5 bits): 00001

Immediate/Target Address (20 bits): 2048 in binary is 00000001000000000000.
##### Breaking it Down:

Offset Calculation: The immediate value in J-type instructions is spread across multiple fields in the instruction encoding.

imm[20] bit is at position 31.

imm[10:1] bits are at positions 30-21.

imm[11] bit is at position 20.

imm[19:12] bits are at positions 19-12.

These fields are extracted and combined to form a 21-bit signed immediate value, which is then shifted left by one bit to align with even byte boundaries (since instruction addresses are word-aligned).

</details>

#  32-bit instruction code for 15 unique RISC-V instructions. 

![32 bit](https://github.com/Varshitha-H-N/vsd-riscv/blob/f6ce196b0b68c0194868fb67536b1d6664ce5503/task3/main.png)


</details>
---------------------------------------------------------------------------------------------------------------------------------------------------------------------
<details><summary><b>
Task 4:</b>Perform a functional simulation of the given RISC-V Core Verilog netlist and 
testbench. </summary>
  Functional simulation of RISC-V cores involves verifying that the core behaves correctly according to its design specifications. This process includes testing all possible instructions, ensuring compliance with the RISC-V instruction set architecture (ISA), and checking for any security vulnerabilities or malicious logic

  # About iverilog and gtkwave
1. Icarus Verilog is an implementation of the Verilog hardware description language.
2. GTKWave is a fully featured GTK+ v1. 2 based wave viewer for Unix and Win32 which reads Ver Structural Verilog Compiler generated AET files as well as standard Verilog VCD/EVCD files and allows their viewing.

**Step 1: installation of iverilog and gtkwave**
   using the below commands in ubuntu
   ```sh
   $   sudo apt get update
   $   sudo apt get install iverilog gtkwave
   ```
   
  **Step 2: clone the repository and download the netlist files for simulation by entering the following commands in terminal.**
  ```sh
   $ git clone https://github.com/vinayrayapati/iiitb_rv32i
   $ cd iiitb_rv32i
   $ gedit iiitb_rv32i.v
   $ gedit iiitb_rv32i_tb.v
   ```
 **Step 3: To simulate and run the verilog code , enter the following commands in your terminal.**
  ```sh
 $ iverilog -o iiitb_rv32i iiitb_rv32i.v iiitb_rv32i_tb.v
 $ ./iiitb_rv32i
   ```
**Step 4:To see the output waveform in gtkwave, enter the following commands in your terminal.**
 ```sh
 $ gtkwave iiitb_rv32i.vcd
   ```




## Analysis of output waveforms
The waveform includes the following key signals:

clk: The clock signal driving the design.

NPC [31:0]: The next program counter value.

WB_OUT [31:0]: The write-back output signal.


**1. add r6,r1,r2**

![ADD](https://github.com/Varshitha-H-N/vsd-riscv/blob/d682b9a8e5647daee93bdeba2f7ac1ee71c2e154/task4/Screenshot%20(374).png)

**2. sub r7,r1,r2**

![SUBTRACT](https://github.com/Varshitha-H-N/vsd-riscv/blob/d682b9a8e5647daee93bdeba2f7ac1ee71c2e154/task4/Screenshot%20(375).png) 

**3. and r8,r1,r3**

![AND](https://github.com/Varshitha-H-N/vsd-riscv/blob/d682b9a8e5647daee93bdeba2f7ac1ee71c2e154/task4/Screenshot%20(376).png)


**4. or r9,r2,r5**
 
![OR](https://github.com/Varshitha-H-N/vsd-riscv/blob/d682b9a8e5647daee93bdeba2f7ac1ee71c2e154/task4/Screenshot%20(377).png)

**5. xor r10,r1,r4**

![EXOR](https://github.com/Varshitha-H-N/vsd-riscv/blob/d682b9a8e5647daee93bdeba2f7ac1ee71c2e154/task4/Screenshot%20(378).png)

**6. slt r11,r2,r4**

![SLT](https://github.com/Varshitha-H-N/vsd-riscv/blob/d682b9a8e5647daee93bdeba2f7ac1ee71c2e154/task4/Screenshot%20(379).png)
 
**7. addi r12,r4,5**

![ADDI](https://github.com/Varshitha-H-N/vsd-riscv/blob/d682b9a8e5647daee93bdeba2f7ac1ee71c2e154/task4/Screenshot%20(380).png)

**8. sw r3,r1,2**

![SW](https://github.com/Varshitha-H-N/vsd-riscv/blob/d682b9a8e5647daee93bdeba2f7ac1ee71c2e154/task4/Screenshot%20(381).png)

**10.  beq r0,r0,15**

 ![BEQ](https://github.com/Varshitha-H-N/vsd-riscv/blob/d682b9a8e5647daee93bdeba2f7ac1ee71c2e154/task4/Screenshot%20(382).png)

**11.  add r14,r2,r2**

 ![ADD](https://github.com/Varshitha-H-N/vsd-riscv/blob/d682b9a8e5647daee93bdeba2f7ac1ee71c2e154/task4/Screenshot%20(384).png)
 
</details>
</details>

 --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
 
<details><summary><b>
   
Task 5:</b>Implementation of Binary to Gray code converter using VSDSquadron Mini Board. </summary>


## Project Overview
 Binary to Gray code converter 
 This project demonstrates the implementation of a binary to Gray code converter using the VSDSquadron Mini. The goal is to take a 3-bit binary input from the user and convert it into a 3-bit Gray code output. This conversion is crucial in digital systems for minimizing errors in signal processing and data transmission. The project utilizes the VSDSquadron Mini’s GPIO capabilities and programming flexibility, showcasing an application of RISC-V processors in digital logic design.

## Pin Configuration
| **Component** | **Pin** |
|----------------|---------|
| **VSD SQUADRON BOARD** | **Led** | **Button**|
| **Led 1** | **Pin0(PD0)** |
| **Led 2** | **Pin2(PD2)** |
| **Led 3** | **Pin3(PD3)** |
| **Button 1** | **Pin4(PD4)** |
| **Button 2** | **Pin5(PD5)** |
| **Button 3** | **Pin6(PD6)** |


## Truth Table

![TRUTHTABLE](https://github.com/Varshitha-H-N/vsd-riscv/blob/50374b1fc83881e673b9b596e96504f1b39e4383/task5/image018.png)

## Circuit Diagram

![CIRCUIT](https://github.com/Varshitha-H-N/vsd-riscv/blob/50374b1fc83881e673b9b596e96504f1b39e4383/task5/Screenshot%20(388).png)

## Working
The converter operates by reading a 3-bit binary input through buttons, applying the binary to Gray code conversion formula, and displaying the resulting Gray code on LEDs. The conversion process involves exclusive OR operations to calculate each bit of the Gray code based on the input binary bits. This project provides a practical example of digital logic design using a RISC-V based development board.

## Code
The code includes functions for GPIO configuration, the XOR logic for binary to Gray conversion, and the main loop for continuous operation. The project demonstrates handling input from GPIO pins, processing the data according to digital logic principles, and outputting the result through GPIO pins.


</details>
</details>
--------------------------------------------------------------------------------------------------------------------------------------------
<details><summary><b>
Task 6:</b>Project Implementation</summary>

## Steps to implement
1. Hardware Setup:
  - VSDSquadron Mini RISC-V Board
   
  - Button
   
   -LEDs 
   
  - Breadboard and jumper wires (for connections)
   
  - Power supply (USB or external source)

2.Compilation and Upload:

-Compile the code

-Upload to VSDSquadron Mini Board

3.Testing and Debugging:

-Input testing

-Debugging

## Expected Output


The LEDs will turn on accordingly based on the button pressed and gray coded will be output.


## Code Implementation
```sh
#include <ch32v00x.h>
#include <debug.h>
int xor(int bit1, int bit2)
{ int xor = bit1 ^ bit2;
return xor;
}

void GPIO_Config(void)
{ GPIO_InitTypeDef GPIO_InitStructure = {0}; //structure variable used for the GPIO configuration
RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOD, ENABLE); // to Enable the clock for Port D
GPIO_InitStructure.GPIO_Pin = GPIO_Pin_4 | GPIO_Pin_5 | GPIO_Pin_6 ; // Defines which Pin to configure
GPIO_InitStructure.GPIO_Mode = GPIO_Mode_IPU; // Defines Input Type
GPIO_Init(GPIOD, &GPIO_InitStructure);
GPIO_InitStructure.GPIO_Pin = GPIO_Pin_0 | GPIO_Pin_2 | GPIO_Pin_3 ; // Defines which Pin to configure
GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP; // Defines Output Type
GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz; // Defines speed
GPIO_Init(GPIOD, &GPIO_InitStructure);
}
int main(void)
{ uint8_t b0, b1, b2, g0 , g1, g2 = 0;
NVIC_PriorityGroupConfig(NVIC_PriorityGroup_2);
SystemCoreClockUpdate();
Delay_Init();
GPIO_Config();
while(1)
{ b0 = GPIO_ReadInputDataBit(GPIOD, GPIO_Pin_4);
b1 = GPIO_ReadInputDataBit(GPIOD, GPIO_Pin_5);
b2 = GPIO_ReadInputDataBit(GPIOD, GPIO_Pin_6);
g0 = xor(0, b0);
g1 = xor(b0, b1);
g2 = xor(b1, b2);
if(g0 == 0)
{ GPIO_WriteBit(GPIOD, GPIO_Pin_0, RESET); }
else
{ GPIO_WriteBit(GPIOD, GPIO_Pin_0, SET); }
if(g1 == 0)
{ GPIO_WriteBit(GPIOD, GPIO_Pin_2, RESET); }
else
{ GPIO_WriteBit(GPIOD, GPIO_Pin_2, SET); }
if(g2 == 0)
{ GPIO_WriteBit(GPIOD, GPIO_Pin_3, RESET); }
else
{ GPIO_WriteBit(GPIOD, GPIO_Pin_3, SET); }
}
}
 
```

## Applications
-It is used in analog to digital converters.

-In digital communication for correction of an error.

-It reduces errors while changing the signals from analog to digital.

-Mathematical puzzles.

-Minimization of a Boolean circuit.

-It is used for communication between two clock domains.

-Genetic algorithms.

## Demonstration video

(https://drive.google.com/file/d/15MvrX2tMbzq0z_6PSRQCnOxmc9tYpWsI/view?usp=drive_link)


## Conclusion
This implementation demonstrates the use of the VSDSquadron Mini board to design a basic digital circuit. The Binary to Gray Code is implemented successfully using the RISC-V Processors VSDSquadron Mini
and the video for the same is attached with this report. This project reinforces the fundamental concepts of digital design.Overall, this project was a valuable learning experience.

</details>
</details>
 
