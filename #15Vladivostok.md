Microcorruption-Solutions
==========================

Vladivostok
--------------------------

This program has the user enter a username and password to unlock the door

Step 1: <b><br>
The first thing that you might notice is that after running the program and entering your username, that the program moves to a random spot in memory.

Step 2: <b><br>
The next thing to notice is that if long usernames and passwords are entered the debugger may say that there is an invalid return address.

Step 3: <b><br>
From this point we can step through the code until it gets to that invalid return address. We know two pieces of information from this, which input caused the problem, and what length that input needs to be to return to some address that is sensible.

Step 4: <b><br>
Ideally we would return to our own input message, since we'll be inputting code that unlocks the door. But we don't know the location of the stack since the code is moved randomly throughout memory.

Step 5: <b><br>
After hours of debugging, I came to realize that I've done absolutely nothing with the username, so I investigated further into what happens after the username is put in the system.

Step 6: <b><br>
I copied and pasted the code into a text file so I could trace which lines of code were being executed, and I noticed a call to printf was made and the return address of the next instruction to execute was stored on the stack.

Step 7: <b><br>
By manipulating printf, we can print that value out. We now know a specific location of the code. However this is not the address we want to return to. The goal is to have the program return to our password input.

Step 8: <b><br>
To get the address of our input, we merely calculate before hand how many bytes apart the stack is from that position in memory and perform a simple subtraction.

Step 9: <b><br>
Return to the password input, and execute your code for the win!
