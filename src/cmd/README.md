# `src/cmd/`

All `.cpp` files in this directory can be compiled by The Makefile to executables with `make {cmd}` where `{cmd}` is the filename without the extension.

Keep the command sources small and refactor any and all behaviour outside of taking user input to [`src/`](..).
