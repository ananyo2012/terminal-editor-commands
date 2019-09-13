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
