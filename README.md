# Text Document Analyzer in Assembly Language
A text file analyzer program written in **x86 Assembly Language** using the **Irvine32 library**. It provides a console-based menu to create, read, analyze, and manipulate plain text files.
## Group Members
| Name | ID |
|------|----|
| Ahmed Khalid | 22k-4018 |
| Adil Rizwan | 22k-4082 |
| Ibrahim Khawer | 22k-8715 |
---
## Overview
The program operates on a file called `output.txt` and lets the user perform a range of text file operations through a numbered menu. It is built entirely in x86 assembly, leveraging low-level file I/O and string manipulation routines.
---
## Features
| Menu Key | Feature |
|----------|---------|
| `1` | **Create New File** – Write new content to `output.txt` |
| `2` | **Word Count** – Count and display the total number of words |
| `3` | **Search Word** – Find and display the frequency of a given word |
| `4` | **Delete Word** – Remove all occurrences of a specified word |
| `5` | **Replace Word** – Replace all occurrences of a word with a new word |
| `6` | **Read & Display** – Read and display the current file content |
| `7` | **Reset File** – Clear/reset the contents of `output.txt` |
| `0` | **Exit** – Quit the program |
---
## How It Works
### Procedures
| Procedure | Description |
|-----------|-------------|
| `main` | Displays the menu and dispatches to the selected procedure |
| `newfile` | Prompts for text content and writes it to `output.txt` |
| `read_file` | Opens and reads `output.txt` into an in-memory buffer |
| `countwords` | Counts words in the buffer using space (`' '`) as a delimiter |
| `searchword` | Prompts for a word and counts its occurrences in the buffer |
| `deleteword` | Finds and removes all occurrences of a given word in the buffer |
| `replaceword` | Finds and replaces all occurrences of a word with another |
| `updatefile` | Writes the modified buffer back to `output.txt` |
| `reset` | Recreates `output.txt` as an empty file |
| `findindex` | Locates the index of a matching word in the buffer |
| `compare_substring` | Compares a substring to verify a word match |
### File Handling
The program uses Irvine32 procedures (`OpenInputFile`, `CreateOutputFile`, `ReadFromFile`, `WriteToFile`, `CloseFile`) for all file I/O. All text is stored in a 500-byte `buffer` between operations.
---
## Requirements
- **Assembler:** Microsoft MASM (ML) or compatible x86 assembler
- **Library:** [Irvine32](http://asmirvine.com/) – Kip Irvine's 32-bit assembly library for Windows
- **OS:** Windows (32-bit or 32-bit compatibility mode)
- **Linker:** Microsoft Linker (included with MASM / Visual Studio)
---
## Getting Started
### 1. Install MASM and Irvine32
1. Install **Visual Studio** (any edition) with the MASM component.
2. Download and set up the **Irvine32 library** from [http://asmirvine.com/](http://asmirvine.com/).
### 2. Assemble and Link
Copy the assembly source code from `Code Text File Analyzer.docx` into a `.asm` file (e.g., `analyzer.asm`), then assemble and link:
```
ml /c /coff analyzer.asm
link /subsystem:console analyzer.obj Irvine32.lib kernel32.lib user32.lib
```
Or open the project in a Visual Studio solution configured with the Irvine32 include/library paths.
### 3. Run
```
analyzer.exe
```
The program will display the menu and wait for your input. All operations are performed on `output.txt` in the same directory as the executable.
---
## Project Structure
```
├── Code Text File Analyzer.docx   # x86 assembly source code
├── Report-Text File Analyzer.pdf  # Project report and documentation
└── README.md
```
---
## Advantages & Limitations
### Advantages
- **Low-level control** over file operations and memory
- **Lightweight and fast** – no runtime overhead
- Demonstrates the practical use of assembly language for text processing
### Limitations
- Console-based interface only
- Buffer limited to 500 bytes of text content
- Requires familiarity with x86 assembly and the Irvine32 library setup
---
## References
- Kip Irvine – *Assembly Language for x86 Processors* ([asmirvine.com](http://asmirvine.com/))
- Intel x86 Instruction Set Reference
- `Report-Text File Analyzer.pdf` (included in this repository)
