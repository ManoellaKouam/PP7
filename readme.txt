Manoella readme: 
Time spend: almost 91 minutes because i was struggling with the installation of gcc on my windows machine
	    I have also installed gitBash for linux specific commands like "sed"

Task 1: C Compilation Stages 
-------------------------------------------------
- Preprocessing (-E): Expands #include <stdio.h> into its full content (e.g., printf declarations), handles macros, and removes comments. 
- Compilation to Assembly (-S): Translates preprocessed C code (sample.i) into assembly (sample.s). 
- Assembly (-c): Converts assembly code (sample.s) into machine code, producing an object file (sample.o) 
- Linking: Combines the object file (sample.o) with libraries to create the executable (sample). 

Running ./solutions/sample outputs "Hello, PP7!".

Task 2: Regex Search & Replace in Code 
-------------------------------------------------------
- grep: Uses regex ("printf\s*\(") to search for printf calls, outputs matching lines with line numbers (-n). 

- sed: Performs in-place substitution (s/printf\s*/debug_printf/g) using regex. Efficient for automated replacements. 
- awk: Extracts lines matching /debug_printf/ and prints them with line numbers. More flexible than grep for processing output. I may use this to manipulate matched lines.
- Vim Interactive: Uses /printf to search and :%s/printf/debug_printf/g to replace interactively. Ideal for manual edits with visual feedback. use this when i need to review changes.
- Vim CLI: Automates substitution (:%s/printf/debug_printf/g) without opening the UI. Useful for scripted edits. 

Task 3: Modular Linking with extern 
------------------------------------------------------------
- Role of extern: The extern int add(int, int); declaration in main.c tells the compiler that the add function exists in another file (add.c). It allows main.c to compile without the function's definition, deferring resolution to linking.
- Why separating compilation speeds up builds: Compiling add.c and main.c separately into add.o and main.o means only changed files need recompilation. In large projects, this saves time compared to recompiling all sources.
- Manual Linking vs. gcc Single Command: Manual linking explicitly combines object files and resolves references. Using gcc main.c add.c -o add_example handles all steps automatically, which is simpler but less flexible.
