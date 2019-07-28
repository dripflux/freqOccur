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
_Discussion_

...

## Command Line Arguments
_Discussion_

Short/Long arguments and options style (classic command line), sub-command style (git, openssl), or both?

### Classic Style
_Discussion_

...

_Arguments and Options_

-a \<format\> : Process input as format.
  Single use applies to all input files.
  [future] First use applies to follow on input files (until next as option), and preceding input files.
  [future] Successive uses apply to follow on input files.

-A \<format\> : Produce output as format.
  Single use applies to all output files.
  [future] First use applies to follow on output files (until next AS option), and preceding output files.
  [future] Successive uses apply to follow on output files.

--classic : Process command line arguments as classic style.

-f \<fields\> : Fields to process. Comma separated values, interpret decimal values as field numbers, indexing starts at 1.
  Single use applies to all input files.
  [future] First use applies to follow on input files (until next field option), and preceding input files.
  [future] Successive uses apply to follow on input files.

-F \<fields\> : Fields to process. Comma separated values, interpret decimal values as field names. Requires labeled data format.
  [future] Same multiple use processing rules as -f option.

-g \<fields\> : Group by input fields to process. Comma separated values, interpret decimal values as field numbers, indexing starts at 1.
  Single use applies to all input files.
  [future] First use applies to follow on input files (until next field option), and preceding input files.
  [future] Successive uses apply to follow on input files.

-G \<fields\> : Group by input fields to process. Comma separated values, interpret decimal values as field names. Requires labeled data format.
  [future] Same multiple use processing rules as -f option.

-h : Help message. Display help message.

-i \<filename\> : Input file.
  [future] (Multiple processing tasks)

-I [future] (Reserved for future IOC, Indicator Of Compromise, use)

-o \<filename\> : Output file.
  [future] (Multiple processing tasks)

--scripted : [future] Perform internal processing as if scripted, less overall memory usage (better support of large files on constrained systems).

### Sub-Command Style
_Discussion_

Rationale, sub-command style is a more natural transition to VUI (Voice User Interface); i.e. CLI and VUI are similar/same style.

Verbs...

Adverbs...

Nouns...

Adjectives...

E.g. $ freqOccur process \<files\> [as \<format\>] [take \<fields\>] ... {[count|sum|...] [output [file] [as \<format\>]]}...

_Commands and Clauses_

...
