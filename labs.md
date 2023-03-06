# Review of Matlab files

Summarize all  labs in terms of:

- how straight forward the code will be. Are there complex m files that are used? How hard will it be to convert them?

- any other barriers to converting to Python

## Summary

- Labs 4, 5, and 7 have code that may take a while to translate. Lab 7 uses a toolbox written by Rich Pawlowicz. Lab 4 uses code for the Price-Weller-Pinkel written by Rich as well. Lab 5 has code for raytracing calculations for ocean internal waves written by Rich. There exist attempts on writing Python version equivalents for Lab 4 and 7 code.
- lots of animated plots, specifically lab 5. animations are purely for visualization to help students - how the code is written may not matter too much.
- interactive plots in almost all labs, may not be necessary but are useful for given exact answers to questions.

### student grading and coding requirments
- students hand in pdf version of the .mlx files with their answers to questions.
- most of the labs require only running code and interperating and commenting on ouputs
- all coding done requires reusing given code and changing no more than a few parameters
- some simple math is done with coding (division, square root etc.) and some rearranging of equations (latex)

## Lab 1

### main components
- live animation to watch signal propagated through space
- Heatmaps - hovering on plot is helpful for questions
- regular plots - hovering on plot is helpful for questions

### student grading and coding requirments
- observing plots and answer questions
- simple calculations
- copying code and changing input


### Notes/Summary
Python approaches/issues with animations and hovering documented on readme file.

## Lab 2

### main components
- multiple lines on plots - mainly visual

### student grading and coding requirments
- open ended questions
- simplifying equations (math)
- translating math euqations to code
- writing code for plotting based on code in previous labs
- some math done using code

### Notes/Summary

straigthforward translation to python possible.

## Lab 3

### main components
- uses external m file - this is mainly so workspace doesnt clutter up with long code
- external m file produce heatmap and regular plot - same as lab 1.3
- discrete plots
- some discrete to continous math - should be straightforward in python
- use of w2_22 not clear
- PM_animate.m - animation for sake of learning. No student coding. external file. INstructor mentions there is a difficulty with animations in live editor so this is a sepearte file but Lab 1 has animaitons in live editor.
-  Some more heatmaps and multi line plotting

### student grading and coding requirments
- modifiying exisitng scripts
- solutions and regular document look the same..

### Notes/Summary
- heatmap hovering is not a major component in this lab, but same issue (is hovering important?)
- external files - can be done fairly easily. tested locally and on UBC hub. file test.ipynb calls functions from test.py and test2.ipynb . to create .py file locally you need a spearate editor. on the hub you can create py files no problem
- discrete plots should be straightforward:
https://community.plotly.com/t/plot-of-a-discrete-distribution/20697/5
https://matplotlib.org/stable/gallery/lines_bars_and_markers/stem_plot.html#sphx-glr-gallery-lines-bars-and-markers-stem-plot-py
- w2_22.m - there is a readme mentioning this should not be used. 
- another animation- seems like animation code is given so library used may not matter


## Lab 4

### main components
- another animation (temp vs dist)
- contour plot - hover may be required. can answer questions by eyeballing answer
- pwp.m - all runpwp_ex#.m call this function. extremly slow on MatLab (3 minutes on my computer, note in .mlx file says it can take 4-5 minutes). 

### student grading and coding requirments
- answer questions based on interpratation of plots produced form given code
- modifying paramters in given scripts

### Notes/Summary
- both plotly and matplotlib have contour plots, hovering will be more straightforward with plotly (no need to define cell type)

#### pwp.m
- may require time to translate correctly
- Will need textbook resources on this model to make sure code is correct upon translation.
- There seemes to be an existing python attempt on this that may be worth exploring: https://github.com/earlew/pwp_python_00
- the python link above seems very thorough. Will need to check if the code/model is correct. uses many extra libraries.
- initial impression from pwp.m is that it can be done with only numpy + a plotting library - doesnt need so many extra libraries.

## Lab 5

### main components

- uses some more external m files that will require some time to translate. less intensive the pwp.m, but still long code. very slow code.
- interactive plot based on the m files

### student grading and coding requirments
- answer questions based on interpratation of plots produced form given code
- modifying paramters in given code
- writing code based on previous cprovided code (copy paste plus some modification of parameters)

### Notes/Summary

## Lab 6

### main components
- extrnal .m file used for multi plot animation - static version of plotting also shown. inputs can be changed. plotting is very slow.
- inputs need to be changed and replotted to explore diffusivity
- .mat file for external variables. can load it directly into python: https://stackoverflow.com/questions/874461/read-mat-files-in-python or can translate to csv and load it into python: https://www.mathworks.com/matlabcentral/answers/195151-how-to-convert-a-mat-file-into-a-csv-file
-  BONUS QUESTION: Can you estimate the eddy diffusivity from this data? - no code provided

### student grading and coding requirments
- answer questions based on interpratation of plots produced form given code
- modifying paramters in given code
- writing code for *animations* based on previous provided code (a bit more hands on)

### Notes/Summary
- more interactive plots and code that needs translation - code is simpler than other questions.

## Lab 7

### main components
- uses T-Tide toolbox written by Rich Pawlowicz https://www.eoas.ubc.ca/~rich/#T_Tide

### student grading and coding requirments
- answer questions based on interpratation of plots produced form given code
- no need to write code

### Notes/Summary
- there exists python modules for tidal harmoic analysis:
        https://github.com/sam-cox/pytides
        https://github.com/CNES/pangeo-pytide
- translation of toolbox will be long, using exisitng modules will need thorough review of modules to check for correctness. 
- not many functions from toolbox are used. it may be possible to only write the necessary functions for this lab -> still a copmlex feat

## Lab 8
- answer questions based on interpratation of plots produced form given code
- only small code bits for calculations required 

### main components
- uses .mat file for data. can turn into .csv or upload as is to python
- mainly multi line static plots

### student grading and coding requirments

### Notes/Summary
- shouldnt be an issiue to translate
