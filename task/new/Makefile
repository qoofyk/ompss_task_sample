PROGRAM=jacobi

TARGETS=$(PROGRAM)-p $(PROGRAM)-i $(PROGRAM)-d

JOB_SCHED_VERSION=-smp

#BASE_DIR=../..
#include $(BASE_DIR)/common-files/Makefile

CC = mcxx

CFLAGS = --ompss
CFLAGS_P =
CFLAGS_I = --instrument
CFLAGS_D = --debug

LIBS  = 
INCS  = 

EXTRA = -std=c++11 -O3 -Wall -Wno-unused -mcmodel=large 

$(PROGRAM)-p: $(PROGRAM).cc
	$(CC) $(GFLAGS) $(CFLAGS) $(CFLAGS_P) $(EXTRA) $(INCS) -o $@ $< $(LIBS)

$(PROGRAM)-i: $(PROGRAM).cc
	$(CC) $(GFLAGS) $(CFLAGS) $(CFLAGS_I) $(EXTRA) $(INCS) -o $@ $< $(LIBS)

$(PROGRAM)-d: $(PROGRAM).cc
	$(CC) $(GFLAGS) $(CFLAGS) $(CFLAGS_D) $(EXTRA) $(INCS) -o $@ $< $(LIBS)

clean:
	rm -f $(CC)_* *.o *~ $(TARGETS) 

