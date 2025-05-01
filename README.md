# Monkey Programming Language

Monkey is a programming language implemented in Go, featuring a C-like syntax with functional programming capabilities. This interpreter includes a lexer, parser, evaluator, and REPL (Read-Eval-Print Loop) for interactive use.

## Features

### Language Features

- **Data Types**:
  - Integers
  - Booleans
  - Strings
  - Arrays
  - Hashes (dictionaries/maps)
  - Functions (first-class)
  - Null values

- **Operators**:
  - Arithmetic: `+`, `-`, `*`, `/`
  - Comparison: `==`, `!=`, `<`, `>`
  - Logical: `!`

- **Control Structures**:
  - Conditionals (`if`/`else`)
  - Return statements

- **Variable Bindings**:
  - `let` statements

- **Functions**:
  - First-class functions
  - Higher-order functions
  - Closures

- **Data Structures**:
  - Arrays with indexing
  - Hash maps with string, integer, and boolean keys

- **Built-in Functions**:
  - `len`: Get length of arrays and strings
  - `puts`: Print values
  - `first`: Get first element of array
  - `last`: Get last element of array
  - `rest`: Get all elements except first
  - `push`: Add element to array

### Implementation Features

- **Lexer**: Tokenizes source code
- **Parser**: Recursive descent parser that builds an Abstract Syntax Tree (AST)
- **Evaluator**: Tree-walking interpreter that evaluates the AST
- **REPL**: Interactive shell for testing and exploration
- **Object System**: Represents values in the language

## Getting Started

### Prerequisites

- Go (version 1.11 or later recommended)

### Installation

1. Clone the repository:
   ```
   git clone <repository-url>
   cd monkey
   ```

2. Build the interpreter:
   ```
   cd src/monkey
   go build
   ```

### Running the REPL

After building, run the interpreter:

```
./monkey
```

This will start the REPL where you can enter Monkey code interactively.


## Project Structure

The project is organized into several packages:

- **token**: Defines the token types and structures
- **lexer**: Converts source code into tokens
- **ast**: Defines the Abstract Syntax Tree nodes
- **parser**: Parses tokens into an AST
- **object**: Defines the object system for representing values
- **evaluator**: Evaluates the AST to produce results
- **repl**: Provides the Read-Eval-Print Loop interface

## Implementation Details

The Monkey interpreter follows a traditional interpreter design:

1. **Lexical Analysis**: The lexer breaks the source code into tokens.
2. **Parsing**: The parser converts tokens into an Abstract Syntax Tree (AST).
3. **Evaluation**: The evaluator walks the AST and executes the code.

The parser uses Pratt parsing (also known as top-down operator precedence parsing) to efficiently parse expressions with different precedence levels.

The evaluator is a tree-walking interpreter that recursively evaluates nodes in the AST. It uses an environment to keep track of variable bindings and supports lexical scoping for closures.

