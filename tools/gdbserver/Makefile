PRG := st-util
OBJS = gdb-remote.o gdb-server.o

CFLAGS+=-g -Wall -Werror -std=gnu99
CFLAGS+=-I../libstlink/src
LDFLAGS=-L../libstlink -lstlink

# libusb location
LDFLAGS+=`pkg-config --libs libusb-1.0`
CFLAGS+=`pkg-config --cflags libusb-1.0`

all: $(PRG)

$(PRG): $(OBJS) ../libstlink/libstlink.a
	$(CC) -o $@  $^ $(LDFLAGS)

clean:
	rm -rf $(OBJS)
	rm -rf $(PRG)
	make -C ../libstlink clean


../libstlink/libstlink.a:
	make -C ../libstlink

.PHONY: clean all
