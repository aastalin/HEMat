###############################################################
#
#  Choose C++ compiler, compiler flags
#
###############################################################

PREFIX = $(HOME)
CC = g++
AR = ar
CFLAGS= -g -O2 -std=c++11 -pthread -fPIC

INCS = -I./ -I../../HEAAN/HEAAN/src
LIBS = -L./ -L../../HEAAN/HEAAN/lib -lntl -lm -lgmp -lHEMat -lHEAAN


###############################################################
#
#  Files
#
###############################################################

HEADER = matrix.h  HEmatrix.h TestHEmatrix.h

SRC = $(HEADER:.h=.cpp)

OBJ= $(SRC:.cpp=.o)


###############################################################
#
#  Library
#
###############################################################
all: libHEMat.so

clean:
	rm *.o libHEMat.so  || echo nothing to clean

new:
	make clean
	make all

###############################################################
#
#  Test
#
###############################################################

test:
	g++ main.cpp -o foo $(CFLAGS) $(INCS) $(LIBS)


obj: $(OBJ)


%.o: %.cpp $(HEADER)
	 $(CC) $(CFLAGS) -c $(INCS) $<

libHEMat.so: $(OBJ)
	gcc -shared -o libHEMat.so $(OBJ)
	rm *.o
