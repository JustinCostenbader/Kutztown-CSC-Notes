<h1 align="center">Structs</h1>

## Structure
- A template or pattern given to a logically related group of variables.
- **field** - structure member containing data
- Program access to a structure:
 - entire structure as a complete unit
 - individual fields
- Usefule way to pass multiple related arguments to a procedure
  - example: file directory information
 
## Using a Structure
Using a structure involves three sequential steps:
  1. Define the structure.
  2. Declare one or more variables of the structure type, called **structure variables**.
  3. Write runtime instructions that access the structure.

## Structure Definition Syntax
```
name STRUCT
  field-declarations
name ENDS
```
- Field-declarations are identical to variable declarations

## COORD Structure
- The COORD structure used by the MS-Windows programming library identifies X and Y screen coordinates
```
COORD STRUCT
  X WORD ?      ; offset 00
  Y WORD ?      ; offset 02
COORD ENDS
```

## Employee Structure

## Declaring Structure Variables

## Initializing Array Fields

## Array of Structures

## Referencing Structure Variables

## Looping Through an Array of Points
