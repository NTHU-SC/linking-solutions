# Solutions

## Lab00

+ `readelf`
+ `dd if=./hello_world.elf of=./hello_world.data bs=1 skip=$((0x2000)) count=$((0x11))`
+ `hexdump -C`
+ `objdump -d -M intel`

## Lab 01

```
CC = gcc
CCFLAGS = -Wall -O2
LDFLAGS = -lm 

.PHONY = all clean

all: super_calculator

super_calculator: super_calculator.o tinyexpr.o basic_operator.o 
	$(CC) $(CCFLAGS) -o $@ $^ $(LFLAGS) 

%.o:%.c
	$(CC) -c $(CCFLAGS) $^ -o $@

clean:
	rm -f *.o super_calculator
```

## Lab 02

```
CC = gcc
CCFLAGS = -Wall -Wshadow -O2
LDFLAGS = -lm -lstdc++ -lgfortran -pthread

.PHONY = all clean

all: super_calculator

my_sub.a: my_sub.go
	go build -buildmode=c-archive -o my_sub.a my_sub.go

my_sum.o: my_sum.f90
	gfortran -c my_sum.f90

my_divide.o: my_divide.cpp
	g++ -c my_divide.cpp

basic_operator.o: basic_operator.c my_sub.a

super_calculator: super_calculator.o tinyexpr.o basic_operator.o my_sub.a my_sum.o my_divide.o

.c.o:

clean:
	rm -f *.o *.a my_sub.h super_calculator 
```

