# nim arm-none-eabi
Tiny test of nim cross-compiling for arm-non-eabi nosys.

# building
# install compiler
To build the lib, install the `nim` compiler first (`sudo apt install nim`).
I tested with this version:
```bash
➜ nim --version
Nim Compiler Version 0.17.2 (2018-02-05) [Linux: amd64]
Copyright (c) 2006-2018 by Andreas Rumpf
active boot switches: -d:release
```

You'll also need the arm-none-eabi toolchain.

Either install from releases here:
>https://developer.arm.com/open-source/gnu-toolchain/gnu-rm/downloads

Or `sudo apt install arm-none-eabi libnewlib-arm-none-eabi`.
I tested with this version:
```bash
➜ arm-none-eabi-gcc --version
arm-none-eabi-gcc (GNU Tools for Arm Embedded Processors 7-2018-q2-update)
7.3.1 20180622 (release) [ARM/embedded-7-branch revision 261907]
Copyright (C) 2017 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
```

# build command
Run this:
```bash
➜ nim cc --app:staticlib test.nim
Hint: used config file '/etc/nim.cfg' [Conf]
Hint: used config file '/home/noah/dev/test/nimtest/nim.cfg' [Conf]
Hint: system [Processing]
Hint: test [Processing]
Hint:  [Link]
Hint: operation successful (7727 lines compiled; 0.041 sec total; 7.344MiB peakmem; Debug Build) [SuccessX]
```
Should emit a `libtest.a`.
