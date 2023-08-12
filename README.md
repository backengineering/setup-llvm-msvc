# setup-llvm-msvc
GitHub action to set up llvm-msvc


## Use it in your workflow like this:
```
- name: Setup llvm-msvc
  uses: backengineering/setup-llvm-msvc@v3
```
```
- name: Setup llvm-msvc
  uses: backengineering/setup-llvm-msvc@v3
  with:
    version: llvm-msvc-v2.9.3
    path: $GITHUB_WORKSPACE

```        

API
---

| Input     | Value       | Default | Description
| --------- | -------     | ------- | -----------
| version   | latest      | ✓       | Install the latest version available in the repository.
| path      | $env:TEMP   | ✓       | Path to store installer.

## Example
```
- name: Setup llvm-msvc
  uses: backengineering/setup-llvm-msvc@v3

- name: Checkout
  uses: actions/checkout@v2
      
- name: Build
  run: |
    cmake -B build -TLLVM-MSVC_v143
    cmake --build build --config Release
```
