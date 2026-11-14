# SHA256-BruteForce-With-Pthreads

**Developed during the academic year 2024-2025.** This educational project compares sequential and multithreaded brute-force searches for SHA-256 hashes, using C and Pthreads.

## Overview

The programs search for a password by hashing candidate strings and comparing each result with a target SHA-256 hash. They support passwords of exactly five lowercase letters (`a-z`), for a total search space of 26^5 candidates.

## Implementations

- `sha256_seq.c` checks candidates sequentially and stops when it finds a match.
- `sha256_pthread.c` uses four Pthreads to search different portions of the candidate space concurrently. The threads stop searching when a match is found.

## Build and run

### Requirements

- GCC
- OpenSSL development libraries
- Pthreads

On Linux, install the OpenSSL development package (for example, `libssl-dev` on Debian or Ubuntu). Then compile the programs:

```bash
gcc sha256_seq.c -o sha256_seq -lcrypto
gcc sha256_pthread.c -o sha256_pthread -pthread -lcrypto
```

Run either program; it will prompt you to enter the target SHA-256 hash as 64 hexadecimal characters:

```bash
./sha256_seq
./sha256_pthread
```
