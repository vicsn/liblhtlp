INCLUDE := ../include
LIBS := ../lib
EXT_LIBS := -llhp -lgmp -lssl -lcrypto  #-lpbc 

CC=gcc
CFLAGS=-I ${INCLUDE} -L ${LIBS} ${EXT_LIBS} -g

.PHONY: test

./%.o: %.c
	@$(CC) $^ -o $@ $(CFLAGS)

./%.test: %.o
	@echo "-----------------------------"
	@echo "Running `basename $^ .o` Test"
	@echo "-----------------------------"
	@./$^
	@echo "============================="

test: code.test \
	timecode.test \
	batch.test \
	seeded.test

build: code.o \
	timecode.o \
	batch.o \
	seeded.o

