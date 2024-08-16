# Patterns with traits in C/C++

## Member function with the given signature

**Motivation**: 
Ensure that class has a member function with the given signature

**Solution**: 

Use expression [SFINAE](https://en.cppreference.com/w/cpp/language/sfinae) [^gockelhut:has-member-trait-post] [^krzaq:member-func-trait-post] [^SO:expression-SFINAE] as pointed here: http://stackoverflow.com/a/12654277

<details><summary>Code</summary>

```c++
template <typename T>
struct HasMessageMethod
{
  private:
    using Yes = std::true_type;
    using No  = std::false_type;

    template <typename U>
    static decltype(std::is_same_v<decltype(std::declval<U>().message(std::errc{})), std::string_view>, Yes())
    test(int);
    template <typename>
    static No test(...);

  public:
    static constexpr bool value = std::is_same_v<decltype(test<T>(0)), Yes>;
};
```
</details>

[^gockelhut:has-member-trait-post]: `has_member`. http://www.gockelhut.com/cpp-pirate/has-member.html
[^krzaq:member-func-trait-post]: https://dev.krzaq.cc/post/checking-whether-a-class-has-a-member-function-with-a-given-signature/
[^SO:expression-SFINAE]: https://stackoverflow.com/questions/12654067/what-is-expression-sfinae/12654277#12654277



## `is_base_of` with template base

**Motivation**: 
checks if a template type is a base of the other type.

**Solution**: 

```c++
template <template <class...> class BaseT, class DerivedT>
struct IsBaseOf
{
  private:
    using Yes = std::true_type;
    using No  = std::false_type;

    template <class... ErrorCodeEnumTraitsTs>
    static Yes test(BaseT<ErrorCodeEnumTraitsTs...>);
    // qacpp-2012-R1: The ellipsis is only used for SFINAE purposes
    static No test(...); // PRQA S 2012 # R1

  public:
    static constexpr bool value = decltype(test(std::declval<DerivedT>()))::value;
};
```