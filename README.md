# decode

**Disclaimer:** There is currently a bug in the Lua disassembly routine,
which might lead to strange behaviour in the disassembly of functions.
I am working on it.

A Lua/Python Bytecode Disassembler. It is in the very early stages of
development. The Lua Disassembler could be called semi-functional,
a typical listing it provides you with would look like this:

```
$ bin/decode test/hello.luac 
File has 'luac' ending, assuming lua bytecode.

; Disassembly of file: test/hello.luac
; Endianness: little endian
; Int size: 4
; Size_t size: 8
; Instruction size: 4
; lua_Number size: 8

; Source file name: hello.lua 
; Line defined: 0
; Last Line defined: 0
; Number of Upvalues: 0
; Number of Parameters: 0
; Vararg flag: 2
; Maximum stack size: 2

; Constants: (Size 2)
; Line	Type	Value
; -------------------
0000	STRING: print 
0001	STRING: hello world and lua 

; Function prototypes list(Size 0): {
; }

; Opcodes (Size 4): 
; Line	Opcode		       A	|	       B	|	       C
; -------------------------------------------------
  0001	GETGLOBAL	       0	|	       0	|
  0001	LOADK   	       1	|	       1	|
  0001	CALL    	       0	|	       2	|	       1
  0001	RETURN  	       0	|	       1	|


; End of binary information.
```

The code looks like it just came out of a cows' behind, so beware.

## Why another disassembler?

This disassembler is written purely in C, so it may well be faster than lad, 
ChunkySpy, dis et al.
Also, **it does not depend on any external libraries**. You can use it even
without having Lua or Python installed. Yay, right?

## TODO

* Parse Lua nested functions(curious bug)
* Parse Python (only header is parsed until now)
