
# AFL

American Fuzzy Lop is a program fuzzer.

Instruments program source - can't fuzz binaries you don't have src to.

Need to create test cases.

Create a file used for test input.

Each test case mutates the file, and the program is run with it.

Build with:

```
CC=/path/to/afl-gcc CXX=/path/to/afl-g++ ./configure --disable-shared
make clean all
```

## See also
http://lcamtuf.coredump.cx/afl/QuickStartGuide.txt