# LaTeX-Expansions *for Sublime Text 3*

![Illustration of LaTeX-Expansions](https://i.imgur.com/qmvH0E7.gif)

Install directory: `C:\Users\<YOURUSERNAME>\AppData\Roaming\Sublime Text 3\Packages\LaTeXTools`

This JSON file can be used in Sublime Text 3 by **[LaTeX-Tools](https://github.com/SublimeText/LaTeXTools)** to increase the efficiency of your writing not only with initiating/navigating/closing of LaTeX environments but also in reducing the time spent typing common terms. This config has been designed with Chemistry in mind but the potential for increasing this project's scope is very broad. 

Expansions are triggered by typing a short field of text, (the *snippet*) of text and pressing `Tab` to expand the snippet to its defined field, (the *expansion*). For example in the .gif illustration above, typing `"sup"` then pressing `Tab` auto-fills the field to `\textsuperscript{}`, what's more, the cursor automatically knows to move to within the curly braces so that you can fill them, and pressing tab again moves the cursor outside the braces when you've finished filling the braces.

# Principles
A few guiding principles for how the expansions should be structured are as follows:

 1. *Snippets* should be short (this is meant to save time, right?)
 2. *Snippets* should not be so general as to be confusing (e.g - Avoid things like `"subs"` for `\textsubscript{}` because this could be mistaken for expanding to `\subsection`
 3. *Expansions* should intuitively follow from the content of the *snippet* 
 
	 4. Users should be able to *by-in-large* predict the *expansion* just given the *snippet*, or at least, not be shocked by the *expansion* which results. This helps users having to learn by rote which *snippets* create which *expansions*
 4. *Expansions* should be feature-complete (if you're unsure with whether or not to add certain fields like `\label{}` for example, err on the side of adding it)
 5. Snippets should be internally consistent, that is, if adding a new *snippet* which is related to another snippet, it should be assigned logically
 
	 6.	For example, considering `"sec"` expands to `"\section{}"`, `"ssec"` should be used to expand to `\subsection{}` and `"sssec"` (**NOT** 2sub or similar) should be used to expand to `\subsubsection{}`
 6.	*Expansions* should be intelligent
 
	 7.	`$n` can be used iteratively to move the cursor following pressing `Tab` with `$0` being the final position. This should be used so the the user can tab their way through the *expansion* from beginning to end in a thought-through manner
	 8.	Line breaks (by using `\n` should be employed where appropriate, for example `\\section{$1}\n$0`is preferred over `\\section{$0}\n` or worse again, `\\section{}`

9.	Because JSON does not permit comments, line breaks separate clusters of related *snippets*


10. Include multiple variants where possible to maximise user flexibility

	11. For the example of the *expansion* "nausea and vomiting", the following variants were included
		
	        { "trigger": "NandV", "contents": "Nausea and Vomiting"},
            { "trigger": "Nandv", "contents": "Nausea and vomiting"},
            { "trigger": "nandv", "contents": "nausea and vomiting"},
            { "trigger": "n&v", "contents": "nausea \\& vomiting"},
            { "trigger": "N&V", "contents": "Nausea \\& Vomiting"},
	        { "trigger": "N/V", "contents": "Nausea \\& Vomiting"},
            { "trigger": "n/v", "contents": "nausea \\& vomiting"},
		
    12. In this example, there are variants for not only alternate capitalisations, but also for `&` vs `and`.

# Expanding Scope

Areas of interest for the time being include

 - Medical acronyms and terminology
 - Optimising LaTeX
 - Physics
 
# Dependencies

 - [Sublime Text](https://www.sublimetext.com/) (3 is tested, YMMV using ST2)
 - [LaTeX-Tools](https://github.com/SublimeText/LaTeXTools)
 - A working LaTeX distribution (not required technically but most users will need this)
