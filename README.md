# Recursive GCD in C

A small learning exercise implementing Euclid's greatest-common-divisor (GCD)
algorithm with recursion.

## What is actually in this repository

The `code` file contains a `gcd(int a, int b)` function and an interactive `main`.
The current implementation does **not** contain recursive array processing or a
separate negative-number detection algorithm.

## Build and run the current file

The source is currently named `code` without a `.c` extension. Tell GCC or Clang
to treat it as C:

```sh
cc -x c -std=c11 -Wall -Wextra -Wpedantic code -o gcd
./gcd
```

On Windows, a C compiler must be installed first; the executable is normally
launched as `gcd.exe`.

Example input/output:

```text
Enter two numbers: 48 18
GCD: 6
```

## Algorithm

For nonnegative integers, `gcd(a, b) = gcd(b, a % b)` until `b == 0`.
For positive inputs, time complexity is O(log(min(a, b))); the recursive calls
use O(log(min(a, b))) stack space. An input with `b == 0` returns immediately.

## Current limitations

- `scanf`'s return value is not checked; malformed input is not handled safely.
- Inputs must fit the platform's `int` range.
- Negative inputs can produce a negative result, so use nonnegative inputs.
- `gcd(0, 0)` returns zero as an implementation convention.
- There is no automated test suite yet.

## Next improvements

1. Rename `code` to `gcd.c` for standard compiler and GitHub language detection.
2. Add input validation and define negative-input behavior.
3. Separate the algorithm from input/output and add tests for zero, equal values,
   coprime values and invalid input.

This README describes the existing implementation; the next improvements are
plans, not completed features.
