
python is strongly and dynamically typed.
JS i weakly typed as it allows type-coercion like "1" + 2 => "12"


__name__ is a built-in variable which evaluates to the name of the current module. 
If the source file is executed as the main program, the interpreter sets the __name__ variable to have a value “__main__”. If this file is being imported from another module, __name__ will be set to the module’s name.
It can be used to check whether the current script is being run on its own or being imported somewhere else


Memory management ++++++++++++
  Memory allocatd in the form of private heap space.
  in-built garbage collection 

Gobal namespace -
  for imported packages. Ex: import sys

Build-in namespace -
  Builtin functions of core python and built-in names for various types of exceptions.

Decorators - 
  They add functionality to an existing function without chnaging the struture of function itself.
  besides adding functionality to the output of the method, they can even accept arguments for functions
  and can further modify those arguments before passing it to the function itself.

    def lowercase_decorator(function):
      def wrapper():
          func = function()
          string_lowercase = func.lower()
          return string_lowercase
      return wrapper

    @lowercase_decorator 

List and Tuples -
  Lists are mutable and tuples are non mutable

Lambda functions ---
  Anonymous functions

pass - 
  null operation. To fill empty blocks of code.

Generators --
  They return an iterable collections of items. They use yield keyword.

*args ---
  pass variable length argument

**kwargs ---
  pass variable length keyworded argument. It is actually a dictionary.


TensorFlow - 
  Based on execution of data flow graph, where node is mathematical operation and edge, a multidimensional array tensor...
  Works with CPU, GPU and distributed processing.
  Computations are run after creation of session

