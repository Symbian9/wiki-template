C++11 is used for all builds of Mapper.

This page documents the usage of C++11 features in OpenOrienteering Mapper. 

## Accepted Elements

`auto`

Initializer Lists

Nonmember `begin` and `end` 

`nullptr`

`override` and final` 

Range-based `for-loop

R-Value References and `std::move`

Smart Pointers, esp. `std::unique_ptr`

`static_assert`


### Suggested Elements

Unicode String Literals (MSVC support unknown) 


### Known Issues

Apple delivers C++11 with LLVM's Clang and libc++. This is the standard since Xcode 4.5. However, Apple does not provide libc++ for OS X 10.6 (Snow Leopard) which was released on 28 August 2009, but is still widely used. 

MSCV implements some features only in version 11 or newer. However, MSVC is not supported at the moment.


## Weblinks

  * [C++11/14 compiler and library shootout](http://cpprocks.com/c1114-compiler-and-library-shootout/)
  * [Elements of Modern C++ Style](http://herbsutter.com/elements-of-modern-c-style/) by Herb Sutter 
  * [C++0x Compiler Support](http://wiki.apache.org/stdcxx/C%2B%2B0xCompilerSupport) (Stdcxx Wiki) 
