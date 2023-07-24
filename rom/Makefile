TARGETS = $(patsubst %.z80,%.bin,$(wildcard *.z80))

.PHONY: all
all: $(TARGETS)

%.bin: %.z80
	sjasmplus $< --syntax=abfw --raw=$@
	truncate -s 4096 $@

.PHONY: run
run: inc.bin
	z80e-sdl main.bin --no-rom-check --debug --print-state

program:
	minipro -p W27C512@DIP28 -w main.bin -S
