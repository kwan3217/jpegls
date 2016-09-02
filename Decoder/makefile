CC=gcc

LNKFLAGS = -lm

SRCS = global.c jpegmark.c initialize.c decoder.c lossless_d.c lossy_d.c bitio.c melcode.c 
INCL = global.h jpegmark.h bitio.h

EOBJS = global.o jpegmark.o initialize.o decoder.o lossless_d.o lossy_d.o bitio.o melcode.o

all: $(EOBJS)

jpegmark.o: jpegmark.c jpegmark.h bitio.h global.h

global.o: global.h global.c

initialize.o: initialize.c bitio.h global.h

lossless_d.o: global.h lossless_d.c bitio.h 

lossy_d.o: global.h lossy_d.c bitio.h

decoder.o: decoder.c jpegmark.c global.h 

bitio.o: bitio.c bitio.h global.h

melcode.o: melcode.c bitio.h global.h


$(DECODER): $(EOBJS)
	$(CC) $(CFLAGS) -o $@ $(EOBJS) $(LNKFLAGS)

lint:
	lint $(SRCS)
clean:
	-rm -f *.o core loco* *.out
