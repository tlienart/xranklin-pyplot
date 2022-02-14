# Hello

abc

```!
using PyPlot
plot(rand(15), rand(15))
gcf()
```


\newcommand{\pycode}[1]{
  <!-- Show python code block -->
  ```python
  #1
  ```
  <!-- Execute code with PyCall.jl -->
  ```!
  #hideall
  using PyCall
  lines = replace(
    """#1""",
    r"(^|\n)([^\n]+)\n?$" => s"\1res = \2"
  )
  py"""
  $$lines
  """
  println(py"res")
  ```
}

\pycode{
  import pandas as pd
  df = pd.DataFrame({
    "A": ["Alice", "Bob"],
    "B": [2, 3]
    })
  df["B"].mean()
}
