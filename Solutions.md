# Solutions

## Lab00

+ `readelf`
+ `dd if=./hello_world.elf of=./hello_world.data bs=1 skip=$((0x2000)) count=$((0x11))`
+ `hexdump -C`
+ `objdump -d -M intel`

## Lab 01

see `Makefile`

## Lab 02

see `Makefile` and `basic_operator.c`

## Lab 03

see `Makefile`

## Lab 04

```
(gdb) b 'RBTree<int>::remove(int)'
(gdb) disassemble 'RBTree<int>::remove(int)'
(gdb) set $rip=0x000055555555589a
(gdb) c
```
