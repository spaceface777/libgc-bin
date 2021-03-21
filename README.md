# libgc-bin

Prebuilt static libgc binaries - for use in the V programming language

All currently available platforms are listed under the branches on this repo. Any missing platform
has not been precompiled yet; PRs are welcome if you get a working binary for a new patform.

### Build instructions

the general idea is the following:
```sh
git clone --depth 1 https://github.com/ivmai/bdwgc
cd bdwgc
gcc -Iinclude -O3 -flto -c *.c
gcc-ar -rcs ../libgc.a *.o
cd ..
rm -rf bdwgc
```
NB: some platforms may require slightly different build commands and/or compiler flags.

If you want to cross-compile to a new architecture: 
1. create a new, `--orphan` branch from any existing branch (apart from `main`)
1. edit the readme as needed
1. compile the .a file (please try to keep the steps as similar to those above as possible)
1. if any compilation flags/commands apart from those above were required, add them to the readme
1. `git push` and open a PR :)
