
# CTF Writeups Collection

**Competition Experience:** 50+ CTF events
**Notable Achievements:** Top 10% in multiple national competitions

---

## Overview

Collection of Capture the Flag competition solutions demonstrating penetration testing methodologies and problem-solving approaches.

[View writeups](https://github.com/chad-hackerman/ctf-writeups)
---

## Featured Writeups

### Web Exploitation - SQL Injection
Identified and exploited blind SQL injection vulnerability in authentication system. Used time-based techniques to extract database contents without error messages.

**Tools Used:** Burp Suite, SQLMap, Custom Python scripts

**Key Learning:** Boolean-based blind injection when time-based is blocked

---

### Cryptography - RSA Weak Keys
Broke RSA encryption by exploiting small public exponent with common modulus attack. Recovered plaintext from two ciphertexts encrypted with related keys.

**Tools Used:** Python, gmpy2 library

**Key Learning:** Importance of proper key generation and padding schemes

---

### Binary Exploitation - Buffer Overflow
Achieved remote code execution through stack-based buffer overflow. Bypassed ASLR using information leak, then ROP chain for shell access.

**Tools Used:** GDB, pwntools, ROPgadget

**Key Learning:** Modern exploit mitigation bypasses

---

### Reverse Engineering - Malware Analysis
Analyzed obfuscated malware binary to recover C2 server communication protocol. Identified encryption algorithm and extracted encryption keys.

**Tools Used:** IDA Pro, Ghidra, x64dbg

**Key Learning:** Static and dynamic analysis techniques

---

## Competitive Results

- **DEF CON CTF Qualifier 2023** - Top 15% globally
- **SANS NetWars Tournament** - 2nd place regional
- **PicoCTF 2023** - Top 5% of 10,000+ participants

---

[← Back to Main Portfolio](../README.md)
