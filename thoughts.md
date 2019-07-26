# freqOccur Development Thoughts
Development design decision thoughts and rationale for freqOccur.

## Overall Design
Project shall be designed to support the below usage models.

- Command Line
- Interactive Python Session
- Library/Module

The above usage models support the various techniques used in cyber operations.

Object oriented and modular design paradigms are used to simultaneously support all three usage models.
The general idea is that the command line version will use the same classes and functions provided via an interactive Python session.
Similarly, the same classes and functions will be available when imported as a module.
The main() function will simply instantiate objects and call functions.
The control logic in main() will be the minimal; i.e. there should not be any core functionality in main() itself, core functionality should either be a method of a class or a separate function.

### Class vs. Function
...
