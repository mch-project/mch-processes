## MCH Processes

This `mch-processes` code repository could be used to collaborate on developing an initial prototype of a shared object (`.so`) library that would allow software developed in other languages (e.g. Python) to run MCH's Pascal/C functions.

An initial proof-of-concept may look something like this...


1. Pascal and C source code available in the current repository with the following structure:
    1. `src` directiory

        A directory containing C and Pascal functions

    2. `tests` directory - <kbd>optional</kbd>

        Unit tests that can run using just the original Pascal/C code in the repository's `src` directory. The directory would contain a small amount of sample data if this is required to run the tests

        GitHub can automatically run these tests each time new code is merged into the code repository to check that everything is still working as expected.
        
    3.  `LICENSE`

        Update the `LICENSE` file with a suitable open-source licence

    4.  `/`
        
        Build script(s) or `Makefile` for building shared object libraries.

2. Docstrings (machine readable comments)

	If the docstrings describing the Pascal/C functions are written using the Doxygen style then it should be easier to create automatically generated documentation in other environments (e.g. Python)

3. Library files

	The Linux version of a Window's Dynamic Linked Library (`DLL`) is called a Shared Object (`.so`). It should be possible to use both C and Pascal functions from other environments (e.g. Python) if the MCH processes library exports its functions with C calling conventions.

	Shared objects (`.so` files) can often be used on multiple Linux distributions as long they use the same version of the C compiler, however to avoid problems we should agree which distro and version to target (in OpenCDMS we have been using versions of Debian/Ubuntu).
  
	In GitHub we can create a version release (e.g. version 0.1.0) of the `mch-processes` library. When we create a release, we can attach the binary shared library files to the release which will allow us to not store these binary files in the code repository itself.
