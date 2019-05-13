# Game Hacking

## Notes
- To edit the memory of a game, you must first create a handle for the process. After creating the handle and obtaining the process ID (PID), you can change the access to that process to `FULL`. From there you can find all modules loaded within the process and begin reading/writing memory values.
- The structure for memory within games (and I believe all processes) is as follows: `Module -> Base Pointer -> Offset`. Where `Module` is an imported module that holds the specific structures you'd like to read or write to, `Base Pointer` is the pointer that points to your structure, and `Offset` is the offset from the pointer to the exact memory value. An example would be `GameModule.dll + PointerValue + Offset`, which would yield some value within memory.
- Use `uintptr_t` (in C++) data types instead of things like `DWORD`, as `uintptr_t` is platform agnostic and will work on Windows, Linux, etc.
- When using an infinite loop, adding `Sleep(1)` (in C++) supposedly helps put less stress on the CPU.

## Links
- [SlimMem](https://www.unknowncheats.me/forum/c-and-c-/167302-slimmem-simple-memory-manipulation-class.html) - A simple to use memory-manipulation class
