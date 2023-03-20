# AVRAssemblyLatexListing
A Latex "listings" style that can be used in Lyx, or plain LaTeX, to highlight code written in AVR Assembly.
 
Place `AVRAssembyLanguage.tex` file in your working directory (next to the latex file you're working on).  
To add it to your project, place:
```TeX
\input{AVRAssembyLanguage.tex}  
```
somewhere before ```\begin{document}``` in your latex file.  

In your document, place your arduino code between:
``` TeX
\begin{lstlisting}[language=AVRAssembly]  
    %% AVR Assembly code here %%  
\end{lstlisting}
``` 
  
  
Or create your own style to make changes like adding non-built-in functions and variables.  After ```\input{AVRAssembyLanguage.tex}```, but before ```\begin{document}```, place:
``` TeX
\lstdefinestyle{AVRasm}{
  language=AVRAssembly,
  %% Add other words needing highlighting below %%
  morekeywords=[1]{},        % [1] -> dark blue - opcodes
  morekeywords=[2]{},        % [2] -> blue - registers & bit names
  morekeywords=[3]{},        % [3] -> bold orange - directives
  morekeywords=[4]{},        % [4] -> bold green - assembler functions 
  %% The lines below add a nifty box around the code %%
  frame=shadowbox,
  rulesepcolor=\color{arduinoBlue},
  numbers=left,
}
 ``` 
And in your document place your arduino code between:
``` TeX
  \begin{lstlisting}[style=AVRasm]  
    %% arduino code here %%  
  \end{lstlisting}  
``` 
