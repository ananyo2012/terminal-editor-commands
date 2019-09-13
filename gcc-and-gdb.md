# GCC

| Commands | Description |
|---|---|
| `gcc -o hello hello.c` | Create executable with name hello |
| `gcc -c hello.c` | Preprocess and compile only |
| `gcc hello.o -lm` | Tells the compiler (ie. gcc) to link the executable file with the given library (math.h here) |
| `gcc -x c hello.txt` | `-x` option asks for source language |
| `gcc -std=89 hello.c` | `-std` option is for specifying standard |
| `gcc -I ./sources -o hello hello.c` | `-I` option is for path to header files |

## Creating and using Static libraries

1. `gcc -c greet.c` - Create `greet.o` after compiling greet.c
2. `ar cr libgreet.a greet.o` - Create static library (archive) from object file
3. `ar -tvf libgreet.o` - See the contents of an archive file
4. `gcc -L ./ -o hello hello.c -lm -lgreet` - `-L` option specifies the directory to search the static library

## Creating and using Dynamic libraries

1. `gcc -c -fPIC greet.c` - Generate object file in fixed position code format
2. `gcc hello.o -shared -o libgreet.so` - Create dynamic library (.so) from object file
3. `gcc -I ./headers -L ./ -o hello hello.c -lgreet` - Link dynamic library during linking stage

## Other useful flags

| Command | Description |
|---|---|
| `-Wall` | enable **all** compile time warning messages |
| `-O<level>` | This option is used to specify the code optimisation level. `<level>` here is an integer. This way while generating binary code for macros, or loop statements, or pointer/string operations, gcc can produce more efficient/faster code. |
| `-g` | Adds extra information to the executable which can be used for debugging |
| `-S` | Used to produce the compilation output in an assembly language, i.e. a step just before the code generation. It produces a `.s` file while contains program in assembly code. |

# GDB

There are 2 ways to attach a program to gdb

1. Attach using executable
```
gdb ./exec # You can just use the command that points to the executable or use the full path
gdb --args ./exec arg1 arg2 # Debug executable with command lines args
```
2. Attach a running process
```
ps -al # Get the PID of the process you want to debug
gdb -p <PID>
```
Once you attach the program to gdb you can start debugging the program using various gdb commands

Commands | Description
---|---
b <func_name> | Set breakpoint in the first line of specified function
b filename.c:n | Set breakpoint at line `n` of the file
r | Run program. After you set breakpoints this is the first command to run to start execution
info b | List all breakpoints
n | excute next statement
c | continue excution (Step Over)
step | Step into next funtion (Step into)
finish | finish function execution and return to it's caller. Shows what value the function returned (Step out)
ignore <k> [n] | skips breakpoint `k`, `n` no of times. `k` is the no that shows up in `info b`
disable <k> | disables a breakpoint `k`
enable <k> | enables a breakpoint `k`
delete <k> | deletes a breakpoint `k`
p <var> | prints the value of a variable
list | Shows 10 lines above and below breakpoint
set x=1 | sets the value of the variable `x`
call func() | call func() (any linked function), can be standard lib or user defined
backtrace/bt | see call stack
frame <n> | go to frame n in stack
info frame | Displays info about current stack frame
info args | Shows the value of arguments in the function
info locals | Shows the value of locals
watch x | Sets a watch on variable x
rwatch x | Sets a read watchpoint for x
awatch x | Sets a read/write watchpoint for x
core <filename> | Debug a coredump
ENTER | Execute last command
`b file.c:n if i >= ARRAYSIZE` | Conditional breakpoint
q | quit gdb  


