# Learning interrupts using the user button of Nucleo ⏹️

In this project we are going to use interrupts to change the state of the LED on Nucleo, instead of just continuously reading the input from the pin that is connected to the user button.

In the following section we describe step by step the process that we followed.

1️⃣ STEP : Configure GPIO for Interrupt
  
In Pinout & Configuration tab click on PC13 and select GPIO_EXT13 (External Interrupt). Then go to System Core > GPIO > PC13 and set GPIO mode to "External Interrupt Mode with Falling edge trigger detection", set User Label  to "Button" and
leave GPIO as Pull-up.

2️⃣ STEP : Enable NVIC Interrupt

First go to System Core > NVIC and check "EXTI Interrupts" to enable the interrupt. Then set priority as needed (default 0 is fine).

> **Note:** The NVIC (Nested Vector Interrupt Controller) is a hardware block that manages all the interrupts and exceptions in an STM32 MCU

3️⃣ STEP : Generate code and add ISR

After we generate the code, we should add the interrupt service routine:

    /* USER CODE BEGIN 4 */
    void HAL_GPIO_EXTI_Callback(uint16_t GPIO_Pin)
    {
        if(GPIO_Pin == GPIO_PIN_13) 
        {
            // Toggle LED when button is pressed
            HAL_GPIO_TogglePin(GPIOA, GPIO_PIN_5);
        }
    }
    /* USER CODE END 4 */
