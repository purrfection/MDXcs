all: logappend logread

CFLAGS=-g -Wall -std=gnu99
LFLAGS=-lcrypto

UNAME := $(shell uname)
ifeq ($(UNAME),Linux)
CFLAGS += -DLINUX -I/usr/local/ssl/include -L/usr/local/ssl/lib
endif

logappend: logappend.o
	$(CC) -o $@ $(CFLAGS) $^ $(LIBS) $(LFLAGS)

logread: logread.o 
	$(CC) -o $@ $(CFLAGS) $^ $(LIBS) $(LFLAGS)

logappend.o: logappend.c
	$(CC) -c -o $@ $(CFLAGS) $^ 

logread.o: logread.c
	$(CC) -c -o $@ $(CFLAGS) $^ 

clean:
	rm -f *.o logappend logread
