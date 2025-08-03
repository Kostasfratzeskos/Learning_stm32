# Button_polling 🔘

In this project, we are going to use HAL_GPIO_ReadPin to read the state of the button on our Nucleo board.

First, we configure PC13 as an input using the GPIO configuration tab, since this pin is connected to the user button on the Nucleo board. After making this change, we save the project to generate the code.

When the code has been generated we go again to the part of while loop and write the above code:

       // Read button state (PC13)
	     if (HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_13) == 0)
	     {
	         // Button is pressed (active low)
	         HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, 1);  // Turn LED ON
	     }
	     else
	     {
	         // Button is not pressed
	         HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, 0); // Turn LED OFF
	     }
This code reads continuously from pin13 of port C and switches the LED on or of based on whether the button is pressed.