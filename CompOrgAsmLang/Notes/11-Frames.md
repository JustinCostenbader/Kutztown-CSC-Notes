# Stack Frames and Advanced Procedures

## Stack Frame
- Also known as an **activation record**
- Area of the stack set aside for a procedure's return address, passed parameters, saved registers, and local variables
  - Managed using register EBP (frame "base pointer")
 
- Created by the following steps
  - Calling program pushes arguments on the stack and calls the procedure
  - The called procedure pushes EBP on the stack, and sets EBP to ESP.
  - If local variables are needed, a constant is subtracted from ESP to make room on the stack.

 ## Stack Parameters
 - More convenient than register parameters
 - Two possible ways of calling DumpMem. (DumpMem is an Irvine Library rountine for printing out data stored in memory)

## Passing Arguments by Value
- Push argument values on stack
  - (Use only 32-bit values in protected mode to keep the stack aligned)
- Call the called-procedure
- Accept a return value in EAX, if any
- Remove arguments from the stack if the called-procedure did not remove them

## Passing by Reference
- Push the offsets if arguments on the stack
- Call the procedure
- Accept a return value in EAX, if any
- Remove arguments from the stack if the called procedure did not remove them
