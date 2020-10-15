COMPILE_OPTIONS = -O3 -fno-strict-aliasing
# -Wall -Wno-unused-value -Wno-unused-local-typedefs -Wno-misleading-indentation
LINKER_OPTIONS = -pthread

OBJECTS = crunch.o corpus_gen.o corpus_test.o

all: ../bin/crunch

%.o: %.cpp
	$(CXX) $< -o $@ -c -I../inc -I../crnlib $(COMPILE_OPTIONS)

../bin/crunch: ../lib/libcrunch.a $(OBJECTS)
	if [ ! -d ../bin ]; then mkdir ../bin; fi
	$(CXX) $(OBJECTS) -o ../bin/crunch ../lib/libcrunch.a $(LINKER_OPTIONS)

clean:
	@rm -f $(OBJECTS)
