TARGET = librlclient.a
ARFLAGS = rcs 

INCLUDE = -I ../include

.PHONY: default all clean

default: $(TARGET)
all: default

things: all

SOURCES = $(filter-out mail.cc, $(wildcard *.cc)) $(filter-out model_mgmt.cc, $(wildcard */*.cc))
OBJECTS = $(patsubst %.cc, %.o, $(SOURCES))
HEADERS = $(wildcard *.h)

%.o: %.cc $(HEADERS)
	$(CXX) $(FLAGS) $(INCLUDE) -c $< -o $@

.PRECIOUS: $(TARGET) $(OBJECTS)

$(TARGET): $(OBJECTS)
	ar $(ARFLAGS) $@ $(OBJECTS) 

clean:
	-rm -f *.o
	-rm -f $(TARGET)