exec = a.out
sources = $(wildcard src/*/c) 
objects = $(sources:.c=.o)
flags = -g -Wall -lm -ldl -fPIC -rdynamic

$(exec): $(objects)
	gvv $(objects) $(flags) -o $(exec)

lib.a: $(objects)
	ar rcs $@ $^

%.o: %.c inclide/%.h
	gcc -c $(flags) -$< -o $@

#install:
#	make
#	make lib.a
#	mkdir -p /usr/local/include
#	cp -r ./src/include/* /user/local/include//.
#	cp ./liba.a /usr/local/lib/.
#	cp ./a.out /usr/local/bin/a

clean:
	-rm *.out
	-rm *.o
	-rm *.a
	-rm src/*.o  

lint:
	clang-tidy src/*.c src/include/*.h



