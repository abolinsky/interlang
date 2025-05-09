# interlang
interlang - the interface language

## What is it?
interlang is a synthesis of declarative programming, formal methods, and AI-driven code generation, with a compiler that acts more like a verifier and synthesizer than a traditional translator.

It is a compiled language with no variables. The programmer architects a program by specifying interfaces and constraints on those interfaces. Tests are first-class citizens. The compiler uses the specification written by the programmer to generate the implementations of these interfaces such that they satisfy the constraints. The compiler can generate a final program in any language the programmer specifies (e.g. C++, Javascript, go, etc.).

## Core principles
1. No Variables:
    - Instead of named state, everything is described through constraints, interfaces, and contracts.
    - This would heavily favor referential transparency and functional purity.
2. Tests as First-Class Citizens:
    - Test cases are built into the language, not external.
    - The compiler treats them as mandatory conditions that implementations must satisfy.
    - Could resemble property-based testing or formal verification assertions.
3. Interfaces + Constraints = Program:
    - Programmers describe:
        - What modules/functions must do (interfaces).
        - Under what conditions (constraints).
    - There is no manual implementation unless desired.
    - The compiler (backed by an LLM) figures out how to implement them.
4. LLM-Powered Compilation:
    - The compiler uses a plug-and-play LLM backend (e.g., GPT, Claude, Gemini, open-source models).
    - Different models can be swapped without changing source code.
    - LLM acts like a code generator, fulfilling interface+constraint specifications.
