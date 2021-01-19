CC = gcc
CCFLAGS = -Wall -Wshadow -O2 -g
LDFLAGS = -lm 

.PHONY = all clean

all: super_calculator

super_calculator: super_calculator.o tinyexpr.o basic_operator.o 
	$(CC) $(CCFLAGS) -o $@ $^ $(LDFLAGS) 

.c.o:
	$(CC) -c $(CCFLAGS) $< -o $@

clean:
	rm -f *.o super_calculator 
