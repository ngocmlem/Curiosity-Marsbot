# Curiosity-Marsbot
The Curioisity Marsbot runs on Mars, operated remotely by programmers on Earth. By sending control codes from a matrix keyboard, the programmer controls the movement of Marbot as follows:
1b4: Marbot begins to move
c68: Marbot stands still
444: Turn left 90* from recent direction of motion and maintain new direction
666: Turn right 90* from recent direction of motion and maintain new direction
dad: Started leaving marks on the road
cbc: Stop leaving marks on the road
999: Automatically return by reverse route. Do not draw a trace, do not receive another code until the reverse route is completed.
Description: Marsbot is programmed to remember the entire history of control codes and the time interval between code changes. Therefore, it can reverse the path to return to the starting point (although it may be a bit off because the syscall sleep function is not really real-time).

After receiving the control code, Curioisity Marsbot will not process it immediately, but must wait for the command to activate the code from the Keyboard & Display MMIO Simulator keyboard. There are 2 such commands:
"Enter" key: Finish entering the code and ask Marbot to execute
"Del" key: Delete all control codes that are in progress
