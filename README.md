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






