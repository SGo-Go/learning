# Patterns with enums in C/C++

## Strong type alias (strong typedef)  (since C++17)

**Motivation**:

In C++, conventional type aliases are transparent
(i.e., aliases with the same underlying type can be interchanged without errors and warnings).
[Strong](https://en.wikipedia.org/wiki/Strong_and_weak_typing) type alias (strong typedef)
for integral types (like [`std:::byte`](https://en.cppreference.com/w/cpp/types/byte))
strengthen the restrictions w.r.t. substitutability and computational base [^Boeger-Strong-aliases].

[^Boeger-Strong-aliases]: Lukas Böger (2019) [*Strong aliases for integral types*](https://accu.org/journals/overload/27/152/boger_2683/)

**Solution**: 

`static_cast` has UB for empty scoped enums according to the [standard](https://cplusplus.github.io/CWG/issues/1766.html):

> A value of integral or enumeration type can be explicitly converted to an enumeration type. The value is unchanged if the original value is within the range of the enumeration values. Otherwise, the behavior is undefined.

C++17 guarantees to safely convert underlying integral type to enum by means of the list initialization
(even if the input value is out of the range of the enumeration values).
