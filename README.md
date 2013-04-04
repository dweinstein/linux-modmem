linux-modmem
============
This code is a subset from Allan Cruse's Virtualization class http://www.cs.usfca.edu/~cruse/cs686s07/
but it is generally useful for hacking on Linux devices.

* Build the kernel-module-builder.

```
g++ -o mmake mmake.cpp
```

* Build the kernel module component

```
./mmake dram
```

* As root create the device node.

```
mknod /dev/dram c 85 0
chmod a+rw /dev/dram
```

* Insert the kernel module into the running system

```
insmod dram.ko
```

* Build the userspace process that will be used to look at the dram device.

```
$ g++ -o fileview fileview.cpp
```

* Run the userspace process

```
# ./fileview /dev/dram
```

