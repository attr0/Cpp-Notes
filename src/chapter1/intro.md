# 新基础类型



## 整数类型 long long

> 在C99中正式加入，所以C++98并没有`long long`类型:(

`long long` 表示一个**至少**为64位的有符号整数类型，对应无符号类型为`unsigned long long`，其后缀分别为`LL`和`ULL`

```cpp
// 此时必须使用后缀，不然则当成默认32bit处理
long long x1 = 65535   << 32;  // x1=0
long long x2 = 65535LL << 32;  // x2 为0x10000 0000，正确的
```



其最大值最小值在宏和limits类模板中均有定义

```c++
#include <limits>
// ...
// marco
std::cout << LLONG_MAX <<　'\t' << LLONG_MIN << '\n';
std::cout << ULLONG_MAX << '\n';
// limits
std::cout << std::numeric_limits<long long>::max() << '\t'std::numeric_limits<long long>::min() << '\n';
```



格式化时，请用`%lld`和`%llu`，但推荐使用C++流来处理



## 新的字符类型 `char16_t` 和 `char32_t`

