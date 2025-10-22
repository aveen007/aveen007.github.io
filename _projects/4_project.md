---
layout: page
title: MonKeys Programming Language Compiler
description: Custom compiler for a dynamically typed language with inheritance, polymorphism, and template support, featuring a stack-based virtual machine with shared memory architecture.
img: /assets/img/Monkey.png
importance: 2
category: work
related_publications: false
---

The MonKeys Programming Language Compiler is a comprehensive compiler system developed from scratch for a custom dynamically typed programming language. This project demonstrates advanced compiler design skills, featuring support for object-oriented programming concepts, template-based generics, and a complete toolchain from source code to executable bytecode.



## Language Features

### Advanced Type System
- **Dynamic Typing**: Flexible type system with runtime type resolution
- **User-Defined Types**: Custom classes/structs with member variables and methods
- **Inheritance Hierarchy**: Single inheritance with member and method extension
- **Polymorphism**: Method overriding and dynamic dispatch
- **Template Support**: Generic programming with type parameters

### Modern Language Constructs
- **Object-Oriented Programming**: Full class-based programming model
- **Method Overriding**: Runtime polymorphism through virtual method tables
- **Member Access Control**: Structured access to type members and methods
- **Expression Evaluation**: Complex arithmetic and logical operations

## Compiler Architecture

### Multi-Stage Compilation Pipeline
- **Lexical Analysis**: Tokenization and syntax validation
- **Parser**: Constructs abstract syntax tree with type annotations
- **Control Flow Builder**: Generates operation tree with type-aware instructions
- **Code Generator**: Produces linear intermediate code for stack machine
- **Assembler**: Translates intermediate code to VM bytecode instructions

### Virtual Machine Design
- **Stack-Based Architecture**: Efficient execution model with operand stack
- **Shared Memory**: Common RAM for global data and heap allocation
- **Register Management**: Optimized variable storage and access
- **Execution Engine**: Bytecode interpreter with runtime type checking

## Technical Implementation

### Parser & Semantic Analysis
- **Recursive Descent Parsing**: Robust syntax analysis with error recovery
- **Symbol Table Management**: Comprehensive scope and type resolution
- **Type Checking**: Dynamic type verification and coercion rules
- **Inheritance Resolution**: Method table construction and override validation

### Code Generation
- **Intermediate Representation**: Linear code format for stack operations
- **Optimization Passes**: Basic peephole optimizations and constant folding
- **Memory Management**: Stack frame allocation and garbage collection ready
- **Template Instantiation**: Runtime generic type specialization


## Development Tools

### Console-Based Inspector
- **Runtime Debugging**: Real-time examination of program state
- **Nested Type Visualization**: Recursive display of complex object structures
- **Variable Inspection**: Local and global variable value examination
- **Stack Tracing**: Execution context and call stack analysis
- **Memory Analysis**: Heap allocation and reference tracking

### Build System
- **Modular Compilation**: Separate compilation units with linking
- **Error Reporting**: Detailed syntax and semantic error messages
- **Cross-Platform**: Portable implementation across development environments
- **Example Suite**: Comprehensive test programs demonstrating language features

## Example Programs

### Inheritance Demonstration
```monkeys
class Animal {
    var name;
    func speak() {
        print("Animal sound");
    }
}

class Dog extends Animal {
    func speak() {
        print("Woof! My name is " + name);
    }
}

var myPet = Dog();
myPet.name = "Buddy";
myPet.speak();  // Output: Woof! My name is Buddy