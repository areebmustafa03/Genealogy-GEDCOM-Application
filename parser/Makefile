CC=gcc
CFLAGS= -std=c11 -Iinclude

#UNAME Shell Variable
UNAME_S := $(shell uname -s)

# OS X Dependant Variables
ifeq ($(UNAME_S), Darwin)
    LIB := sharedLib.dylib
# GNU/Linux Depedant Variables
else ifeq ($(UNAME_S), Linux)
    LIB := ../sharedLib.so
endif

$(LIB): sharedLib.o
	$(CC) -shared -o $(LIB) LinkedListAPI.o GEDCOMparser.o GEDCOMutilities.o

sharedLib.o: src/LinkedListAPI.c src/GEDCOMparser.c src/GEDCOMutilities.c
	$(CC) $(CFLAGS) -c -fpic src/LinkedListAPI.c src/GEDCOMparser.c src/GEDCOMutilities.c

clean:
	rm $(LIB) *.o
