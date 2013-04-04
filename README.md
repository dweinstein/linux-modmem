linux-modmem
============
This code is a subset from Allan Cruse's Virtualization class http://www.cs.usfca.edu/~cruse/cs686s07/
but it is generally useful for hacking on Linux devices.

* Build the kernel-module-builder.
```bash
$ g++ -o mmake mmake.cpp
```
* Build the kernel module component
```bash
$ ./mmake dram
```

```bash
# mknod /dev/dram c 85 0
# chmod a+rw /dev/dram
```

* Insert the kenrel module into the running system
```bash
# insmod dram.ko
```

* Build the userspace process that will be used to look at the dram device.
```bash
$ g++ -o fileview fileview.cpp
```

* Run the userspace process
```bash
# ./fileview /dev/dram
```
