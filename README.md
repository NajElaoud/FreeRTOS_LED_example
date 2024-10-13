## STM32 RTOS Project
This project implements a simple real-time operating system (RTOS) on an STM32 microcontroller using FreeRTOS. It demonstrates task management, semaphore handling, GPIO manipulation, and scheduling. The system manages three tasks that toggle LEDs, perform synchronized actions, and demonstrate basic RTOS functionality.

#Features:
 + Task Management: Three tasks (TASK_1, TASK_2, TASK_3) are created, each toggling an LED at different rates.
 + Semaphore Usage: A semaphore is used for task synchronization, demonstrating how tasks can share resources.
 + Task Suspension and Resumption: Tasks are suspended and resumed in a round-robin style, ensuring efficient time-sharing.
 + GPIO Control: LED toggling is achieved using the STM32 GPIO pins, simulating real-time control.
 + Debugging Outputs: Print statements are included for debugging and tracking task execution flow.

# Project Structure
```
Copy code
.
├── Core
│   ├── Inc
│   │   └── main.h         # Header file with main definitions
│   └── Src
│       └── main.c         # Main program code
├── Drivers
│   └── CMSIS              # CMSIS and HAL library files
└── README.md              # Project documentation
```

# How it Works:
 1. Task Creation: In the main.c file, three tasks are created using FreeRTOS APIs. Each task toggles a specific LED and then suspends itself, allowing the next task to run.
 2. Task Flow:
   - TASK_1: Toggles LED 1, suspends itself, and resumes TASK_2.
   - TASK_2: Toggles LED 2, suspends itself, and resumes TASK_3.
   - TASK_3: Toggles LED 3, suspends itself, and resumes TASK_1.
 3. Semaphore Usage: A binary semaphore is used to manage critical sections, ensuring safe access to shared resources.
 4. Debugging Output: Messages like "Task-1 running" are printed to track task execution flow, helping with debugging.

# Prerequisites :
 + STM32CubeMX and STM32CubeIDE for development
 + FreeRTOS for task management
 + STM32 development board (tested on STM32F4xx series)

# Setup:
 1. Clone the repository:
```
git clone https://github.com/NajElaoud/Music-Player-wav.git
```
 2. Open the project in STM32CubeIDE.
 3. Build the project and upload it to the STM32 board.

# Usage:
 + When the system starts, the tasks run in a round-robin fashion.
 + LEDs will toggle based on the task execution.
 + Debugging information will be output via the printf function to monitor the task flow.
