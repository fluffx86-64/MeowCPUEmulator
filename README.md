# MeowCPUEmulator
An Emulation of the CPU I am currently designing.
![Alt text](images/Main.PNG?raw=true "Logisim Design")
------------------------------------------------

// Help //

This is a CPU Emulation, from the current CPU I am designing on Logisim (A Circuit Simulation Program) named MeowCPU.
* yes i know meowcpu is a shit name im no good at naming stuff :c

[*] Still early in developlent (clearly, due to lack of instructions).

// How to use the Emulator //

/*/ Important Make Sure there are whitespaces seperating the INSTRUCTION, OPERAND and VALUE. /*/

eg. 0000 00000 00000000
        ^     ^
       WHITESPACES

/*/                                                                                         /*/
Firstly how the CPU works, the CPU Currently has 5 Registers named A,B,C,D,E.
A and B are the only registers currently being used to store user values.
C,D,E Registers store the result of A,B. Result varying in which instruction you use. 
An instruction for the CPU is for example [0000 (4bits) 00000 (5bits) 00000000 (8bits)] for a total of 17 bits per instruction.
An instruction can be broken down into 3 parts as listed above ^, the first four bits are the opcode.
Here are the following supported opcodes:
    "0000": "MOV" // MOVE TO REGISTER
    "0001": "ADD" // ADD REGISTER A AND REGISTER B AND STORE RESULT IN REGISTER C
    "0010": "SUB" // SUBTRACT REGISTER A AND REGISTER B AND STORE RESULT IN REGISTER D
    "0100": "CMP" // COMPARE REGISTER A AND REGISTER B AND STORE RESULT IN REGISTER E
With "CMP" Instruction, there are 3 compartive values that can be stores.
Here is a table showing the value of Register E with the meaning of the value.
IF 2 IS STORED IN E, THIS MEANS A == B.
IF 1 IS STORED IN E, THIS MEANS A > B.
IF 4 IS STORED IN E, THIS MEANS A < B.

With "ADD" and "SUB" Instruction, set the operand to 00000 (5 bits of '0') and the value to 00000000, they will serve as
a placeholder as they will not effect the outcome as the value after the arithetic has been applied will be either stored in
C,D,E (depending on which instruction you use). 
------------------------------------------------
The second part of the Instruction is the operand (aka. what to effect).

EG. MOV A, 4
0000 = MOV
00001 = A
00000100 = 4 (TWOS COMPLEMENT) // ALL NUMBERS BINARY NUMBERS SHOULD BE IN TWOS COMPLEMENT.
TOTAL: 0000 00001 00000100

In this scenario we are setting the value of register A, which value is 00001.


You can set register B's using 00010.
EG. MOV B, 4
0000 = MOV
00010 = A
00000100 = 4 (TWOS COMPLEMENT) // ALL NUMBERS BINARY NUMBERS SHOULD BE IN TWOS COMPLEMENT.
TOTAL: 0000 00010 00000100


A REGISTER: 00001
B REGISTER: 00010
------------------------------------------------------------------------------------------------
And finally if you havent noticed the last 8 bits are the value which you are going to store. (2'S COMPLEMENT).
------------------------------------------------------------------------------------------------
Last Updated: 9/01/23
------------------------------------------------