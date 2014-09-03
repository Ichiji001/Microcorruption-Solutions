Microcorruption-Solutions
==========================

Lagos
--------------------------

This program will only accept alphanumeric passwords, otherwise the program shuts down.

Step 1: <b><br>
The first step in solving this problem is to first observe the program with different length inputs. You will quickly notice that the password is transfered into program space, and will eventually overwrite code.

Step 2: <b><br>
Next, observe that 'conditional unlock door' is very early in the program memory, so this is the function we will ultimately rewrite.

Step 3: <b><br>
Note the position of the stack when we call 'conditional unlock door' is 2 bytes away from our password input. 

Step 4: <b><br>
This step here is where the work comes into play. We need to determine what instructions are alphanumeric. By trial and error, I determined that pop R4 & R5, and ret were valid alphanumeric instructions. And it just so happens that 'getsn' happens to be at an alphanumeric memory location.

Step 5: <b><br>
R4 and R5 are used by the 'getsn' function for location to store the password and how many bytes are allowed. So we have control over all of this, and by calling 'getsn' we can now ignore the alphanumeric requirement, and for the 2nd round of input, we simply input code that unlocks the door.

Step 6: <b><br>
The fact that the 'getsn' function adds 0x6 to the stack pointer is why we have control of where 'getsn' ultimately returns to, the only requirement is that the return address be alphanumeric since we need to set this return address during the 1st round of the password input.
