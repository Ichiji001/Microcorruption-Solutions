Microcorruption-Solutions
=========================

Hollywood
-------------------------

Initially when faced with this program it may seem daunting, but the solution is actually surprisingly simple.

Step 1: <b><br>
Notice that the debugger does not show any sensible code. Copy and paste the contents of the entire memory map into a file and write a program to parse it in such a way that only program code remains.

Step 2:<b><br>
Copy and paste the program code into Microcorruption's assembler and generate code. The program will need to be copied and pasted in sections due to character limits of the assembler. Paste this generated code into your favorite code viewer.

Step 3:<b><br>
Organize this code by searching for key instructions such has br, ret, and call.

Step 4:<b><br>
Using the debugger step through the code, while keeping an eye on your pasted code to find out what is being executed. Notice that there are a bunch of JMP #0x4 instructions through the code. These instructions are only here to confuse us. These jumps trick the assembler. It turns a 4 byte instruction into a 6 byte instruction. 

Step 5:<b><br>
Go throughout the pasted code and alter the code to it's proper state by removing all the 'JMP 0x4's, and use the assembler to reveal the true code.

Step 6:<b><br>
Now that we have the 'actual' program, we should network the flow of the program. The way I did this was by stepping through the code and organizing my pasted functions in execution order. The code is fairly short, and you'll soon find yourself going in circles.

Step 7:<b><br>
Observe the program with different length inputs and you'll notice a vast difference in execution time

Step 8:<b><br>
The details of the code don't matter so much, but notice that a new function is generated every single pass of the loop. In each of these functions there is an instruction of importance. Load the program with empty input and record each instruction generated. It totals about 38 lines long.

Step 9:<b><br>
The execution time of the program would drastically change given different inputs, so this time give an input of 4 bytes or so and observe where this newly found 38 lined long program loops.

Step 10:<b><br>
After examining the this newly found 38 lined function, you'll notice 2 lines of interest... they compare R4 and R6 to specific values. Take advantage of the debugger and you'll find out these are the conditions to unlock the door!!!!

Step 11:<b><br>
R4 and R6 are only affected within THAT 38 lined function, and the equation that controls those values are in plain sight... We know what the result of the equation needs to be, and we know both R6 and R4 initial values, so write a C program to generate a password... The only assumption we need to make is the password length. Given the equation at hand, it would be reasonable to assume the password is short. The simplest way of handing this is to have the C program generate all possible passwords of length 1 byte, 2 bytes, 3 bytes... etc.

Step 12:<b><br>
Presto!
Input your generated password!!!!
