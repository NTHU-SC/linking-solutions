CC = gcc
CCFLAGS = -Wall -Wshadow -O2 
LDFLAGS = -lm -Wl,-rpath='$$ORIGIN' 

.PHONY = all clean

all: super_calculator fake_operator.so

basic_operator.so: basic_operator.c basic_operator.h
fake_operator.so: fake_operator.c 
%.so:
	$(CC) $(CCFLAGS) $^ -shared -o $@

super_calculator: super_calculator.o tinyexpr.o basic_operator.so 

.c.o:

clean:
	rm -f *.o *.so super_calculator 
