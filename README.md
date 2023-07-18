# STM32F103-Interrupt--TIMER
This C code is a main program file targeting a microcontroller, likely an STM32 microcontroller, using the TIM1 (Timer 1) peripheral in interrupt mode to count up a counter variable.

Let's go through the key components of the code:
![How-are-timer-interrupts-caused](https://github.com/ivias2000/STM32F103-Interrupt--TIMER/assets/125237611/24376415-d7fe-42f7-8fc2-48780e4139a8)

Includes:
The code includes various header files representing different libraries used in the project, including "main.h," "tim.h," and "gpio.h." These headers provide access to functions and constants required for the peripherals and libraries used in the application.

Global Variables:

counter: An unsigned 16-bit integer variable used as a counter.
Period Elapsed Callback Function:
The code includes a callback function HAL_TIM_PeriodElapsedCallback, which is called whenever the TIM1 timer overflows and the period is elapsed. Inside this function, the counter variable is incremented.

Main Function:
The main function is the entry point of the program. It initializes the microcontroller's peripherals, specifically TIM1, and then enters an infinite loop.

System Clock Configuration:
The SystemClock_Config function configures the system clock for the microcontroller.
![Screenshot 2023-07-18 114930](https://github.com/ivias2000/STM32F103-Interrupt--TIMER/assets/125237611/cc1f4ed5-fe16-4cf7-b619-d72d16f1b263)

Timer Configuration:
The line HAL_TIM_Base_Start_IT(&htim1); starts the TIM1 timer in interrupt mode. The timer is set up to generate an interrupt when it overflows.

Infinite Loop:
The main loop in the main function remains empty and doesn't perform any additional tasks. The counter is incremented in the interrupt callback function.

The TIM1 timer is configured to generate an interrupt when it overflows, which happens when the counter reaches its maximum value (65535 for a 16-bit timer). When the overflow occurs, the HAL_TIM_PeriodElapsedCallback function is called, and the counter is incremented.

To use this code on GitHub, follow the steps mentioned earlier to create a new repository and upload this C code as the main program file. Additionally, you can include a README.md file in your repository to provide more information about the project and how to use the code.
