# ICS3203-CAT2 - Assembly Programming

This repository contains the solutions for the **Assembly Programming** tasks in the **ICS3203** course.

## Overview of Each Program's Purpose

### Task 1: Control Flow and Conditional Logic
This program classifies a number as `POSITIVE`, `NEGATIVE`, or `ZERO` based on user input. It demonstrates the use of conditional and unconditional jumps for control flow in assembly language.

### Task 2: Array Manipulation with Looping and Reversal
This program accepts an array of integers from the user, reverses the array in place using a loop, and then displays the reversed array. It showcases memory manipulation and the use of loops for array manipulation.

### Task 3: Modular Program with Subroutines for Factorial Calculation
This program computes the factorial of a number using a subroutine. It demonstrates the use of recursion and stack management in assembly language, along with modular program design.

### Task 4: Data Monitoring and Control Using Port-Based Simulation
This program simulates a control system that reads a sensor value from an input and performs actions such as turning on a motor or triggering an alarm based on that value. It highlights the use of control flow and conditional logic in assembly for hardware simulation.

## Instructions for Compiling and Running the Code

### Task 1: Control Flow and Conditional Logic
1. Save the code as `task1.asm`.
2. Compile the code using NASM:
   ```bash
   nasm -f elf32 -o task1.o task1.asm
   
3. Link the object file:
```bash
  ld -m elf_i386 -o task1 task1.o
```
4. Run the program:
```bash
  ./task1
```
### Task 2: Array Manipulation with Looping and Reversal
1. Save the code as task2.asm.
2. Compile the code:
```bash
  nasm -f elf32 -o task2.o task2.asm
```

3. Link the object file:
```bash
  ld -m elf_i386 -o task2 task2.o
```
5. Run the program:
```bash
  ./task2
```
### Task 3: Factorial Calculation with Subroutine
1. Save the code as task3.asm.
2. Compile the code:
```bash
  nasm -f elf32 -o task3.o task3.asm
```
3. Link the object file:
```bash
  ld -m elf_i386 -o task3 task3.o
```
4.Run the program:
```bash
  ./task3
```
### Task 4: Data Monitoring and Control Using Port-Based Simulation
1. Save the code as task4.asm.
2. Compile the code:
``` bash
  nasm -f elf32 -o task4.o task4.asm
```
3.Link the object file:
```bash
  ld -m elf_i386 -o task4 task4.o
```
4. Run the program:
```bash
  ./task4
```
## Answer To Last question
The program determines which action to take based on the "sensor" input by using conditional logic and simulated memory manipulation. The sensor value, stored in a designated memory location (`sensor_value`), is read into a register. If the input is in ASCII format (e.g., `'0'` for 0, `'1'` for 1), it is converted to its numerical equivalent by subtracting the ASCII value of `'0'`. The program then compares this value against predefined conditions using the `cmp` instruction. Based on the results, conditional jumps (`je` for "jump if equal") redirect execution to the appropriate code block.

For instance, if the sensor value is `3`, the program jumps to the `trigger_alarm` section, setting the `alarm_status` variable to `1` to indicate the alarm is triggered. If the sensor value is `2`, it jumps to `stop_motor`, updating the `motor_status` variable to `0` to turn the motor off. Similarly, if the sensor value is `1`, the program jumps to `start_motor` and sets `motor_status` to `1` to turn the motor on. If the value is `0` or any unrecognized value, the motor remains off by default.

The program uses memory variables such as `motor_status` and `alarm_status` to simulate hardware port control. These variables act as flags to indicate the current state of the motor and alarm. In a real hardware scenario, this logic could be extended to manipulate I/O ports directly using `IN` and `OUT` instructions. This approach ensures efficient and clear control of the simulated system, demonstrating basic principles of embedded systems programming in assembly.

