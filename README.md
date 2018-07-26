# RStudio commenting

## Problem statement

Word and PDF output can be directly commented on by stakeholders. 
HTML output does not allow non-technical stakeholders to edit the document.

## Scope

This solution applies only to HTML content produced by Rmarkdown. 
A solution that requires compilation in an environment like RStudio Connect would be acceptable.

## Other examples of implementations

Both examples are more focussed on technical users. 
While it's great that other data scientists can comment AND run your code in a coloborative space
we would require this commenting feature on a pre-compiled analysis (notebooks are ok for exploratory use
but are not a robust way to build outputs, compared to running the document sequentially (e.g. `rmarkdown::render`).

### Colabotory

* https://colab.research.google.com/
* Python only
* Is an online notebook, like a Jypter and google doc hybrid
* Can comment on a block of code or text

![image](https://user-images.githubusercontent.com/2760096/43199249-a3d6d51a-9011-11e8-8c95-df8d0683dc75.png)
    
### Overleaf

* LaTeX focus
* Let's you click a point *in the code* and add a comment. Not as nice as Colab's solution.
* SyncTeX behaviour: clicking somewhere on the result PDF brings you to the corresponding position in the code, and *vice versa*

![image](https://user-images.githubusercontent.com/2760096/43199412-212f3a8e-9012-11e8-846d-83970045a699.png)

## Key features
* Can select something - e.g. word, image, cell on table - then add a comment on to it
	* More granular is better. e.g. select a cell awesome, select just the whole table, is still ok.
* *Nice to have:* Can ‘draw’ on the document.
* Comments ‘integrated’ - an example is Google’s Colob and Overleaf. E.g. move code and analysis to the same place (RStudio Connect)? So source and output are inherently linked - this means a comment ‘points’ to a line of the code. Or a block of code or text.
	* Limitation of Colob is python only, and it’s notebooks. In most data science settings, notebooks are for exploring - but ‘analyses’ are run as markdown blocks compiled on run (to enforce reproducibility)
	* A non technical user who is ‘reading’  the document via a web-browser (not executing the code) can make a comment.  
	* Code developer can click and jump to where that comes in the source code (Overleaf has this implemented for LaTeX)
	* Commenters often will not be R users (e.g. physicians, drug development teams)
	* Comment tied to line of code (e.g. line of code gone, so is comment)
	* Comment can also be marked as resolved in the browser
	* *Nice to have:* Can tag connect users in organisation (note many stakeholders note users of R environment)
	* *Nice to have:* Github.com and Github enterprise integration
	* When you recompile - comments persist unless resolved or line completely removed (if anchor for comment disappears, another option could be to move ‘unanchored’ comments somewhere.

## Other points

* An alternative simple approach that meets some of the requirements, but has limitations: Make it work on just the HTML output, so could be a js library independent approach. Comments destroyed on rebuild.
