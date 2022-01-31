---
title: pkg-config
date: 2022-01-11
---

# pkg-config
[[pkg-config]] is a tool that return meta-information about installed packages

## Usage
To get [[compiler]] flags

```bash
pkg-config --cflags <lib>
```

To get [[linker]] flags 
```bash
pkg-config --libs <lib>
```

Note that you can use the flags at the same time if you are compiling and linking in the same step

Also with the use of back ticks this can be imbedded directly into a compile command

Here is an example to compile with [[SDL2]]

```bash
gcc main.c `pkg-config --cflags --libs sdl2`
```