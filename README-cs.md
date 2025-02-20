# csCatch2
a wrapper over catch2 library to easy compile with cmake presets

## How to Build

- checkout in a folder, e.g., `projects/csCatch2` where `csCMake` has already been checked out in `projects/csCMake`
  - your folder structure will look like
```
projects
  csCMake
    csCMake.cmake
    ...
  csCatch2
    csCatch2
      README.md
      ...
```  
- checkout `Catch2` repo as subfolder of this folder (note it is not a git submodule)
- create a `cmakeUserPath.json` file with  your settings for path. The following should be sufficient
```
{
  "version":  10,
  "configurePresets": [
    {
      "name": "cmake-user-path-msvc2022-x64",
      "hidden": true
    },
    {
      "name": "cmake-user-path-msvc2022-x64-LLVM",
      "hidden": true
    }
  ]
}
```
- check now your folder contains
```
projects
  csCMake
    csCMake.cmake
    ...
  csCatch2
    csCatch2
      Catch2
      README.md
      cmakeUserPath.json
      ...
```  

- compile with one of the available workflows, e.g.,
```
cmake --workflow msvc2022-x64
```

## Available workflows

- `msvc2022-x64`
- `msvc2022-x64-LLVM`

## TODO list
- add automatic checkout of `Catch2` folder in cmake