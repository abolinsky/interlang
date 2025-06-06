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
    - There is no default manual implementation unless explicitly defined.
    - The compiler (backed by an LLM) figures out how to implement them.
4. LLM-Powered Compilation:
    - The compiler uses a plug-and-play LLM backend (e.g., GPT, Claude, Gemini, open-source models).
    - Different models can be swapped without changing source code.
    - LLM acts like a code generator, fulfilling interface+constraint specifications.

## Possible program structure
```
Sorter {
  interface {
    sort(List<Int>) -> List<Int>
  }

  constraints {
    sort([3, 1, 2]) == [1, 2, 3]
    sort([]) == []
    forall l: List<Int> => isSorted(sort(l))
  }

  tests {
    assert sort([5, 4, 3]) == [3, 4, 5]
  }
}
```
### Component
`Sorter { ... }` declares a component called `Sorter`.

### Interface
`interface { ... }` declares the interface of the `Sorter` component. Inside it we define a function signature `sort(List<Int>) -> List<Int>`. This says: "Sorter has a function sort that takes a list of integers and returns a list of integers."

### Constraints
`constraints { ... }` declares the constraints on the `Sorter` component. Inside it we define one constraint per line.

### Tests
`tests { ... }` declares explicit tests that must pass for `Sorter` to be considered properly implemented.
