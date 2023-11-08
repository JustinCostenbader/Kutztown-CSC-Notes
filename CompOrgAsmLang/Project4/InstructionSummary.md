# Project 4 (Vowels) Summarized Instructions:

- Must store vowel counts in an array and output them after all vowels have been processed (NOT as they are found).
- Use symbolic constants to set fixed values (array sizes).
- Just search for lower case vowels and disregard "y" for this project.
- Use Irvine32 procedures for input/output display.

  ## Main PROC:
  - Prompt user for character string (up to 100 characters).
  - Read and store the user string.
  - Call "CountChars" procedure that will count the number of occurences for each vowel.
  - Store the total for each vowel in an array.
  - Output the totals and pause execution so that the user can see the results.

  ## CountChars PROC:
  - Inputs should be supplied to NumChars via registers as decribed in class and in chapter 5 of the textbook.
  - The character count should be returned in a register.
  - Properly manage the stack so that register data does not get corrupted
  - Irvine32 input/output
