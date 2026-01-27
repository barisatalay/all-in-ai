# C / C++

## Detection signals
- `CMakeLists.txt`
- `meson.build`
- `Makefile`
- `conanfile.*`, `vcpkg.json`
- `compile_commands.json`
- `src/`, `include/`

## Multi-module signals
- `CMakeLists.txt` with `add_subdirectory(...)`
- Multiple `CMakeLists.txt` or `meson.build` in subdirs
- `libs/`, `apps/`, or `modules/` with their own build files

## Before generating, analyze these sources
- `CMakeLists.txt` / `meson.build` / `Makefile`
- `conanfile.*`, `vcpkg.json` (if present)
- `compile_commands.json` (if present)
- `src/`, `include/`, `tests/`, `libs/`

## Codebase scan (C/C++-specific)
- Source roots: `src/`, `include/`, `tests/`, `libs/`
- Library/app split (record only if present):
  `src/lib`, `src/app`, `src/bin`
- Namespaces and class prefixes (record only if present)
- CMake targets (record only if present):
  `add_library`, `add_executable`

## Mandatory output (C/C++ module CLAUDE.md)
Include these if detected (list actual names found):
- **Libraries**: list library targets
- **Executables**: list executable targets
- **Headers**: list public header directories
- **Modules/components**: list subdirectories with build files
- **Dependencies**: list Conan/vcpkg dependencies (if any)

## Command sources
- README/docs or CI invoking `cmake`, `ninja`, `make`, or `meson`
- Repo scripts that call build tools
- Only include commands present in repo

## Key paths to mention (only if present)
- `src/`, `include/`
- `tests/`, `libs/`
