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









 


















