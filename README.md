# Personal Shell

This is a custom shell written in C that I intend to build on. Big shout-out to
[Stephen Brennan][] for his help getting this project kick-started and getting
me back into the groove of OS-level programming.

## Running the Shell

The shell runs in an emulated mode where memory is accessed through a file. If
the emulation mode still makes you nervous, you can run the program from a
container.

### Building

The project uses [Zig](https://ziglang.org/) as the build system to compile the
C sources. With Zig installed, build the binary with:

```sh
zig build
```

The compiled binary is placed at `zig-out/bin/lsh`.

### Running

The shell requires two arguments: a disk image filename and a block count:

```sh
./zig-out/bin/lsh <diskfile> <nblocks>
```

For example, to open (or create) a disk image named `store` with 2000 blocks:

```sh
./zig-out/bin/lsh store 2000
```

### Running in a Container

To run inside Docker instead:

```sh
docker build -t lsh .
docker run -it lsh
```

[Stephen Brennan]: https://brennan.io/2015/01/16/write-a-shell-in-c/
