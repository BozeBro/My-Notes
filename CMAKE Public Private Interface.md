# TL;DR 
- Public if libraries included is used by header and source files
- Private if library is only used by source files
- Interface if library is only used in the header (think header-only impls)
[Follow up read](https://kubasejdak.com/modern-cmake-is-like-inheritance)
Cmake uses Public by default. 


### included directories and interface directories
**INCLUDE_DIRECTORIES** and **INTERFACE_INCLUDE_DIRECTORIES** are two variables that have header files to search when building a *target*. **INCLUDE_DIRECTORIES** are used only for *target*, **INTERFACE_INCLUDE_DIRECTORIES** are appended to the included directories for other targets that depend on *target* 

### Public, Private, and Interface distinction
Public - headers here are used in target's include directories and its interface include
Private - headers are only used in the current target
Interface - headers are only used by other target's that depend on the current one being built

#### Example:
Thinking in terms of inheritance, say we privately link Shape library to Math library. Then let's link the Shape library to a target we are building. Then we can use the functionality in Shape but not in Math. Linking Publicly Shape to Math would allow use to use the Math library.

If only your src files include a header library, than the library is PRIVATE
If src and header files include the header, than the library is PUBLIC

If the header files include other libraries not used by the src, than the library is INTERFACE
Imagine B has a class called Pizza, and it's used in a class definition in A as a pointer. The Pizza pointer is not used in the src files but accessible as an API. Than, we do not need the full implementation of Pizza, but only the headers (pointers can be incomplete). Remember forward declarations from Roblox. 