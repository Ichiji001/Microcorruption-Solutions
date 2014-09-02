Microcorruption-Solutions
==========================

Chernobyl
--------------------------

This program uses hash maps to store password information and I found it quite challenging. But nonetheless, luck prevailed. \*cough\* (skill)

Step 1: <b><br>
This program asks the user to input a username and password in a single line, in a certain format. That format is: 'access [your name] [pin]'. It's pretty strange for a user login to require a command field, and perhaps there are more commands than access.

Step 2: <b><br>
And... Yes there are other commands, just by looking in the run function there are two compares that are done, one for an 'a' and one for an 'n'. 

Step 3: <b><br>
Try making some user accounts and observe where they are stored, and how more space is added as necessary. After trying a variety of inputs via a generator, you'll get an error where some function somewhere is returning to an invalid address. This is exactly what we're looking for.

Step 4: <b><br>
Using the same input that gave the return error, trace the code and see which function is overwriting the stack. In my case, the function I found was the 'free' function. 

Step 5: <b><br>
At this point the goal is to control where the function returns, so we must note the address on the stack, in the case of this solution, the return address we overwrite is the 'free's return value, but the function that called free, 'rehash'

Step 6: <b><br>








