# STM32-FreeRTOS-UART-Mutex

## Project Overview

This project demonstrates multitasking, UART communication, and mutex synchronization using FreeRTOS on an STM32 microcontroller.

Three RTOS tasks run concurrently and print messages to a serial terminal through a shared UART peripheral. Since all tasks use the same UART resource, a mutex is implemented to ensure synchronized and corruption-free communication.



# Features

* FreeRTOS multitasking
* CMSIS-RTOS V2 API
* UART serial communication
* Mutex synchronization
* Shared resource protection
* Round-robin task scheduling
* STM32CubeMX generated RTOS framework





# Hardware Used

* STM32 Nucleo Board
* ST-Link Virtual COM Port





# Software Used

* STM32CubeIDE
* STM32CubeMX
* FreeRTOS
* TeraTerm Serial Terminal





# RTOS Tasks

|Task|Delay|Function|
|-|-|-|
|Task1|500 ms|UART message transmission|
|Task2|1000 ms|UART message transmission|
|Task3|1500 ms|UART message transmission|



# UART Configuration

|Parameter|Value|
|-|-|
|UART Peripheral|USART2|
|Baud Rate|115200|
|Data Bits|8|
|Stop Bits|1|
|Parity|None|



# Why Mutex Is Needed

All three tasks access the same UART peripheral.

Without synchronization, multiple tasks may try to transmit simultaneously, causing corrupted serial output. To solve this problem, a mutex is used.

The mutex allows only one task to access UART at a time.



# Mutex Workflow

1. Task requests UART access
2. Mutex locks UART resource
3. UART transmission occurs
4. Mutex releases UART
5. Another task can now use UART



# Important RTOS Concepts Demonstrated

|Concept|Description|
|-|-|
|Multitasking|Multiple tasks execute concurrently|
|Scheduler|FreeRTOS manages task execution|
|Mutex|Prevents simultaneous UART access|
|Shared Resource|UART used by all tasks|
|Synchronization|Tasks coordinated using mutex|
|Blocking Delay|osDelay() allows task switching|



# Serial Output

!\[UART Output](Images/output.png)



# Learning Outcome

This project helps understand:

* RTOS task management
* Context switching
* Shared resource protection
* Mutex synchronization
* UART communication in RTOS
* CMSIS-RTOS V2 APIs

