# C+Alt
C+Alt (CplusAlt) is an alternative C++ standard library. It's designed to be used as an outright replacement for the C++ Standard Template Library, and **is not** directly compatible.

## What's wrong with C++'s Standard Template Library (STL)
STL is old. It was originally designed back in the late 80's and early 90's, back before the internet was prevelent and before internationalization was an everyday problem. A **huge** amount of important software is written in C++, so while C++ and STL can evolve, it can-not break compatibility. To much important code relies on it.

Even with all the improvements to the C++ language made by the ISO C++ comittee, when compared to competing languages, in practice C++ with the STL _is not_ a good language for new software.

C+Alt is a reboot. Starting with the C standard library, it throws away the naming scheme and heavy templating of the original 

## What does C+Alt code look like?
Work in progress


### Simple Mode
```c++
#include <alt.hpp>
using namespace alt;

int main( int argc, char* argv[] ) {
  Array<int> myArray = { 10, 20, 30 };
  String text = "myArray has "+myArray.size()+" elements";
  printN(text);   // Variation of `alt::print` that appends a newline

  return 0;
}
```

### Verbose Mode

```c++
#include <alt/lib.hpp>
#include <alt/array.hpp>
#include <alt/string.hpp>

int main( int argc, char* argv[] ) {
  alt::Array<int> myArray = { 10, 20, 30 };
  alt::String text = u8"myArray has "+myArray.size()+u8" elements 😊";
  alt::printN(text);    // Variation of `alt::print` that appends a newline

  return 0;
}
```


## C++ Language Wishlist
* Some way to set the default string format to UTF-8, without the `u8` string prefix.

## C+Alt Wishlist
* SIMD, vector, and matrix math as a first class members of Math library (GLSL syntax)
* Signal operations (smoothstep) as first class members of Math library
* `Flex` type as default for all containers (i.e. `alt::Array<>` == `alt::array<Flex>`)
* JSON, XML parsing (core lib or addon?)
* Networking (core lib or addon?)
