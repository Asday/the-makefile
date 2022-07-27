# The Makefile

C++ project makefile with incremental compilation, support for multiple build configurations, and multiple output executables.

# Usage

For each executable required, create one `.cpp` file in [`src/cmd/`](src/cmd/), a starter [`main.cpp`](src/cmd/main.cpp) is provided.

Modify [`config`](config) to suit the requirements.

Run `make {cmd}` to compile, link, and run the named command with the default build config.

Run `make all` to compile and link all commands with all build configs.

Run `make all-{config}` to compile and link all commands with the specified build config.

Run `make clean` to nuke the build folder.

# Limitations

ALL object files are passed to the linker regardless of dependency, so keep an eye out for ODR violations.

# Directories and files

|Path|Description|
|-|-|
|`build/`|Houses all build artefacts.|
|`build/{config}/`|One directory per config listed in `config.configs`, under which all build artefacts for the given config live.|
|`build/{config}/bin/`|Compiled and linked executables.|
|`build/{config}/d/`|Include information emitted by the preprocessor, matching the directory layout of `src/`, used for incremental recompilation when a dependency changes.|
|`build/{config}/o/`|Compiled object files, matching the directory layout of `src/`.|
|[`src/`](src/)||
|[`.gitignore`](.gitignore)|Base gitignore for C++ projects, containing no useless nonsense.  The idea is to use `.git/info/exclude`|
|[`config`](config)|The user-configurable part of the makefile, useful for defining configs such as debug/release, and the switches therefor.|
|[`makefile`](makefile)|The Makefile.|
