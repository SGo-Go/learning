# Patterns with traits in C/C++

## Member function with the given signature

**Motivation**: 
Ensure that class has a member function with the given signature

**Solution**: 

Use expression [SFINAE](https://en.cppreference.com/w/cpp/language/sfinae) [^krzaq:member-func-trait-post] [^SO:expression-SFINAE] as pointed here: http://stackoverflow.com/a/12654277

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

[^krzaq:member-func-trait-post]: https://dev.krzaq.cc/post/checking-whether-a-class-has-a-member-function-with-a-given-signature/
[^SO:expression-SFINAE]: https://stackoverflow.com/questions/12654067/what-is-expression-sfinae/12654277#12654277
