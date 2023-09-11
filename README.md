# setup-llvm-msvc
GitHub action to set up llvm-msvc


## Use it in your workflow like this:
```
- name: Setup llvm-msvc
  uses: backengineering/setup-llvm-msvc@v5
```
```
- name: Setup llvm-msvc
  uses: backengineering/setup-llvm-msvc@v5
  with:
    version: llvm-msvc-v3.0.6
    path: $GITHUB_WORKSPACE
    token: ${{ secrets.PAT }}

```        

API
---

| Input     | Value       | Default | Description
| --------- | -------     | ------- | -----------
| version   | latest      | ✓       | Install the latest version available in the repository.
| path      | $env:TEMP   | ✓       | Path to store installer.
| token     | ${{ github.token }}   | ✓       | The GitHub token used to create an authenticated client.

## Example
```
- name: Setup llvm-msvc
  uses: backengineering/setup-llvm-msvc@v5
  with:
    token: ${{ secrets.PAT }}

- name: Checkout
  uses: actions/checkout@v2
      
- name: Build
  run: |
    cmake -B build -TLLVM-MSVC_v143
    cmake --build build --config Release
```
