RM=rm -f

SRCS=sfun_main.cpp manager.cpp
OBJS=$(subst .cpp,.o,$(SRCS))

MEXSUFFIX=mexa64
MATLABHOME=/opt/MATLAB/R2014a
MEX=mex
CXX=g++
CFLAGS=-fPIC -ansi -pthread -DMX_COMPAT_32 -DMATLAB_MEX_FILE -std=c++11
LIBS=-lm
INCLUDE=-I$(MATLABHOME)/simulink/include -I$(MATLABHOME)/extern/include
MEXFLAGS=-cxx CC='$(CXX)' CXX='$(CXX)' LD='$(CXX)'

all: build link

link: $(OBJS)
	$(MEX) $(MEXFLAGS) $(LIBS) $^ -output tx

build: $(SRCS)
	$(CXX) $(CFLAGS) $(INCLUDE) -c $^

clean:
	$(RM) $(OBJS) 

distclean: clean
	$(RM) *.$(MEXSUFFIX)

# vim: tabstop=3
