# GNU Make Note

## Get the binary with the same name as the source file
```makefile
EXES += $(basename $(shell ls *.c))

%: %.c
	gcc $< -o $@

all: $(EXES)

clean: rm $(EXES)

.PHONY: all clean
```