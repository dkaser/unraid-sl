![GitHub Downloads (all assets, all releases)](https://img.shields.io/github/downloads/dkaser/unraid-sl/total)
![GitHub Downloads (all assets, latest release)](https://img.shields.io/github/downloads/dkaser/unraid-sl/latest/total)

# Build Instructions

1. Download https://github.com/mtoyoda/sl
2. Download ncurses: https://ftp.gnu.org/pub/gnu/ncurses/ncurses-6.2.tar.gz
3. Create a static build of ncurses:
   
   ./configure --prefix=$PWD CC=musl-gcc
   make -kj$(nproc)

4. Copy the resulting include/ and lib/ folders to the sl folder.
5. Build sl:

   musl-gcc -s -static -Llib/ -Iinclude/ sl.c -lncurses
