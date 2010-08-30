Fiedler's Cubes
===============

This project contains source code and instructions for building [Fiedler's Cubes](http://gafferongames.com/2010/03/11/gdc-2010-networked-physics-slides-demo/),
which is [Glenn Fiedler's](http://gafferongames.com/) demo for his GDC 2010 talk about networked physics.

Along with the source code for the demo, provided by Glenn, I've added sources for [Ode Engine](http://www.ode.org/) 1.11
and [UnitTest++](http://unittest-cpp.sourceforge.net/) 1.4. I have also added pre-compiled binaries for both of these libraries
on MacOS X 10.6.4 (Snow Leopard).

Building on Snow Leopard
------------------------

So, here's how to build Fiedler's Cubes, ODE and UnitTest++ from source on MacOS X 10.6.4:

If you just want to build the demo, you can simply clone this repo and run make:

	git clone git://github.com/malvim/fiedlerscubes.git
	cd fiedlerscubes/src
	make

This should build the Demo, create Demo.app and run all the tests. Then, you can just

	open Demo.app

and the demo will run. Press cmd-q to quit, as usual.

Now, if you want to build ode, there are a few more steps, detailed below. You'll run autogen.sh, configure and make.
Flags for make were gotten from Glenn's own makefile. We use a prefix to set directories for ode's libs and headers in 
&lt;repo-root&gt;/ode.

	(from the root of the git repo:)
	cd ode/ode-0.11.1/
	./autogen.sh
	CFLAGS="-march=core2 -mfpmath=sse -sse3 -O3 " CXXFLAGS="-march=core2 -mfpmath=sse -sse3 -O3 " ./configure --with-trimesh=none --with-drawstuff=none --prefix=`pwd`/..
	make install

Now you have libs and headers in &lt;repo-root&gt;/ode/lib and &lt;repo-root&gt;/ode/include, respectively. Time to build
UnitTest++, so we can run Glenn's unit tests:

	(from the root of the git repo:)
	cd UnitTest++
	make

And that's it! You should now be able to build the demo again, with your brand-new binaries and includes.

Cheers!
