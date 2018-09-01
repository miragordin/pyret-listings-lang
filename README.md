# pyret-listings-lang

The [listings package](https://ctan.org/pkg/listings?lang=en) for LaTeX allows users to typeset programming code from a variety of languages. The file `pyret_lang.tex` defines the syntax coloring and style for code written in Pyret in accordance with the styles in the online Pyret editor. It loads the packages [`listings`](https://ctan.org/pkg/listings?lang=en) and [`xcolor`](https://ctan.org/pkg/xcolor), and defines Pyret as a `listings` language. The syntax to include Pyret code in a LaTeX file is as follows:
```
\documentclass{article}
\include{pyret_lang} % might need to specify a file path here

\begin{document}
\begin{lstlisting}[language=Pyret]
  # a simple function
  fun hello(name :: String, excited :: Boolean) -> String:
    doc: ```returns a personal greeting```
    if excited:
      "Hello, " + name + "!"
    else: 
      "Hello, " + name + "."
    end
  end

  hello("Mira", true)
\end{lstlisting}
\end{document}
```
which generates the output:

![screenshot-pyret-latex-output](screenshot-pyret-latex-output.PNG =250x100)

In this case, the file `pyret_lang.tex` is in the same directory as the main TeX file; otherwise, include the file path to `pyret_lang.tex`.
