# Makefile for demo programs for Lecture 7
# Graphs 
# We also need a queue for this lecture

ifeq ($(OSTYPE),WINDOWS)
	EXECEXT =.exe
	COMP	=__MINGCC__
	PLATFORM	=mingw
else
	EXECEXT =
	COMP	=__GCC__
	PLATFORM	=linux
endif

EXECUTABLES= graphTester$(EXECEXT) queueTesterL$(EXECEXT) 

all : $(EXECUTABLES)

linkedListQueue.o :	linkedListQueue.c abstractQueue.h
	gcc -c linkedListQueue.c

queueTester.o :	queueTester.c abstractQueue.h
	gcc -c queueTester.c

linkedListGraph.o :	linkedListGraph.c abstractGraph.h abstractQueue.h
	gcc -c linkedListGraph.c

graphTester.o :	graphTester.c abstractGraph.h
	gcc -c graphTester.c


# queueTester using the linkedListQueue implementation of the abstract queue
queueTesterL$(EXECEXT) : queueTester.o linkedListQueue.o
	gcc -o queueTesterL$(EXECEXT) queueTester.o linkedListQueue.o

graphTester$(EXECEXT) : graphTester.o linkedListGraph.o linkedListQueue.o
	gcc -o graphTester$(EXECEXT) graphTester.o linkedListGraph.o linkedListQueue.o


clean : 
	-rm *.o
	-rm $(EXECUTABLES) 
