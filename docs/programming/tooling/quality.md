# Tools

- [Helix QAC](https://www.perforce.com/products/helix-qac):
  [CLI](https://esrlabs.github.io/bake/source/tips_and_tricks/qac.html)
  [rules](https://wiki.sei.cmu.edu/confluence/display/c/Helix+QAC)

# Glossary

| Term                                                                            | Meaning                                                                                                                                                             |
|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [**undefined behavior**](https://en.wikipedia.org/wiki/Undefined_behavior) (UB) | Prescribed to be unpredictable, in the language specification (most common for incorrect constructs or invalid data)                                                |
| [**unspecified behavior**](https://en.wikipedia.org/wiki/Unspecified_behavior)  | Specification does not prescribe a result (behavior for a well formed program varying between compilers, compiler is not required to document what its behavior is) |

| Abbrev | Term                                                                         |
|--------|------------------------------------------------------------------------------|
| STCYC  | [Cyclomatic complexity](https://en.wikipedia.org/wiki/Cyclomatic_complexity) |
| STMIF  | Deepest Level of Nesting                                                     |
| STELF  | Number of Dangling Else-Ifs                                                  |
| STPAR  | Number of Function Parameters                                                |
| STRET  | Number of Return Points in Function                                          |
| STUNR  | Number of Unreachable Statements                                             |
| STUNV  | Unused or Non-Reused Variables                                               |
| STSUB  | Number of Function Calls                                                     |
| STAKI  | Akiyama's Criterion (STCYC + STSUB)                                          |
|--------|------------------------------------------------------------------------------ |
| COMF   | Comment Density                                                              |
