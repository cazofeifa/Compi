# Compilacion predeterminada
COMPILER = dcc
PRODUCTS = $(COMPILER) 
default: $(PRODUCTS)

# Lista de archivos fuente
SRCS = errors.cc utility.cc main.cc

OBJS = lex.yy.o $(patsubst %.cc, %.o, $(filter %.cc,$(SRCS))) $(patsubst %.c, %.o, $(filter %.c, $(SRCS)))

# para definir los archivos intermedios basura, para hacer clean
JUNK =  *.o lex.yy.c dpp.yy.c y.tab.c y.tab.h *.core core

# Herramientas usadas en la compilacion
CC= g++
LD = g++
LEX = flex

# Apagar los warnings innecesarios
CFLAGS = -g -Wall -Wno-unused -Wno-sign-compare

# Se activa el debugging de flex
LEXFLAGS = -d

# link con las librerias de c, mate y lex, respectivamente
LIBS = -lc -lm -ll 

# Reglas para productos intermedios
.yy.o: $*.yy.c
	$(CC) $(CFLAGS) -c -o $@ $*.cc

lex.yy.c: scanner.l 
	$(LEX) $(LEXFLAGS) scanner.l

.cc.o: $*.cc
	$(CC) $(CFLAGS) -c -o $@ $*.cc

# Reglas para compilar
$(COMPILER) : $(OBJS)
	$(LD) -o $@ $(OBJS) $(LIBS)

# make depend se encarga de configurar los headers de dependencias,
# agrega la lista de dependencias al final del makefile. Si se agregan
# nuevos headers, se debe hacer make depend.
depend:
	makedepend -- $(CFLAGS) -- $(SRCS)

clean:
	rm -f $(JUNK) y.output $(PRODUCTS)

# DO NOT DELETE

errors.o: errors.h location.h /usr/include/stdio.h /usr/include/features.h
errors.o: /usr/include/bits/predefs.h /usr/include/sys/cdefs.h
errors.o: /usr/include/bits/wordsize.h /usr/include/gnu/stubs.h
errors.o: /usr/include/gnu/stubs-64.h /usr/include/bits/types.h
errors.o: /usr/include/bits/typesizes.h /usr/include/libio.h
errors.o: /usr/include/_G_config.h /usr/include/wchar.h
errors.o: /usr/include/bits/stdio_lim.h /usr/include/bits/sys_errlist.h
utility.o: utility.h /usr/include/stdlib.h /usr/include/features.h
utility.o: /usr/include/bits/predefs.h /usr/include/sys/cdefs.h
utility.o: /usr/include/bits/wordsize.h /usr/include/gnu/stubs.h
utility.o: /usr/include/gnu/stubs-64.h /usr/include/sys/types.h
utility.o: /usr/include/bits/types.h /usr/include/bits/typesizes.h
utility.o: /usr/include/time.h /usr/include/endian.h
utility.o: /usr/include/bits/endian.h /usr/include/bits/byteswap.h
utility.o: /usr/include/sys/select.h /usr/include/bits/select.h
utility.o: /usr/include/bits/sigset.h /usr/include/bits/time.h
utility.o: /usr/include/sys/sysmacros.h /usr/include/bits/pthreadtypes.h
utility.o: /usr/include/alloca.h /usr/include/stdio.h /usr/include/libio.h
utility.o: /usr/include/_G_config.h /usr/include/wchar.h
utility.o: /usr/include/bits/stdio_lim.h /usr/include/bits/sys_errlist.h
utility.o: /usr/include/string.h /usr/include/xlocale.h
main.o: /usr/include/string.h /usr/include/features.h
main.o: /usr/include/bits/predefs.h /usr/include/sys/cdefs.h
main.o: /usr/include/bits/wordsize.h /usr/include/gnu/stubs.h
main.o: /usr/include/gnu/stubs-64.h /usr/include/xlocale.h
main.o: /usr/include/stdio.h /usr/include/bits/types.h
main.o: /usr/include/bits/typesizes.h /usr/include/libio.h
main.o: /usr/include/_G_config.h /usr/include/wchar.h
main.o: /usr/include/bits/stdio_lim.h /usr/include/bits/sys_errlist.h
main.o: utility.h /usr/include/stdlib.h /usr/include/sys/types.h
main.o: /usr/include/time.h /usr/include/endian.h /usr/include/bits/endian.h
main.o: /usr/include/bits/byteswap.h /usr/include/sys/select.h
main.o: /usr/include/bits/select.h /usr/include/bits/sigset.h
main.o: /usr/include/bits/time.h /usr/include/sys/sysmacros.h
main.o: /usr/include/bits/pthreadtypes.h /usr/include/alloca.h errors.h
main.o: location.h scanner.h
