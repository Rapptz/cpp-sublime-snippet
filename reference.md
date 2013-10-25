## Documentation

In this documentation, `$1` represents the first tabbed input, all the way to `$n`. `$0` represents the last place you end up in after you're done tabbing. If there are two `$n`, e.g. `$1 f($1)`, then that means whatever you input will be put in those two places. If you see `${2:$1}` then that means that you can input part of $2 first, in this case $1, and then tab over to the whole expression, which in this case is `$2`.

To activate a snippet just type the trigger and then press tab.

Although the snippets show up as having four spaces in the reference, in the actual snippet it will substitute it with
your preference.

## Table of Contents

- [Do While Loop](#do-while-loop)
- [While Loop](#while-loop)
- [For Loop](#for-loop)
- [Range Based For](#range-based-for)
- [Forward](#forward)
- [If Statement](#if-statement)
- [Header Guards](#header-guards)
- [Namespace](#namespace)
- [Trailing Return](#trailing-return-type)
- [MIT License](#mit-license)
- [Struct](#struct)
- [Template](#template)
- [Templated Functions](#templated-functions)


### Do While Loop

**Trigger**: do

```cpp
do {
    $0
} while ($1);
```

### While Loop

**Trigger**: while

```cpp
while($1) {
    $0
}
```

### For Loop

**Trigger**: for

```cpp
for(unsigned $2 = 0; $2 < $1; ${3:++$2}) {
    $0
}
```

### Range-Based For

**Trigger**: forv

```cpp
for(auto&& $1 : $2) {
    $0
}
```

### Forward

**Trigger**: forw

```cpp
std::forward<$1>($2)
```

### If Statement

**Trigger**: if

```cpp
if ($1) {
    $0
}
```

### Header Guards

**Trigger**: ifnd

```cpp
#ifndef $1
#define $1

${0}

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

### Trailing Return Type

**Trigger**: returns

```cpp
-> decltype($1) {
    return $1;
}
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

