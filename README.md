- This folder contains an minimal offline pyscript example. It's created by following doc in https://docs.pyscript.net/2024.2.1/user-guide/offline/
- Both MicroPython and Pyodide interpreters are included. We can choose one of them by changing `public/index.html`. And we can also delete the folder of `public/micropython` or `public/pyodide` if unused.
- To use more packages released with Pyodide, we need to: 1) download the release package, e.g. [0.24.1](https://github.com/pyodide/pyodide/releases/tag/0.24.1); 2) extract and copy everthing in `pyodide-0.24.1/pyodide/` into `public/pyodide/`, then update `public/index.html` to add `packages` in `<py-config>`, for example:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>PyScript Offline</title>
  <script type="module" src="/pyscript/core.js"></script>
  <link rel="stylesheet" href="/pyscript/core.css">
</head>
<body>
  <py-config>
    interpreter = "/pyodide/pyodide.mjs"
    packages = ["pandas"]
  </py-config>
  <script type="py">
    import pandas as pd
    x = pd.Series([1,2,3,4,5,6,7,8,9,10])

    from pyscript import document
    document.body.append(str([i**2 for i in x]))
  </script>
</body>
</html>
```
