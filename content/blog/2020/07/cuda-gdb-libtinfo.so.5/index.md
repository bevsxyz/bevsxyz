---
title: cuda-gdb Error with libtinfo.so.5
summary: cuda-gdb and the ncurses saga. Fixing shared library error!
authors:
- admin
date: "2021-07-08T08:00:00+05:30"
tags:
- cuda
- ncurses
categories:
- troubleshooting
image:
  caption: 'Photo by Nong Vang on [**Unsplash**](https://unsplash.com/photos/O_Xy25Dj7Mo)'
  focal_point: "Smart"
links:
    - icon_pack: fab
      icon: dev
      name: Also on DEV
      url: 'https://dev.to/bevsxyz/cuda-gdb-error-with-libtinfo-so-5-289i'
---

I had a fresh install of cuda-tools from the Manjaro software repository and I simply couldn’t run **cuda-gdb**. I was getting the following error

```bash
cuda-gdb: error while loading shared libraries: libtinfo.so.5: cannot open shared object file: No such file or directory
```

A related error was as follows:

```bash
cuda-gdb: error while loading shared libraries: libncursesw.so.5: cannot open shared object file: No such file or directory
```

I had to investigate the files `libtinfo.so.5` and `libncursesw.so.5`. It was a simple version-conflict with ncurses. My distro had **ncurses 6.2**, whereas cuda-gdb was insisting on **ncurses 5**. A simple symlink was in order, actually two. The following two lines saved my day!

```bash
sudo ln -s /usr/lib/libncursesw.so.6.2  /usr/lib/libtinfo.so.5

sudo ln -s /usr/lib/libncursesw.so.6.2  /usr/lib/libncursesw.so.5
```

I got the necessary pointers from this [stackoverflow answer](https://stackoverflow.com/a/42686791/16394350) for an unrelated Android Studio question.
