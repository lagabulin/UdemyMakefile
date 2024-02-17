DEBUG = 1

CXX_STANDARD = c++17
CXX_WARNING = -Wall -Wextra -Wpedantic

CXX = g++
CXXFLAGS = $(CXX_WARNING) -std=$(CXX_STANDARD)
LDFLAGS = -lmath

ifeq ($(DEBUG), 1)
CXXFLAGS += -g -O0
EXECUTABLE_NAME = mainDebug
else
CXXFLAGS += -O3
EXECUTABLE_NAME = mainRelease
endif

CXX_COMPILER_CALL = $(CXX) $(CXXFLAGS)

CXX_SOURCES = $(wildcard *.cc)
CXX_OBJECTS = $(patsubst %.cc, %.o, $(CXX_SOURCES))

build: $(CXX_OBJECTS)
	$(CXX_COMPILER_CALL) main.o my_lib.o -o $(EXECUTABLE_NAME)

execute:
	./$(EXECUTABLE_NAME)

clean:
	rm -f *.o
	rm -f $(EXECUTABLE_NAME)

%.o: %.cc
	$(CXX_COMPILER_CALL) $< -c $@
