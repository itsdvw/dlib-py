dlib-py
=======
This project is ultimately intended to provide python bindings for the c++ library dlib. Currently only an RVM module has been implemented (that's what I'm interested in). This has been done in a mixture of C++ and Python due to the heavy use of templates in the dlib C++ Library. In future, I'll look for ways to compile directly to a more Pythonic module without needing any Python code.
 
Needs local copies of Boost::Python and dlib

Installation
------------
1.	Once everything is installed, copy the .sample file and remove the .sample extension.
2.	Make sure all the "/path/to" directories point to the respective Boost and dlib libraries. 
3.	Type "bjam" on the command line.

Notes
-----
There are some strange programming hacks. I hope to create a list here for future inspection:
*	When depickling functions, I try each possible function and return the successful one. Otherwise I throw an exception. In future I should implement proper pickling and depickling to make the module more Pythonic
*	Not all bindings could be declared in the helper functions. For example, declaring the train function of the trainers, results in a syntax error in a helper function, but will work in the main function. Thus I do as much as possible in the helper functions, but some things are still done in the main function.
*	There are still some warnings when compiling the bindings.
*	There's probably some more strange stuff that I did but can't remember at the moment.

Of course, the code should be properly documented too.