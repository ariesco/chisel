Chisel: A Maude slicer parameterized by the semantics
=====================================================

Chisel is a slicing tool for any programming language whose semantics has previously
been defined in Maude. The user is in charge of indicating the sorts for side effects
and for context updates; once this information is loaded Chisel can:
* Infer the dataflow information of the instructions producing side effects.
* Perform intraprocedural slicing in a given program for a given set of variables of interest.
* Perform interprocedural slicing in a given program, which can use functions defined
separately, and given set of variables of interest.

The current limitations of Chisel are:
* No pointers/arrays can be used in programs.
* No parallelism is supported.

Getting the tool
----------------

The code of 'Chisel' is contained in a GIT repository on GitHub, whose URL is
https://github.com/ariesco/chisel. To get a copy of the repository you only
have to write in your Linux/MacOS console:

    $ git clone https://github.com/ariesco/chisel

This will create a chisel folder containing the source code of the tool as well as
several examples.

Using the tool
--------------

Chisel is a Full Maude tool and hence it can be loaded into any system that has Maude
and Full Maude installed. Just start a Maude process and type:

    $ load chisel.maude

This command will start an input/output loop where Chisel commands can be executed.
The available commands in Chisel are:
* *(set side-effect sorts SORTS .)*, for indicating that *SORTS* are the side-effect sorts.

* *(set context-update rules RULES .)*, for indicating that *RULES* are the context-update
rules.

* *(dataflow inferences SORT .)*, for showing the dataflow inferred for the given
*SORT* for programs.

* *(slice PROGRAM wrt VARS .)*, for (intra)slicing the program *PROGRAM* given the slicing
variables *VARS*.

* *(islice SORT with defs DEFS wrt VARS .)*, for interprocedural slicing of the given
top sort *SORT*, with a set of function definitions *DEFS* and a set of slicing variables
*VARS*.