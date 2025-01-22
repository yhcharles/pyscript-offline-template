# Introduction

- This folder contains an minimal offline pyscript example. It's created by following doc in https://docs.pyscript.net/2024.2.1/user-guide/offline/
- Both MicroPython and Pyodide interpreters are included. We can choose one of them by changing `public/index.html`. And we can also delete the folder of `public/micropython` or `public/pyodide` if unused.
- To use more packages released with Pyodide, we need to: 1) download the packages released together with Pyodide, this can be done by `make pyodide`; 2) update `public/pyscript.toml` to include those packages
- This example by defaults includes `puepy`, which is a Python version Vue, see [the official site](https://docs.puepy.dev/) for more information

# TODO

- PWA support