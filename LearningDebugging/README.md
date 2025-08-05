# Learning Debugging 🪲

In this project, we will practice using the debugging features of STM32CubeIDE.

First, we create our stm32 project and write the following simple code in main.c:

        int counter = 0;

         while (1) {
            counter++;
	        HAL_Delay(1000);
        }

To start debugging, right-click on the project and select Debug As > STM32 C/C++ Application .    

Important note: You must have your board connected to you computer via USB so that STM32CubeIDE can recognize the ST-LINK debugger.

Once you click the debugg icon, the debugg process begins. STM32CubeIDE will switch to the Debug perspective, which provides specialized windows and views
for debugging operations. The next step is to set a breakpoint in your code. You can do this by double-clicking in the gray margin area (line number area) next
to the line where you want to place the breakpoint. Alternativaly, you can right-click in the margin and select "Toggle Breakpoint".

Finally, resume your program by pressing F8 or clicking the resume button. Now you can use the debugging controls:

 -Step Over (F6): Execute the current line and move to the next one.
 
 -Step Into (f5): Enter into function calls.
 
 -Step Return : Exit the current function.
 
 -You can also monitor variables and registers in the appropriate debugging windows, such as the Variables view, Expressions view, or Live Expressions view.
