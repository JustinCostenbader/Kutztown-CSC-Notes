## CSC235 - Final Project, olympians
Assignment: Write a program that will store and retreive information using an array of structs.
<br>
Supplied: 
<br>
A folder containing a Visual Studio project that is set up for a MASM program.
<br>
An example input data file called *olympians.txt*.
<br>
Location: OneDrive Projects folder, under Project 5
<br>
Deliverable: **Only** the **olympian.asm** file containing the completed program.
<br>
<br>
Overview:
<br>
In this project, you will complete a program that will read information from a file, load it into an array of structs, and then display the information on the screen.
<br>
<br>
Your starting point will be a VS project with a pre-defined strucutre called *olympian* and a procedure called *readFileChar*, which is also pre-defined. *readFileChar* will read one character of information from an open text file, returning the character in eax.
<br>
<br>
Your task is to write and call procedures, described below, to load an array of *olympian* structs with the information about some olympians that will be read from a file with a well-defined format. You will then output the data in the struct array for display on the terminal.
<br>
<br>
A properly formmatted text file, called *olympians.txt*, is provided for initial testing purposes. You will need to write additional tests of your own as described below.
<br>
<br>
Requirements:
<br>
<br>
The basic operation is as follows:
<br>
1) Ask the user for the number of olympians
2) Open a file containing olympian information
3) Read the information for the number of olympians requested (or until the end of the file), loading the information into the *olympian* struct array.
4) Output the information, as decribed below
5) Be sure to close the file!

You will need to write a number of procedures to accomplish this.
<br>
<br>
First, you will need to query the user for the number of olympians to process. Once you have that, you will need to write a procedure to allocate memory in the program's heap to hold an array of *olympian* structs for storing the data, returning the pointer to the struct array.
<br>
<br>
As mentioned, you are supplied with a procedure called *readFileChar* that will serve as a basis for doing file access. We will go over this procedure in class.
<br>
<br>
As in high level languages, in order to access information in a file, it must first be opened. You will do this in your *main* procedure by prompting for the name of the filel and using the Irvine procedure called *OpenInputFile* to open it (Irvine, Chapter 5- look it up!). This procedure will provide you with a file pointer in EAX that you can use to read the information in the file. Be sure to exit the program gracefully on an error (hint: compare EAX to INVALID_HANDLE_VALUE).
<br>
Also, be sure to close the file when you are finished with it.
<br>
<br>
Once the file has been successfully opened in main, and a pointer obtained, you will need to call several procedures that you will write to get the information from the file, load it into the array of olympian structs, and output the required data. Note that you are **required** to comment your procedures in a manner similar to what is provided in *readFileChar* - including a header and individual line comments.
<br>
<br>
Procedures:
<br>
<br>
All procedure should make use of stack frames to recieve input parameters (as discussed in class and in Chapter 8 of the text - see *readFileChar*). Where it is necessary to output information to the console, use procedures supplied in the Irvine32 library. Note that this also implies that we are using he STDCALL calling convention, as opposed to the C calling convention (sec 8.2.4).
<br>
<br>
Following is a list of procedures you need to write and use in your program:
<br>
<br>
*allocOlympians*:
<br>
This procedure takes as input the number of structs (olympians) that should be in the array. It should access the heap and allocate sufficient memory to store that number of structs and return the pointer to be used as the array pointer.
<br>
<br>
Receives:
- number of structs (olypians) in the array
<br>
Returns (in eax):

- A pointer to the allocated array
- set the carry flag on an error.
- (don't forget to test it when you return from the procedure)
<br>
<br>

*readFileLine*:
This procedure reads bytes from an open text file by calling *readFileChar*. It stores those bytes in a target character array, loading them in successive array locations, building up a string. It continues reading and storing bytes until it encounters the end of a line. This is represented by the line feed character, which is hex cose 0x0A. In the target array, simply substiture a NULL character for the line-feed. This will result in a final well-formatted string containing the line just read with a proper NULL character termination. This will also leave the file pointer in a position to read the next line of the file on the next call to the *readFileLine*, enabling successive calls to *readFileLine* to sequentially read file data line by line.
<br>
<br>
IMPORTANT: There is a wrinkle in this process. Unix files end lines with the line feed character as just described. In Windows, however, lines end with a two-character combination - the line feed character is preceded by a carriage return character, which is hex code 0x0D. So, in Windows, lines end with 0D0Ah. In Unix, they end with just 0Ah.
<br>
Since we are working in Windows, you need to handle the two character combination. The solution is simple. Just ignore the carriage return. When you encounter it, don't store it in the string. Simply move on to the next character, which should be a line feed. This approach has the added bonus of properly handling text files created in either Windows or Unix.
<br>
<br>
Receives:
- pointer to open file
- pointer to the output BYTE array (string)
- max size of the string
To avoid accessing past the end of the BYTE array, the max number of bytes read should be one less than the string size - to allow room for the terminating NULL character.
<br>
Returns (in eax):

- The number of characters read and stored in the target array.
- Also, if any kind of error occurs, the carry flag should be set (and tested upon return)!

<br>
<br>

*loadOlympian*:
<br>
This procedure reads information, line by line, from a file using *readFileLine*, and loads it into a olympian struct. Before loading anything into the struct, the procedure should first check to see if the file pointer is positioned at the beginning of information for a olympian. A properly formatted file will precede five lines of olympian information with a line containing just an asterisk. Following that, on separate lines, will be the olympian's name, their class, followed by three medal counts (gold, silver, bronze). Refer to the provided *olympian.txt* file example. Loading the medals will require special attention. You will first need to create and load a local string variable (BYTE array) with a medal count using *readFileLine*. Once the count is loaded into the local string, *ParseInteger32* (from the Irvine32 library) can be used to convert the string representation of the number to a DWORD that can then be loaded into the struct.
<br>
<br>
Receives:
- pointer to the beginning of a struct object
- file pointer
<br>
Returns (in eax):

- updated file pointer (which has been advanced past the information just loaded)
- If an unsuccessful load occurs, i.e. an error is encountered or a leading asterisk is not found, the carry flag should be set (and tested upon return)!