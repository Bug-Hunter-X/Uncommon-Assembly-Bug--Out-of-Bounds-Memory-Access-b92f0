# Uncommon Assembly Bug: Out-of-Bounds Memory Access

This repository demonstrates an uncommon bug in assembly code related to out-of-bounds memory access.  The bug arises from an incorrect calculation of a memory address, leading to a segmentation fault or access violation.

## Bug Description
The assembly instruction `mov eax, [esi+ebx*4+0x10]` calculates a memory address. If the values in `esi` and `ebx` are such that the resulting address is outside the bounds of allocated memory, or attempts to access a memory location the program is not permitted to access, this will cause a crash.

## How to Reproduce
The `bug.asm` file contains the buggy code. To reproduce the error, assemble and run the code with values for `esi` and `ebx` that result in an out-of-bounds memory address. The exact values will depend on the system and how memory is allocated.  The solution demonstrates how to avoid this error.

## Solution
The `bugSolution.asm` file provides a corrected version of the code. This version includes comprehensive checks to ensure that the calculated memory address is within valid bounds before attempting to access it.