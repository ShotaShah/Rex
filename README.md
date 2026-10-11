# Rex

Rex is a lexical analyzer generator, similar to Lex/Flex for C. 

It reads a lexical specification file and generates code that performs lexical analysis according to the specified rules.

Rex currently supports only Haskell code generation, with support for other languages planned.


## Features

- Generates Haskell source code from lexical rules
- Can output a DFA (deterministic finite automaton) in Graphviz DOT format


## Requirements

- GHC
- Stack
- Graphviz (optional, for DFA visualization)


## Installation

Clone the repository and run:

    stack install


## Usage

To generate Haskell source code from a lexical specification file, run:

    rex -Ths abc.rex

This generates `abc.hs`.

To visualize the DFA and export it as a PDF:

    rex -Tdot abc.rex
    dot -Tpdf abc.dot -o abc.pdf

This generates `abc.pdf`.


## Examples

The `examples` directory contains:

- `abc` — reads from standard input and recognizes *abc*, *abcd*, and *abcde* as tokens. For example, the input *abcdabc* is tokenized as *abcd* + *abc*.
- `bignum` — reads from standard input and recognizes integers of four or more digits, with or without thousands separators. 
- `karamazov` — a benchmark example that scans the full English text of *The Brothers Karamazov* from Project Gutenberg and counts the occurrences of *Alyosha*.


## Name Origin

The name *rex* is a play on *lex*, with a nod to the notorious difficulty that Japanese speakers have in distinguishing *l* and *r*.

It also hints at regular expressions, which lie at the heart of lexical analysis.

