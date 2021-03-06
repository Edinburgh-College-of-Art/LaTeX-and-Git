# LaTeX-and-Git
##### using LaTeX with a git repo

[The Wikibook for LaTeX is a fantastic resource](https://en.wikibooks.org/wiki/LaTeX). Here is some basic info to get you started.

## 1. Creating a project

`.tex` files are essentially just text files. Just like this file `README.md`, which is a markdown file, `.tex` files are just text with TeX commands. It is recommended that you install a LaTeX distribution as suggested in [the setup page](https://edinburgh-college-of-art.github.io/2019-04-15-gitcarp/). TeX packages just ensure you have a tex compiler installed. You can edit your tech file in whichever plain text editor you are comfortable with. [You can even use LaTeX in atom](https://gist.github.com/Aerijo/5b9522530715e5be6e89fc012e9a72a8)

For LaTex in Atom, download these packages:
  - [Language-LaTeX](https://atom.io/packages/language-latex) by area
  - [Latex](https://atom.io/packages/latex) compile tool by thomasjo
  - [latex-autocomplete](https://atom.io/packages/latex-autocomplete) by evpok

## 2. Building the file

For a LaTeX file to build, all we need is:

```latex
\documentclass[12pt]{article}
\begin{document}
Some Text
\end{document}
```

For the proposal and final submission, you will be provided with a LaTeX template. It is good to start with the basics in order to experiment. The `\documentclass[options]{type}` can take a number of options and the format of the document can be set to change the layout. [The options and types are documented in the LaTeX wikibook](https://en.wikibooks.org/wiki/LaTeX/Document_Structure#The_document_environment)

The compiler you use may have some effect on the final look of your file. `pdflatex` is the recommended compiler for your submission. You should build the file from time to time to make sure that there are no errors. Try not to ignore errors for too long as you will have to fix them at some point.

## 3. BiBTeX

Like tex files, BiBTeX files are just text with a specific format. It is recommended that you use a bibliography management app like [JabRef](http://www.jabref.org) or BibDesk for macOS

You should be able to export Bibtex resources for journal articles that you are using. DiscoverEd has this functionality. Export to bibtex and use utf-8 encoding

To use a bibliography file you need to place the following commands at the end of your LaTeX file (that is, after the content, but before `\end{document}`).
```latex
\bibliographystyle{plain}
\bibliography{path/to/bib/file}
```

The `\cite{ref_key}` is the command you need, making sure that the `ref_key` corresponds exactly to one of the entries in the `.bib` file. If you wish to cite more than one reference at the same time, do the following: `\cite{ref_key1, ref_key2, ..., ref_keyN}`.

##### Workflow
- latex
- bibtex
- latex
- latex

Specifically

- `latex latex_source_code.tex`
- `bibtex latex_source_code.aux`
- `latex latex_source_code.tex`
- `latex latex_source_code.tex`

## 4. [Figures](https://en.wikibooks.org/wiki/LaTeX/Floats,_Figures_and_Captions)

Figures are always in the form:

```latex
\begin{figure}[placement_specifier]   
     \includegraphics[width=0.25\textwidth]{path/to/file}
   \caption{Caption Text}
\end{figure}
```
<table>
<tbody><tr>
<th>Specifier
</th>
<th>Permission
</th></tr>
<tr>
<td><code>h</code>
</td>
<td>Place the float <i>here</i>, i.e., <i>approximately</i> at the same point it occurs in the source text (however, not <i>exactly</i> at the spot)
</td></tr>
<tr>
<td><code>t</code>
</td>
<td>Position at the <i>top</i> of the page.
</td></tr>
<tr>
<td><code>b</code>
</td>
<td>Position at the <i>bottom</i> of the page.
</td></tr>
<tr>
<td><code>p</code>
</td>
<td>Put on a special <i>page</i> for floats only.
</td></tr>
<tr>
<td><code>!</code>
</td>
<td>Override internal parameters LaTeX uses for determining "good" float positions.
</td></tr>
<tr>
<td><code>H</code>
</td>
<td>Places the float at precisely the location in the LaTeX code. Requires the <span style="font-family: monospace; color: #2020C0; font-weight: normal;">float</span> package. i.e., <code class="mw-highlight" dir="ltr"><span class="k">\usepackage</span><span class="nb">{</span>float<span class="nb">}</span></code>.
</td></tr></tbody></table>


## 5. [Equations](https://en.wikibooks.org/wiki/LaTeX/Advanced_Mathematics)

Below is short cheat sheet for typing equations into LaTeX. If you need to use special characters at any point, it is easier to insert symbols inline using `\( \)`. Anything written beteen `\[ \]` or `\( \)` is typically referred to as *math mode*

| Function      | Description |
| ------------- |-------------|
| `\[ ... \]` | equation display     |
| `/( ... /)` | inline equation |
| `^{...}` | Superscript      |
| `_{...}`      | Subscript |
| `\frac{n}{d}` | fraction with a numerator `n` and denominator `d` |

[A reasonably comprehensive list of symbols can be found in the wikibook](https://en.wikibooks.org/wiki/LaTeX/Mathematics#List_of_mathematical_symbols). Use an app like LaTeXiT to style equations.

## 6. LaTeX and Git


Using LaTeX and git together, take heed of the following.

Use a `.gitignore` to avoid committing files generated by LaTeX. There is a TeX ignore template when creating a `.gitignore` file.


## 7. Spell Checking

For spell checking in LaTeX, [check here](https://en.wikibooks.org/wiki/LaTeX/Tips_and_Tricks#Spell-checking_and_Word_Counting)

### macOS
1. Start Terminal
2. If Homebrew is not installed run:
  `ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)" < /dev/null 2> /dev/null`

#### ispell
3. `brew install ispell`
#### aspell
3. `brew install aspell`
#### hunspell
3. `brew install hunspell`

### Windows

### Linux
- `apt-get install ispell`
- `apt-get install aspell`
- `apt-get install hunspell`


## Step-by-step

- create a repository
- clone the repository
- Create a `.tex` file in local repository directory
- type in `.tex` file:
```latex
\documentclass[12pt]{article}
\begin{document}
Some Text
\end{document}
```
- compile
- commit
- push

# Notes

- use back ticks \`\` for quotations on the left hand side
- There are macros for compiling your bibliography to avoid having to manually compile 4 times.
