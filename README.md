# VSDSquadron Research Internship
The program is based on the RISC-V architecture and uses open-source tools to teach people about VLSI chip design and RISC-V. The instructor for this internship is Kunal Ghosh Sir.                                                                  

# Basic Details
**Name:** Varshitha H N              
**College:** Vidyavardhaka College of Engineering                                                                                                                                                     
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

![32 bit](https://github.com/Varshitha-H-N/vsd-riscv/blob/16e9b532d77eb1b6774f4d5a8f19373cfa95e65d/task3/main.png)


</details>

