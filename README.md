# _vcpkg

- Is found in my <drive:\directory/folder>\Projects\Git directory/folder
- where <some drive:directory/folder> is where my vcpkg installation resides
- Has 2 directories/folders
  - Debug
    - Has 3 directories/folders
      - mklink /j .\bin <some drive:directory/folder>\vcpkg\installed\<triplet>\debug\bin
      - mklink /j .\include <some drive:directory/folder>\vcpkg\installed\<triplet>\include
      - mklink /j .\lib <some drive:directory/folder>\vcpkg\installed\<triplet>\debug\lib
  - Release
    - Has 3 directories/folders
      - mklink /j .\bin <some drive:directory/folder>\vcpkg\installed\<triplet>\bin
      - mklink /j .\include <some drive:directory/folder>\vcpkg\installed\<triplet>\include
      - mklink /j .\lib <some drive:directory/folder>\vcpkg\installed\<triplet>\lib


- This works for me
  - instead of vcpkg integrate install
  - I only use the x64-windows triplet
  - I have a batch cmd file to copy dlls and pdbs from the `..\..\_vcpkg\$(Configuration)\bin directory/folder` to `$(OutDir)`
  - I am working on a C/C++ template
    - It will have the above listed directories populated
    - It will execute the batch cmd file as a Post Build event
    - Examples 
      - SDL2 `_Hello-SDL Project`
      - OpenGL `LunarLander Project`
