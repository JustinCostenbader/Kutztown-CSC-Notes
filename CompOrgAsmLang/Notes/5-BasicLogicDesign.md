# Basic Logic Design - 5

## Sequential vs. Combinatorial
- Combinatorial Circuits
  - Always get the same result for a given set of inputs
- Sequential Circuits
  - Information is stored
  - Output depends on both current inputs and internally stored state(s)
  - A "counter" is a good example
    - "Current count" is stored
    - next value depends on the current count
  - Important for making memories and state machines
  - Important for managing information flow

 ## Basic Latch
 - A **Latch** is a circuit that stores one bit of information
 - Inputs
   - Data - the value to store
   - Enable (or Clock) - data is stored when active
   - Output - the presently stored value
- Various types
  - SR latch
  - D latch
  - JK latch

## Set-Reset (SR) Latch

## D Latch

## Master Slave Flip Flop

## Flip-Flop timing diagram

## Registers

## Example Register

## Memory
- Like registers, but 2-dimensional
  - Stores an array of multi-bit data values

## Typical Memory Interface
- Address Bus
  - Selects which word to access in the memory
- Data Bus*
  - On write: provides the data to store in the memory
  - On read: gets loaded with the addressed word contents
- Write Enable
  - When asserted, write data on Data Bus to the memory
  - Otherwise, read from the memory
- Clock
  - When active, perform the selected operation
* Note: may have seperate read and write Data Busses

## 2<sup>2</sup>x3 Memory

## Register Transfer Logic
- Register Transfer Logic (RTL) is used to implement computational circuits - like microprocessors
- Parallel bits, representing data, are transferred from register to register
- Between the registers is combinatorial logic
  - Data gets modified as it passes through the logic implementing a desired function
- The multi-bit connection between registers is reffered to as a "bus"
  - The number of bits in the bus depends on the architecture (64, 32, 16, ...)

## RTL Example

## Basic Microcomputer Design
- clock synchronizes CPU operations
- control unit (CU) coordinates sequence of exectution steps
- ALU performs arithmetic and bitwise processing
- buses carry multi-bit words representing memory addresses, data, or control information
  - typically 64 bits wide, 32 bits in older machines
