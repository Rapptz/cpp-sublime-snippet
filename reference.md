## Documentation

In this documentation, `$1` represents the first tabbed input, all the way to `$n`. `$0` represents the last place you end up in after you're done tabbing. If there are two `$n`, e.g. `$1 f($1)`, then that means whatever you input will be put in those two places. If you see `${2:$1}` then that means that you can input part of $2 first, in this case $1, and then tab over to the whole expression, which in this case is `$2`.

To activate a snippet just type the trigger and then press tab.

Although the snippets show up as having four spaces in the reference, in the actual snippet it will substitute it with
your preference.

## Table of Contents

- [Loops](#loops)
- [Little Utilities](#little-utilities)
- [Conditional Statements](#conditional-statements)
- [Header Guards](#header-guards)
- [Namespace](#namespace)
- [MIT License](#mit-license)
- [Struct](#struct)
- [Template](#template)
- [Regular Functions](#regular-functions)
- [Templated Functions](#templated-functions)
- [Using Statements](#using-statements)
- [Functors](#functors)

### Loops

A collection of loop auto completions.

**Trigger**: do

```cpp
do {
    $0
} while ($1);
```

**Trigger**: while

```cpp
while($1) {
    $0
}
```

**Trigger**: for

```cpp
for(unsigned $2 = 0; $2 < $1; ${3:++$2}) {
    $0
}
```

**Trigger**: forv

```cpp
for(auto&& $1 : $2) {
    $0
}
```

### Little Utilities

Small simple stuff that can help with some typing.

**Trigger**: forw

```cpp
std::forward<$1>($2)
```

**Trigger**: declv

```cpp
std::declval<$1>()
```

**Trigger**: returns

```cpp
-> decltype($1) {
    return $1;
}
```

### Conditional Statements

**Trigger**: if

```cpp
if ($1) {
    $0
}
```

**Trigger**: ifelif

```cpp
if($1) {
    $2
}
else if($3) {
    $4
}
else {
    $0
}
```

### Header Guards

**Trigger**: ifnd

```cpp
#ifndef $1
#define $1

$0

#endif // $1
```

This snippet defaults to inserting the filename in all caps. e.g. `myheader.hpp` would generate `MYHEADER_HPP`.

### Namespace

**Trigger**: name

```cpp
namespace $1 {
$0
} // $1
```

### MIT License

**Trigger**: mitl

A snippet that generates an MIT License with input choices for your name and year.

### Struct

**Trigger**: struct

```cpp
struct $1 {
    $0
};
```

### Template

**Trigger**: tem

```cpp
template<typename $1>
```

### Regular Functions

**Trigger**: funct

```cpp
$1 $2($3) {
    $0
}
```

There is a `constexpr` variation:

**Trigger**: confunct

```cpp
constexpr $1 $2($3) {
    return $0;
}
```

### Templated Functions

**Trigger**: tempfunc

```cpp
template<typename $1>
$2 $3($4) noexcept {
    $0
}
```

There is also an alternative with `auto`:

**Trigger**: tempfunca

```cpp
template<typename $1>
constexpr auto $2($3) noexcept -> decltype($4) {
    return $4;
}
```

### Using Statements

**Trigger**: usingt

```cpp
template<typename $1>
using $2 = $3;
```

There is also a non-templated version.

**Trigger**: usings

```cpp
using $1 = $2;
```


### Functors

**Trigger**: functor

```cpp
struct $1 {
    $2 operator()($3) const noexcept {
        $0
    }
};
```

There are also templated variations of functors:

**Trigger**: tempfunctor

```cpp
struct $1 {
    template<typename T>
    constexpr auto operator()(T&& t) const noexcept -> decltype($2) {
        return $2;
    }
};
```

**Trigger**: bintempfunctor

```cpp
struct $1 {
    template<typename T, typename U>
    constexpr auto operator()(T&& t, U&& u) const noexcept -> decltype($2) {
        return $2;
    }
};
```