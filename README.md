# interlang
interlang - the interface language

## What is it?
interlang is a synthesis of declarative programming, formal methods, and AI-driven code generation, with a compiler that acts more like a verifier and synthesizer than a traditional translator.

It is a compiled language with no variables. The programmer architects a program by specifying interfaces and constraints on those interfaces. Tests are first-class citizens. The compiler uses the specification written by the programmer to generate the implementations of these interfaces such that they satisfy the constraints. The compiler can generate a final program in any language the programmer specifies (e.g. C++, Javascript, go, etc.).
