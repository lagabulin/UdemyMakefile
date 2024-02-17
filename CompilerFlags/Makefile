DEBUG = 1
EXECUTABLE_NAME = main

CXX_STANDARD = c++17
CXX_WARNING = -Wall -Wextra -Wpedantic

CXX = g++
CXXFLAGS = $(CXX_WARNING) -std=$(CXX_STANDARD)
LDFLAGS = -lmath

ifeq ($(DEBUG), 1)
CXXFLAGS += -g -O0
else
CXXFLAGS += -O3
endif

COMPILER_CALL = $(CXX) $(CXXFLAGS)

build: my_lib.o main.o
	$(COMPILER_CALL) main.o my_lib.o -o $(EXECUTABLE_NAME)

main.o:
	$(COMPILER_CALL) main.cc -c main.o

my_lib.o:
	$(COMPILER_CALL) my_lib.cc -c my_lib.o

execute:
	./main

clean:
	rm -f *.o
	rm -f main
