# makefile for macosx

# note: configuration for ODE build
#CFLAGS="-march=core2 -mfpmath=sse -sse3 -O3 " CXXFLAGS="-march=core2 -mfpmath=sse -sse3 -O3 " ./configure --with-trimesh=none --with-drawstuff=none

#CFLAGS="-Wall -DDEBUG" CXXFLAGS="-Wall -DDEBUG" ./configure --with-trimesh=none --with-drawstuff=none --enable-malloc

flags = -march=core2 -mfpmath=sse -sse3 -O3 -ffast-math -fno-exceptions -finline-functions -fomit-frame-pointer -fstrict-aliasing -Wstrict-aliasing=2 -Wall -DNDEBUG -lm

#flags = -Wall -DDEBUG -lm

headers := $(wildcard *.h)

ode := -lode -L../ode/lib -I../ode/include
unittest := -lUnitTest++ -L../UnitTest++ -I../UnitTest++/src
frameworks := -framework Carbon -framework OpenGL -framework AGL

all : Demo.app test

% : %.cpp makefile ${headers}
	g++ $< -o $@ ${flags} ${ode} ${frameworks}

UnitTest : UnitTest.cpp makefile ${headers}
	g++ UnitTest.cpp -o UnitTest -Wall -DDEBUG -lm ${unittest} ${ode}

test : UnitTest
	./UnitTest

demo : Demo test
	./Demo

demo_app : Demo.app test
	open Demo.app --wait-apps

Demo.app : Demo
	rm -rf $<.app
	mkdir $<.app
	mkdir $<.app/Contents
	mkdir $<.app/Contents/MacOS
	cp $< $<.app/Contents/MacOS/

.PHONY:	demo_app
.PHONY: demo
.PHONY:	test

clean:
	rm -f UnitTest
	rm -f Demo
	rm -rf *.app
	rm -f *.a
