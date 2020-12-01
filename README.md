# ImHex

A Hex Editor for Reverse Engineers, Programmers and people that value their eye sight when working at 3 AM.

## Features

- Featureful hex view
  - Byte patching
  - Patch management
  - Copy bytes as feature
    - Bytes
    - Hex string
    - C, C++, C#, Rust, Python, Java & JavaScript array
    - ASCII-Art hex view
    - HTML self contained div
  - String and hex search
  - Colorful highlighting
  - Goto from start, end and current cursor position
- Custom C++-like pattern language for parsing highlighting a file's content
  - Automatic loading based on MIME type
  - arrays, pointers, structs, unions, enums, bitfields, using declarations, litte and big endian support
  - Useful error messages, syntax highlighting and error marking
- Data importing
  - Base64 files
  - IPS and IPS32 patches
- Data exporting 
  - IPS and IPS32 patches
- Data Exporting
- Data inspector allowing interpretation of data as many different types (little and big endian)
- Huge file support with fast and efficient loading
- Strings search
  - Copying of strings
  - Copying of demangled strings
- File hashing support
  - CRC16 and CRC32 with custom initial values and polynomials
  - MD4, MD5
  - SHA-1, SHA-224, SHA-256, SHA-384, SHA-512
- Disassembler supporting many different architectures
  - ARM32 (ARM, Thumb, Cortex-M, aarch32)
  - ARM64
  - MIPS (MIPS32, MIPS64, MIPS32R6, Micro)
  - x86 (16 bit, 32 bit, 64 bit)
  - PowerPC (32 bit, 64 bit)
  - Sparc
  - SystemZ
  - XCore
  - 68K
  - TMS320C64x
  - 680X
  - Etherium
- Bookmarks
  - Region highlighting
  - Comments
- Data Analyzer
  - File magic based file parser and MIME type database
  - Byte distribution graph
  - Entropy graph
  - Highest and avarage entropy
  - Encrypted / Compressed file detection
- Helpful tools
  - Itanium and MSVC demangler
  - ASCII table
  - Regex replacer
  - Mathematical expression evaluator (Calculator)
  - Hexadecimal Color picker
- Built-in cheat sheet for pattern language and Math evaluator
- Doesn't burn out your retinas when used in late-night sessions

## Screenshots

![](https://i.imgur.com/xH7xJ4g.png)
![](https://i.imgur.com/fhVJYEa.png)

## Compiling

This guide assumes you're either on Windows using mingw or on Arch Linux

The following libraries are needed to compile ImHex. All of them can be found in the default pacman repositories
```
GLFW3                                             ( (sudo) pacman -S glfw )
libmagic, libgnurx, libtre, libintl, libiconv     ( (sudo) pacman -S file )
libcrypto                                         ( (sudo) pacman -S openssl )
capstone                                          ( (sudo) pacman -S capstone )
libLLVMDemangle                                   ( (sudo) pacman -S llvm llvm-libs )
nlohmann json                                     ( (sudo) pacman -S nlohmann-json )
Python3                                           ( (sudo) pacman -S python3 )

All in one: sudo pacman -S glfw file openssl capstone llvm llvm-libs nlohmann-json python3
```

After all the libraries are installed, run the following commands to build ImHex
```
mkdir build
cd build
cmake ..
make -j
```

On Windows, download the python standard library from https://github.com/python/cpython/tree/master/Lib and place the files and folders in `lib/python3.8` next to your built executable. Don't forget to also copy the `libpython3.8.dll` from your mingw setup next to the executable.

On both Windows and Linux, copy the files from `python_libs` in the `lib` folder next to your built executable.
Place your magic databases in the `magic` folder next to your built executable
Place your patterns in the `pattern` folder next to your built executable
Place your include pattern files in the `include` folder next to your built executable
