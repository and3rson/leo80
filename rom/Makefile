TARGETS = $(patsubst src/%.z80,bin/%.bin,$(wildcard src/*.z80))
MAIN = bin/main.bin

.PHONY: all
all: bin $(TARGETS)

bin:
	mkdir -p bin

bin/%.bin: src/%.z80
	sjasmplus $< --syntax=abfw --raw=$@
	# truncate -s 4096 $@

.PHONY: clean
clean:
	rm -f bin/*.bin

.PHONY: run
run: $(MAIN)
	z80e-sdl $(MAIN) --no-rom-check --debug --print-state

.PHONY: program
program: $(MAIN)
	minipro -p W27C512@DIP28 -w $(MAIN) -S

.PHONY: disasm
disasm: $(MAIN)
	z80dasm $(MAIN) -g 0 -l -a

