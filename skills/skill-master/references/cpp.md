# C/C++

## Detection signals
- `CMakeLists.txt`
- `Makefile`, `makefile`
- `*.cpp`, `*.c`, `*.h`, `*.hpp`
- `conanfile.txt`, `conanfile.py` (Conan)
- `vcpkg.json` (vcpkg)

## Multi-module signals
- Multiple `CMakeLists.txt` with `add_subdirectory`
- Multiple `Makefile` in subdirs
- `lib/`, `src/`, `modules/` directories

## Pre-generation sources
- `CMakeLists.txt` (dependencies, targets)
- `conanfile.*` (dependencies)
- `vcpkg.json` (dependencies)
- `Makefile` (build targets)

## Codebase scan patterns

### Source roots
- `src/`, `lib/`, `include/`

### Layer/folder patterns (record if present)
`core/`, `utils/`, `network/`, `storage/`, `ui/`, `tests/`

### Pattern indicators

| Pattern | Detection Criteria | Skill Name |
|---------|-------------------|------------|
| Class | `class *`, `public:`, `private:` | cpp-class |
| Header | `*.h`, `*.hpp`, `#pragma once` | header-file |
| Template | `template<`, `typename T` | cpp-template |
| Smart Pointer | `std::unique_ptr`, `std::shared_ptr` | smart-pointer |
| RAII | destructor pattern, `~*()` | raii-pattern |
| Singleton | `static *& instance()` | singleton |
| Factory | `create*()`, `make*()` | factory-pattern |
| Observer | `subscribe`, `notify`, callback pattern | observer-pattern |
| Thread | `std::thread`, `std::async`, `pthread` | threading |
| Mutex | `std::mutex`, `std::lock_guard` | synchronization |
| Network | `socket`, `asio::`, `boost::asio` | network-cpp |
| Serialization | `nlohmann::json`, `protobuf` | serialization |
| Unit Test | `TEST(`, `TEST_F(`, `gtest` | gtest |
| Catch2 Test | `TEST_CASE(`, `REQUIRE(` | catch2-test |

## Mandatory output sections

Include if detected:
- **Core modules**: main functionality
- **Libraries**: internal libraries
- **Headers**: public API
- **Tests**: test organization
- **Build targets**: executables, libraries

## Command sources
- `CMakeLists.txt` custom targets
- `Makefile` targets
- README/docs, CI
- Common: `cmake`, `make`, `ctest`
- Only include commands present in repo

## Key paths
- `src/`, `include/`
- `lib/`, `libs/`
- `tests/`, `test/`
- `build/` (out-of-source)
