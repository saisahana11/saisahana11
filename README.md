# VSDSquadron-Mini-Internship
Internship at VSD on RISC-V and VLSI using VSDSquadron Mini Board.

## About The Board
* 32-bit RISC-V Core: The heart of the VSDQuadron development board is a powerful 32-bit RISC-V processor.This open-source instruction set architecture (ISA) is known for its flexibility and scalability, making it an excellent choice for educational and development purposes.
* Multiple Clock Options: The board provides various clock configurations, allowing participants to explore different operational frequencies and power modes. This feature is crucial for optimizing performance and energy consumption in embedded applications.
15 GPIO Pins: The board is equipped with 15 General Purpose Input/Output (GPIO) pins.
* These versatile pins can be programmed for various functions, including digital input, digital output, and more. They are essential for interfacing with external sensors, actuators, and other peripherals.
* Software Support: Extensive libraries and frameworks make programming accessible in multiple languages, including C, C++, and Python.

# Task 1 Using a RISC-V simulator, write a C program to count the sum of all numbers from 1 to n.
* Install the RISC-V toolchain using VDI
* Use the Terminal Windows in UBUNTU
* C code for sum of numbers from 1 to N
* Assembly language

1.Virtual box Installed

![Screenshot 2024-07-03 154019](https://github.com/saisahana11/saisahana11/assets/175141569/296daf12-e6c9-4389-99e9-f6c26669094c)


2.Ubuntu installed

![Screenshot 2024-07-09 212512](https://github.com/saisahana11/saisahana11/assets/175141569/b79bb0a2-2600-4a32-951a-4b74f7fa2aab)

3.C code to execute The Sum of Numbers 1 to N
 * Leafpad id installed using sudo snap install leafpad
 * Create file using leafpad sum1ton.c &
 * Here you fnd the leafpad to code write the code

![Screenshot 2024-07-09 212241](https://github.com/saisahana11/saisahana11/assets/175141569/cfcc33c8-e77e-43a8-8e61-30b18e30f512)


4.Output for the C Program
* Compile the program using gcc sum1ton.c then ls -ltr
* Execute the program using ./a.out
* The sum for 1 to 5 is 15 which is also verified using calculator

![Screenshot 2024-07-09 212717](https://github.com/saisahana11/saisahana11/assets/175141569/592db46a-5f79-46d2-bb38-794ec7462efa)

5.C program to RISC-V instruction Set
* Command 1 riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
* Switch tab command 2 riscv64-unknown-elf-objdump -d sum1ton.o| less and access the main part using main function /main
* To calculate the different execution with Ofast instead of O1 as riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c

![Screenshot 2024-07-09 212700](https://github.com/saisahana11/saisahana11/assets/175141569/e32746d4-6aad-48fe-b74e-231073f57833)

6.Search the main() and calculate the RISC-V instruction

![Screenshot 2024-07-09 212643](https://github.com/saisahana11/saisahana11/assets/175141569/ef51fcb9-96b0-45ef-954a-cf219c7a4eca)

## Conclusion
By following these steps, you will have a virtual environment set up with the RISC-V toolchain ready for development.
This setup allows you to compile and test RISC-V programs, providing a robust environment for RISC-V development projects.

# TASK 2
# PROJECT 1 - Ticket Terminal Designer: Developing an Automated Parking Ticket Vending Machine
To develop an Automated Parking Ticket Vending Machine using the RISC-V toolchain, we will create a simple program that simulates issuing parking tickets. The program will prompt the user for the number of hours they intend to park, calculate the total cost based on a predefined rate, and print a ticket with the details.
## 1. C PROGRAM CODE
    #include <stdio.h>
    #define RATE_PER_HOUR 5

    void print_ticket(int hours, int cost) {
    printf("\n----------------------------\n");
    printf("    Parking Ticket\n");
    printf("----------------------------\n");
    printf("Hours Parked: %d\n", hours);
    printf("Total Cost: $%d\n", cost);
    printf("----------------------------\n");
    printf("Thank you for using our service!\n");
    }
    int main() {
    int hours;
    int total_cost;

    // Prompt the user for the number of hours they intend to park
    printf("Welcome to the Automated Parking Ticket Vending Machine\n");
    printf("Please enter the number of hours you intend to park: ");
    scanf("%d", &hours);

    // Calculate the total cost
    total_cost = hours * RATE_PER_HOUR;

    // Print the ticket
    print_ticket(hours, total_cost);

    return 0;
}
## Steps to Compile and Run the Program
 1.Create the Source File: Save the above code in a file named ticketterminaldesigner.c
 
 2.Compile the Program: Use the RISC-V toolchain to compile the program. Make sure you have the RISC-V toolchain installed and properly set up.
 
          riscv64-unknown-elf-gcc -o ticketterminaldesigner ticketterminaldesigner.c
          
3.Run the Program To run the program, you need an emulator such as Spike or QEMU. Assuming you have Spike installed, you can run the program as follows: 

          spike pk parking_ticket_machine
This will prompt you to enter the number of hours, calculate the total cost, and print the parking ticket.

#### Behavior: Manages the flow of the program and user interactions

    int main() {
     int hours;
     int total_cost;

     // Prompt the user for the number of hours they intend to park
     printf("Welcome to the Automated Parking Ticket Vending Machine\n");
     printf("Please enter the number of hours you intend to park: ");
     scanf("%d", &hours);

     // Calculate the total cost
     total_cost = hours * RATE_PER_HOUR;

     // Print the ticket
     print_ticket(hours, total_cost);

     return 0;
    }
This code serves as a foundational example of how an automated ticket vending system can be implemented in C. It can be further extended with additional features such as ticket validation, payment processing, and database integration for a more robust solution.

## EXPLANATION OF THE CODE
 * Header Inclusion: The program includes the
`stdio.h`
   header for input/output operations.

 * Rate Definition: The `RATE_PER_HOUR` is defined as a constant value representing the cost per hour of parking.

 * Ticket Printing Function: The `print_ticket` function takes the number of hours and the total cost as arguments and prints the ticket.

 * Main Function:
    * Prompts the user for the number of hours they intend to park.
    * Calculates the total cost by multiplying the hours by the rate.
    * Calls the `print_ticket` function to print the ticket with the details.

This simple program demonstrates the basics of creating an automated ticket vending machine using the RISC-V toolchain.You can expand this program by adding more features such as handling invalid input, offering different parking rates, or integrating with a real hardware interface for a complete system.
## 2. OUTPUT
 * Compile the program using `gcc ticketterminal.c` and execute the program using `./a.out` command

* Compile the code using the RISC-V GCC compiler with the following command: `riscv64-unknown-elf-gcc -o1 -mabi=lp64 -march=rv64i -o ticketterminal.o ticketterminal.c`
  
![Screenshot 2024-07-10 233845](https://github.com/saisahana11/saisahana11/assets/175141569/3e22dd63-d88f-4da5-bf27-13bb40679a60)

![Screenshot 2024-07-10 234014](https://github.com/saisahana11/saisahana11/assets/175141569/cbd8c34f-5eb7-4963-bca0-896b184da3b2)

* Now, switch tab to function your main function and calculation using this command : `riscv64-unknown-elf-objdump -d ticketterminal.o  |less`

 ![Screenshot 2024-07-10 233939](https://github.com/saisahana11/saisahana11/assets/175141569/8acbf043-2930-4677-a884-878ebe04cc41)

* To access the main function using /main statement

![Screenshot 2024-07-10 234038](https://github.com/saisahana11/saisahana11/assets/175141569/b3676576-1a6a-4d6c-bdd1-d6075509bdc2)

* Calculation `-o1` instruction then to obtain the difference execute the same function using the -Ofast function like given below `riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o ticketterminal.o ticketterminal.c`

![Screenshot 2024-07-10 234057](https://github.com/saisahana11/saisahana11/assets/175141569/1691ecf9-ac38-43fb-bece-65019f7eec79)

# CONCLUSION
This foundational project showcases how RISC-V can be used for practical applications, setting the stage for more complex implementations and integrations with real-world hardware systems. By following these steps, you gain a clear understanding of the development process for embedded systems using the RISC-V architecture.

# TASK 3
## SPIKE simulation and verification with -O1 and -OFast along with running the RISK-V Objdump
To further validate the functionality and performance of the Automated Parking Ticket Vending Machine program, you can use SPIKE for simulation and verification, and also run the RISC-V `objdump` tool to inspect the compiled binary. Additionally, you can compile the program with different optimization levels (`-O1` and `-Ofast`) to observe the impact on performance and code size.
#### Verification with Optimization Levels:

* Verify the program's behavior with two different levels of optimization:
* `-O1`: This optimization level enables basic optimizations that improve performance without significantly increasing compilation time.
* `ofast`: This level enables aggressive optimizations, potentially breaking strict standards compliance for maximum performance.

## Steps to Compile, Simulate, and Verify with SPIKE

  1.Compile with Different Optimization Levels: First, compile the program with the `-O1` optimization level:

`riscv64-unknown-elf-gcc -O1 -o ticketterminaldesigner ticketterminaldesigner.c`

Then, compile the program with the `-Ofast` optimization level:

`riscv64-unknown-elf-gcc -O1 -o ticketterminaldesigner_Ofast ticketterminaldesigner.c`

![Screenshot 2024-07-11 012636](https://github.com/saisahana11/saisahana11/assets/175141569/59a77623-dc82-4a81-8a82-61ca4663a1ef)

I used an AI tool to generate the initial code for the Automated Parking Ticket Vending Machine. Afterward, I compiled the code using the RISC-V toolchain and employed the SPIKE simulator for debugging and verification. By compiling the code with different optimization levels (-O1 and -Ofast) and using riscv64-unknown-elf-objdump to inspect the generated machine code, I ensured the correctness and efficiency of the program.

#### (DEBUG done here) command:

* `riscv64-unknown-elf-objdump -d ticketterminaldesigner |less`

![Screenshot 2024-07-11 012607](https://github.com/saisahana11/saisahana11/assets/175141569/c3d2a59c-a59b-42e7-9f80-a2303237e49f)

![Screenshot 2024-07-11 012708](https://github.com/saisahana11/saisahana11/assets/175141569/acaeed77-06ff-41f7-b3d2-27ca32a1fc5e)

2.Spike simulation:

* Running with spike `spike pk ticketterminaldesigner`

![Screenshot 2024-07-11 012747](https://github.com/saisahana11/saisahana11/assets/175141569/47e6b892-f85f-472d-a803-36a469e3688d)

3.Generating and Inspecting Objdump:

 * To debug the spike we need this command `spike -d pk ticketterminaldesigner`
 * Then, by using the command `until pc 0 100b0`,which is the 1st line command of the main function the program counter runs from the 0 till the code 100b0
 * To find the contents of the code we need to use the command `reg 0 sp` in which we content of the 100b0 th line
 * To find the content in the next line just give `ENTER`
 * Initially the value of the sp is `0X0000003ffffffb40` then the next step the sp values get subtracted with the hexadecimal and we get `0X0000003ffffffb20`
 * Finally, by subtracting the both main function values we get the 3rd output as `0X000000ffffffb20`

![Screenshot 2024-07-11 012817](https://github.com/saisahana11/saisahana11/assets/175141569/e9bfc3a3-5106-4ef7-8b7d-8af83ad8ff31)

![Screenshot 2024-07-11 012837](https://github.com/saisahana11/saisahana11/assets/175141569/0ea50738-90b4-436b-b994-b33eaae2c0fd)

# CONCLUSION

By compiling the Automated Parking Ticket Vending Machine program with different optimization levels, simulating it with SPIKE, and inspecting the generated machine code using objdump, you can gain insights into the performance and efficiency of your code on the RISC-V architecture. This process helps ensure that the program operates correctly and efficiently under different optimization settings, providing a deeper understanding of the compiler's impact on the code.

# TASK 4
## Identify various RISC-V instruction type (R, I, S, B, U, J) and exact 32-bit instruction code in the instruction type format for below RISC-V instructions

ADD r6, r2, r1

SUB r7, r1, r2

AND r8, r1, r3

OR r9, r2, r5

XOR r10, r1, r4

SLT r11, r2, r4

ADDI r12, r4, 5

SW r3, r1, 2

SRL r16, r14, r2

BNE r0, r1, 20

BEQ r0, r0, 15

LW r13, r1, 2

SLL r15, r1, r2

Upload the 32-bit pattern on Github"

#### About RISC-V Instruction Type

RISC-V, is an open standard instruction set architecture (ISA), categorizes its instructions into several types based on their formats and intended operations. These primary RISC-V instruction types are:

#### 1.R-type (Register-type):

   * These instructions operate on registers and typically involve arithmetic or logical operations between two source registers, storing the result in a destination register.
   * Example: add rd, rs1, rs2 (Addition)
     
#### 2.I-type (Immediate-type):

   * These instructions also operate on registers but include an immediate value (constant) as part of the operation. They are used for operations like immediate arithmetic, loads, and conditional branches.
   * Example: addi rd, rs1, imm (Add Immediate)
     
#### 3.S-type (Store-type):

   * These instructions store a value from a register into memory. They involve specifying a base address (in a register) and an offset to calculate the memory address.
   * Example: sw rs2, offset(rs1) (Store Word)
     
#### 4.B-type (Branch-type):

   * These instructions perform conditional branches based on comparisons between two registers. They determine whether to jump to a new address based on the result of the comparison.
   * Example: beq rs1, rs2, offset (Branch if Equal)
     
#### 5.U-type (Upper Immediate-type):

   * These instructions load a large immediate value (shifted left by 12 bits) into a register. They are used to set the upper bits of a register without affecting the lower bits.
   * Example: lui rd, imm (Load Upper Immediate)
     
#### 6.J-type (Jump-type):

   * These instructions perform unconditional jumps to a new address. They are typically used for procedure calls or long jumps within a program.
   * Example: jal rd, offset (Jump and Link)
 Each of these instruction types has a specific format, opcode, and field layout in the instruction encoding, allowing RISC-V processors to efficiently execute a wide range of operations while maintaining 
 simplicity and modularity in the instruction set architecture

![image](https://github.com/saisahana11/saisahana11/assets/175141569/326c63e7-eea2-4489-8139-34385e461273)


# I-Type Instructions (Immediate)
I-Type instructions format: `imm[11:0] | rs1 | funct3 | rd | opcode`

ADDI r12, r3,5

    Funct3: 000
    rs1 (r3): 00011 (binary)
    rd (r12): 01100 (binary)
    Immediate (5): 00000101 (binary)
    Instruction Code: 00000101 00011 01100 000 0010011```

SW r3, r1, 4

    Funct3: 010
    rs1 (r1): 00001 (binary)
    rs2 (r3): 00011 (binary)
    Immediate (4): 000000100 (binary)
    Instruction Code: 000000100 00001 00011 010 0100011```

SRL r16, r11, r2

    Funct7: 0000000
    Funct3: 101
    rs1 (r11): 01011 (binary)
    rs2 (r2): 00010 (binary)
    rd (r16): 10000 (binary)
    Instruction Code: 0000000 00010 01011 101 10000 0110011```

# R-Type Instructions (Register-Register)
R-Type instructions format: `funct7 | rs2 | rs1 | funct3 | rd | opcode`

ADD r1, r2, r3
```
   Funct7: 0000000
   Funct3: 000
   rs1 (r2): 00010 (binary)
   rs2 (r3): 00011 (binary)
   rd (r1): 00001 (binary)
   Instruction Code: 0000000 00011 00010 000 00001 0110011```
```

SUB r3, r1, r2
```
   Funct7: 0100000
   Funct3: 000
   rs1 (r1): 00001 (binary)
   rs2 (r2): 00010 (binary)
   rd (r3): 00011 (binary)
   Instruction Code: 0100000 00010 00001 000 00011 0110011```
```

AND r2, r1, r3
```
   Funct7: 0000000
   Funct3: 111
   rs1 (r1): 00001 (binary)
   rs2 (r3): 00011 (binary)
   rd (r2): 00010 (binary)
   Instruction Code: 0000000 00011 00001 111 00010 0110011```
```
OR r8, r2, r5
```
   Funct7: 0000000
   Funct3: 110
   rs1 (r2): 00010 (binary)
   rs2 (r5): 00101 (binary)
   rd (r8): 01000 (binary)
   Instruction Code: 0000000 00101 00010 110 01000 0110011```
```
XOR r8, r1, r4
```
   Funct7: 0000000
   Funct3: 100
   rs1 (r1): 00001 (binary)
   rs2 (r4): 00100 (binary)
   rd (r8): 01000 (binary)
   Instruction Code: 0000000 00100 00001 100 01000 0110011```
```
SLT r10, r2, r4
```
   Funct7: 0000000
   Funct3: 010
   rs1 (r2): 00010 (binary)
   rs2 (r4): 00100 (binary)
   rd (r10): 01010 (binary)
   Instruction Code: 0000000 00100 00010 010 01010 0110011```
```

# S-Type Instructions (Store)
S-Type instructions format: `imm[11:5] | rs2 | rs1 | funct3 | imm[4:0] | opcode`

SW r3, r1, 4
```
    Funct3: 010
    rs1 (r1): 00001 (binary)
    rs2 (r3): 00011 (binary)
    Immediate (4): 000000100 (binary)
    Instruction Code: 000000100 00001 00011 010 0100011```
```

# B-Type Instructions (Branch)
B-Type instructions format: `imm[12|10:5] | rs2 | rs1 | funct3 | imm[4:1|11] | opcode`

BNE r0, r1, 20
```
   Funct3: 001
   rs1 (r0): 00000 (binary)
   rs2 (r1): 00001 (binary)
   Immediate (20): 0000101000 (binary)
   Instruction Code: 0000101000 00000 00001 001 1100011```
```
BEQ r0, r0, 15
```
    Funct3: 000
    rs1 (r0): 00000 (binary)
    rs2 (r0): 00000 (binary)
    Immediate (15): 0000001111 (binary)
    Instruction Code: 0000001111 00000 00000 000 1100011```
```

## U-Type Instructions (Upper Immediate)
There are none in the provided list

# J-Type Instructions (Jump)

LW r13, r11, 2
```
  Funct3: 010
  rs1 (r11): 01011 (binary)
  rd (r13): 01101 (binary)
  Immediate (2): 00000000010 (binary)
  Instruction Code: 00000000010 01011 01101 010 0000011```
```
SLL r15, r11, r2
```
  Funct7: 0000000
  Funct3: 001
  rs1 (r11): 01011 (binary)
  rs2 (r2): 00010 (binary)
  rd (r15): 01111 (binary)
  Instruction Code: 0000000 00010 01011 001 01111 0110011```
```
## Summary
These instructions and their corresponding formats provide a clear representation of how RISC-V organizes its operations. The exact 32-bit codes ensure that each instruction is properly encoded for execution in a RISC-V processor.


