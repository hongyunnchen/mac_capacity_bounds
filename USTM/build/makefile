

ROOT = ..
SRC = $(ROOT)/src
INC = $(ROOT)/include

# ITPP values
CFLAGS += `pkg-config --cflags itpp`
LDFLAGS += `pkg-config --libs itpp` -lpthread

# GSL values
CFLAGS += `pkg-config --cflags gsl`
LDFLAGS +=  `pkg-config --libs gsl`

#BOOST values
#CFLAGS += -I<PATH/TO/BOOST/include>
#LDFLAGS += -L<PATH/TO/BOOST/lib>
LDFLAGS += -lboost_thread -lboost_program_options -lboost_system -lboost_date_time


#Code values
CFLAGS += -I$(INC) 

all : run

run : main.o MutualInformation.o
	g++ main.o MutualInformation.o -o run $(LDFLAGS)

MutualInformation.o : $(SRC)/MutualInformation.cpp $(INC)/MutualInformation.h
	g++ $(CFLAGS) -c $(SRC)/MutualInformation.cpp 

main.o : $(SRC)/main.cpp $(INC)/MutualInformation.h
	g++ $(CFLAGS) -c $(SRC)/main.cpp  

clean :
	rm -rf *.o run debug 
