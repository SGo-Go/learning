# Patterns with macro in C/C++

## Safe concatenation macro

**Motivation**: 

Unspecified behavior is likely if macro contains multiple token-pasting operators ([## operators](https://en.cppreference.com/w/cpp/preprocessor/replace))
<details><summary>Example</summary>

```c++
#define XY _
#define CONCAT(A,B,C) A ## B ## C
CONCAT(X, Y, Z)
```
Possible macro outcomes:
- `_C` if the 1st ## operator is evaluated before the 2nd
- `XYZ` if the 2nd ## operator is evaluated before the 1st

</details>
<details><summary>QA rules: MISRA-C 19.12</summary>

Rule [MISRA-C](https://en.wikipedia.org/wiki/MISRA_C):[19.12](https://de.mathworks.com/help/bugfinder/ug/misra-c-coding-rules.html) [^SO:misra-c-macro]
([PRQA 1110](https://cpp-rules.bosch.com/vendor/qacpp/Default.html#doc/messages/1110.html))
asks for at most one occurrence of the # or ## preprocessor operators in a single macro definition.

[^SO:misra-c-macro]: https://stackoverflow.com/questions/52532210/is-misra-c-compatible-with-x-macros

</details>

**Solution**: 

[^SO:safe-concat-macro]: https://stackoverflow.com/questions/1489932/how-can-i-concatenate-twice-with-the-c-preprocessor-and-expand-a-macro-as-in-ar

Ensure full expansion of args before concatenation by extra level of indirection (`CONCAT` -> `PASTER`)
```c++
#define PASTER(__arg1, __arg2) __arg1##__arg2
// Safe concatenation of 2 args
#define CONCAT(__arg1, __arg2) PASTER(__arg1, __arg2)
// Left-folded concatenation of 3 args
#define LCONCAT3(__arg1, __arg2, __arg3) CONCAT(CONCAT(__arg1, __arg2), __arg3)
```

## Safe parameter expansion

**Motivation**: 

Embracing of macro args with parens brakes compilation in certain situations (e.g., when they are parts of template param, etc)

**Solution**: 

Add one move level of indirection  to ensure expansion of the 
```c++
#define PASS(__arg) __arg
```
