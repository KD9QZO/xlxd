#
# Makefile
#

CC  := gcc
CXX := g++


CFLAGS   := -c -std=gnu11 -pthread
CXXFLAGS := -c -std=gnu++14 -pthread
LDFLAGS  := -std=gnu++14 -pthread


SOURCES = $(wildcard *.cpp)

OBJECTS = $(SOURCES:.cpp=.o)

EXECUTABLE = xlxd



all: $(SOURCES) $(EXECUTABLE)

$(EXECUTABLE): $(OBJECTS)
	$(CXX) $(LDFLAGS) $(OBJECTS) -o $@

.cpp.o:
	$(CXX) $(CXXFLAGS) $< -o $@

clean:
	$(RM) $(EXECUTABLE) *.o

install:
	mkdir -p /xlxd
	cp -f $(EXECUTABLE) /xlxd/
	[ -f /xlxd/xlxd.blacklist ] && cp ../config/xlxd.blacklist /xlxd/xlxd.blacklist.sample || cp ../config/xlxd.blacklist /xlxd/xlxd.blacklist
	[ -f /xlxd/xlxd.whitelist ] && cp ../config/xlxd.whitelist /xlxd/xlxd.whitelist.sample || cp ../config/xlxd.whitelist /xlxd/xlxd.whitelist
	[ -f /xlxd/xlxd.interlink ] && cp ../config/xlxd.interlink /xlxd/xlxd.interlink.sample || cp ../config/xlxd.interlink /xlxd/xlxd.interlink
	[ -f /xlxd/xlxd.terminal ] && cp ../config/xlxd.terminal /xlxd/xlxd.terminal.sample || cp ../config/xlxd.terminal /xlxd/xlxd.terminal
