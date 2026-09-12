# AGENTS.md

Single-file C++ CLI tool (`main.cpp`) for finding duplicate files. C++20, CMake, Boost (iostreams, crc), OpenSSL (MD5).

## Build

Dependencies: `sudo apt install libboost-iostreams-dev libssl-dev`

```bash
cmake -B build && cmake --build build
```

Output binary: `build/dupdog`

## Quick test

```bash
./build/dupdog <path> <extensions> [-a md5|crc32|fso] [-v]
```

No tests or linters exist in this repo.

## Notes

- Single source file: `main.cpp` (all logic inline, no libraries or subpackages).
- Project name is "dupdog" consistently across `main.cpp`, `README.md`, and `AGENTS.md`.
- Known bug: `std::bad_alloc` crash when no duplicates are found (see `todo.txt`).
- `build/` is in `.gitignore` but currently tracked in git history.
