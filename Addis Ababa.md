Microcorruption-Solutions
==========================

Addis Ababa
--------------------------

Quite fun, I liked this one.

Step 1: <b><br>
To solve this problem, we must understand what the program is checking for to unlock the door. By examining the code we can tell it does a single check to unlock the door. That check specificly is, "is the value at the stack pointer 0?"

Step 2: <b><br>
That said, the next step is to determine where in the code we can change stack values. To do this, we need to notice the line the line of code that sets a particular value on the stack to 0. This just happens to be the same value that is the unlock condition.

Step 3: <b><br>
From that, I determined the printf function merrited more investigation. Within the printf function, they do standard printf things, such as %d, %c, %x... etc. 

Step 4: <b><br>
By pure code examination, it can be determined that %n altars the stack. 

Step 5: <b><br>
Thus by giving inputs that use %n and the memory location of the stack that has our unlock door check value we change that 0 to some other number.

Step 6: <b><br>
DONE!
