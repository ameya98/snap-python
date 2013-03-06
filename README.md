snap-python
===========

SNAP Python code, SWIG related files

SWIG Installation
-----------------

### Mac OS X
swig-1.3.12 and later support OS-X/Darwin. Simply download the Unix sources, configure, and build from the command terminal. This has been tested on 10.8.2.  Adopted from [ColourBlomb](http://blog.colourbomb.net/?p=49).

1. Download the Unix source from swig.org/download.html.

2. Moving to the terminal, extract the files from the tarball and move to the root directory of the SWIG install:

		cd /Developer/SWIG
		tar -xf swig-2.0.4.tar.gz
		cd swig-2.0.4

3. Run `./configure`.  This will produce an error if you don't have the PCRE (Perl Compatible Regular Expressions) library package installed. 
This dependency is needed for configure to complete. Either:
	- Install the PCRE developer package on your system (preferred approach).
	- Download the PCRE source tarball, build and install on your system
	as you would for any package built from source distribution.
	- Use the `Tools/pcre-build.sh` script to build PCRE just for SWIG to statically
	link against. Run `Tools/pcre-build.sh –help` for instructions.
	(quite easy and does not require privileges to install PCRE on your system)
	- Cconfigure using the `–without-pcre` option to disable regular expressions support in SWIG
	(not recommended).
	See `config.log` for more details.
		
			make
			sudo make install

4. PCRE should now have successfully installed so move to the swig install directory and try `./configure` again:

		cd ../swig-2.0.4
		./configure

	This time no errors are thrown so try and install:

		make
		sudo make install

5. Once this has completed test that SWIG has installed correctly, type `swig` into the terminal and hopefully you’ll get the response:
  Must specify an input file. Use `-help` for available options.

