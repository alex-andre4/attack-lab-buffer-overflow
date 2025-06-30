# 🔐 Attack Lab – Buffer Overflow & ROP Exploits

This repository contains completed work from the **Attack Lab** assigned in COSC 30203 – *Computer Systems Fundamentals* at Texas Christian University.

The lab explores stack-based buffer overflows and Return-Oriented Programming (ROP) through two custom binaries (`ctarget` and `rtarget`), each progressively more hardened.

---

## 📚 Lab Overview

| Phase | Binary    | Exploit Type | Goal                  | Points |
|-------|-----------|--------------|-----------------------|--------|
| 1     | ctarget   | Code Inject  | Call `touch1()`       | 10     |
| 2     | ctarget   | Code Inject  | Call `touch2(cookie)` | 25     |
| 3     | ctarget   | Code Inject  | Call `touch3(cookie)` | 25     |
| 4     | rtarget   | ROP          | Call `touch2(cookie)` | 35     |
| 5     | rtarget   | ROP          | Call `touch3(cookie)` | 5      |

---

## 🧠 Key Concepts

- Stack frames and memory layout on x86-64
- Code injection techniques using shellcode or bytecode
- ROP chains to bypass stack protections
- Use of tools: `gdb`, `objdump`, `xxd`, `gcc`, `make`
- Buffer overflow & stack smashing
- Code injection using shellcode and control flow redirection
- Return-Oriented Programming (ROP) with gadget chaining
- Stack frames, register usage, memory inspection

---

## 🧪 Exploit Input Files

Each phase was solved using an input file composed of carefully crafted hexadecimal byte sequences. These input files are stored in the [`exploit-scripts`](./exploit-scripts) folder.

To test locally (example for phase 1):

```bash
./ctarget -q < exploit-scripts/phase1.txt

💡 Setup Instructions
Tools Required:

    Linux environment (run lab on babbage.cs.tcu.edu)

    gdb, objdump, gcc

    hexdump, xxd, vim/nano

Run targets:

./ctarget -t 999 1
./rtarget -t 999 2

(Use the -t 999 option to set a generous timeout while testing manually.)
🛡️ Notes on Security & Ethics

This lab was completed in a controlled environment for academic purposes. Exploit development should never be used on live systems or networks without proper authorization.

📜 License

MIT License (for educational reuse)
