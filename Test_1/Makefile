# -----------
# Flags
# -----------
# Compiler, Compilation and Linker options

CC      := gcc
CFLAGS  := -W -Wall
LDFLAGS :=


# Build variables

TARGETS := helloworld
OBJ     := helloworld.o main.o
DEPS    := helloworld.h

# .PHONY means they don't refer to real files but are things we want make to do

.PHONY: all clean


# -----------
# Makefile :
# -----------

all: $(TARGETS)

clean:
	rm -f $(TARGETS) $(OBJ)
	
$(OBJ): %.o : %.c $(DEPS)
	$(CC) -c -o $@ $< $(CCFLAGS)

$(TARGETS): % : $(filter-out $(MAINS), $(OBJ)) %.o
	$(CC) -o $@ $(LIBS) $^ $(CCFLAGS) $(LDFLAGS)


#    $@ is a macro that refers to the target
#    $< is a macro that refers to the first dependency
#    $^ is a macro that refers to all dependencies
#    % is a macro to make a pattern that we want to watch in both the target and the dependency

