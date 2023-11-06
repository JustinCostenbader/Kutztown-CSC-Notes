# Conditionals - 10
## Boolean and Comparison Instructions
   - AND Instruction
   - OR Instruction
   - XOR Instruction
   - NOT Instruction
   - CPU Status Flags
   - TEST Instruction
   - CMP Instruction

## J*cond* Instruction
### Specific Jumps
   - JB, JC: jump to a label if the Carry flag is set
   - JE, JZ: jump to a label if the Zero flag is set
   - JS: jump to a label if the Sign flag is set
   - JNE, JNZ: jump to a label is the Zero flag is clear
   - JECXZ: jump to a label if ECX = 0
### Jumps Based on Specific Flags
  - JZ: jump if zero (ZF=1)
  - JNZ: jump if not zero (ZF=0)
  - JC: jump if carry (CF=1)
  - JNC: jump if not carry (CF=0)
  - JO: jump if overflow (OF=1)
  - JNO: jump if not overflow (OF=0)
  - JS: jump if signed (SF=1)
  - JNS: jump if not signed (SF=0)
  - JP: jump if parity, even (PF=1)
  - JNP: jump if not parity, odd (PF=0)
### Jumps Based on Equality
  - JE: jump if equal *(leftOp = rightOp)*
  - JNE: jump if not equal *(leftOp != rightOp)*
  - JCXZ: jump if CX = 0
  - JECXZ: jump if ECX = 0
### Jumps Based on Unsigned Comparisons
  - JA: jump if above *(if leftOp > rightOp)* 
  - JNBE: jump if not below or equal (same as JA)
  - JAE: jump if above or equal *(if leftOp >= rightOp)*
  - JNB: jump if not below (same as JAE)
  - JB: jump if below *(if leftOp < rightOp)*
  - JNAE: jump if not above or equal (same as JB)
  - JBE: jump if below or equal *(if leftOp <= rightOp)*
  - JNA: jump if not above (same as JBE)
### Jumps Based on Signed Comparisons
  - JG: jump if greater *(if leftOp > rightOp)*
  - JNLE: jump if not less than or equal (same as JG)
  - JGE: jump if greater than or equal *(if leftOp >= rightOp)*
  - JNL: jump if not less (same as JGE)
  - JL: jump if less *(if leftOp < rightOp)*
  - JNGE: jump if not greater than or equal (same as JL)
  - JLE: jump if less than or equal *(if leftOp <= rightOp)*
  - JNG: jump if not greater (same as JLE)

## Conditional Loop Instructions
   - LOOPZ and LOOPE
   - LOOPNZ and LOOPNE

## Conditional Structures
   - Block-Structured IF Statements
   - Compound Expressions with AND
   - Compound Expressions with OR
   - WHILE loops
   - Table-Driven Selection
