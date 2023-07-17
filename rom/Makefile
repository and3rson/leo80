TARGETS = $(patsubst %.z80,%.bin,$(wildcard *.z80))

.PHONY: all
all: $(TARGETS)

%.bin: %.z80
	sjasmplus $< --syntax=abfw --raw=$@

.PHONY: run
run: inc.bin
	z80e-sdl inc.bin --no-rom-check --debug --print-state
