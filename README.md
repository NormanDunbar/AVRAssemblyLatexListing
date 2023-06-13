# AVRAssemblyLatexListing
A Latex "listings" style that can be used in Lyx, or plain LaTeX, to highlight code written in AVR Assembly.

## LaTeX
 
Place `AVRAssemblyLanguage.tex` file in your working directory (next to the latex file you're working on).  
To add it to your project, place:

```TeX
\input{AVRAssemblyLanguage.tex}  
```

somewhere before `\begin{document}` in your latex file.  

In your document, place your arduino code between:

``` TeX
\begin{lstlisting}[language=AVRAssembly]  
    %% AVR Assembly code here %%  
\end{lstlisting}
``` 
  
  
Or create your own style to make changes like adding non-built-in functions and variables.  After `\input{AVRAssemblyLanguage.tex}`, but before `\begin{document}`, add the following:

```TeX
\lstdefinestyle{AVRasm}{
  language=AVRAssembly,
  %% Add other words needing highlighting below %%
  morekeywords=[1]{},        % [1] -> dark blue - opcodes
  morekeywords=[2]{},        % [2] -> blue - registers & bit names
  morekeywords=[3]{},        % [3] -> orange - assembler directives
  morekeywords=[4]{},        % [4] -> green - assembler functions 
 }
 ``` 
And in your document place your arduino code like this:

```TeX
  \begin{lstlisting}[style=AVRasm]  
    %% arduino code here %%  
  \end{lstlisting}  
``` 

## Lyx

In Lyx, go to Document->Settings and click on LaTeX Preamble.

Add the following text to the existing preamble:

```TeX
\input{AVRAssemblyLanguage.tex} 

\lstdefinestyle{AVRasm}{
  language=AVRAssembly,
  %% Add other words needing highlighting below %%
  morekeywords=[1]{},        % [1] -> dark blue - opcodes
  morekeywords=[2]{},        % [2] -> blue - registers & bit names
  morekeywords=[3]{},        % [3] -> orange - assembler directives
  morekeywords=[4]{},        % [4] -> green - assembler functions 
}
```

To highlight some AVR assembly code, right-click the *program listing* insert, and select settings. On the advanced tab, add the text `style=AVRasm` (without quotes).

To highlight AVR assembly code inserts as a *child document*, right-click the inserted file, choose settings. At the bottom of the dialogue, add the text `style=AVRasm` in the "More parameters" editbox on the right side.
