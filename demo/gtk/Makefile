cflag = -w

gtk2_src = $(wildcard gtk2_*.c)
gtk2_target = $(patsubst %.c, %.run, $(gtk2_src))

gtk3_src = $(wildcard gtk3_*.c)
gtk3_target = $(patsubst %.c, %.run, $(gtk3_src))

gtk4_src = $(wildcard gtk4_*.c)
gtk4_target = $(patsubst %.c, %.run, $(gtk4_src))

all:$(gtk3_target) $(gtk2_target) $(gtk4_target)

gtk2: $(gtk2_target)

gtk3:$(gtk3_target)

gtk4:$(gtk4_target)

gtk2_%.run:gtk2_%.c
	cc -o $@ $^ $(cflag) `pkg-config --cflags gtk+-2.0 --libs gtk+-2.0`

gtk3_%.run:gtk3_%.c
	cc -o $@ $^ $(cflag) `pkg-config --cflags gtk+-3.0 --libs gtk+-3.0`

gtk4_%.run:gtk4_%.c
	cc -o $@ $^ $(cflag) `pkg-config --cflags gtk4 --libs gtk4`

.PHONY:clean all

clean:
	@rm -fr *.run
