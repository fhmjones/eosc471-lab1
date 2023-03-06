# EOSC471

## Current progress:
### lab review
- review of labs in labs.md file
### Lab 1:
- Matplotlib version uploaded with notes on issues 
- Plotly Version uploaded with notes on issues 
- NOTE, as of March 6, 2023 (FJ), both the matplotlib and plotly versions do run on the open.jupyter.ubc.ca hub. 

## Differences in plotting libraries
|                                        | Plotly                                               | Matplotlib                                                                                                                                                                                           |
|----------------------------------------|------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Animations                             | requires hardcoding functionality (play, pause etc.) | has function for animations                                                                                                                                                                          |
|                                        | logic can be confusing at first                      | animations get rendered as video in html - cant hover on traces                                                                                                                                      |
|                                        |                                                      | function for animation requires external packages - some issues encountered when installing locally                                                                                                  |
| Interactivity (hovering, zooming etc.) | inherent                                             | requires definition of cell types, see compatibility row.                                                                                                                                            |
| Compatibility with Jupyter             | Compatible on both Jupyter notebook and Jupyter Labs | with UBC Jupyter hub's *current* python environment interactivity works well - if package version change in the future the interactivity may not work.                                                                                                                           |
|                                        | no apparent dependency issues                        | with local environments, correct library versions are required - many dependency issues when running on Jupyter Lab locally                                                                          |
|                                        |                                                      | some code may work well under some environments but not others - color map in Lab 1 is an example where the UBC hub environment requires functions that are deprecated in new versions of matplotlib |
| File size                              | large file size when outputs are generated           | file sizes arent too large                                                                                                                                                                           |
## Current Issues and fixes
### Matplotlib
- for matplotlib animations we need to use the FuncAnimation and rc functions. these will render the animation to a video and render it as part of the pages html.

    to be able to render the videos we need to make sure the ffpmeg package is installed. Using conda you can use the following command: 
            conda install -c conda-forge ffmpeg
    using pip: 
            pip install ffmpeg

     Note - we have run in to two issue testing this locally. If nothing works try downloading and installing ffmpeg first https://phoenixnap.com/kb/ffmpeg-windows and then use conda or pip to isntall package to your python environemnt.
     
     Another error that arose is "CondaSSLError: OpenSSL appears to be unavailable on this machine. OpenSSL is required to download and install packages.", in this case then try the solution explained at https://stackoverflow.com/questions/55185945/any-conda-or-pip-operation-give-ssl-error-in-windows-10


- Another required step for matplotlib is definining the cell type for interactive plots (i.e. hovering on plots, animations etc.) 
    - If all packages are up to date as mentioned here: https://github.com/matplotlib/ipympl then %matplotlib widget is used for interactive plots and %matplotlib inline for static plots
    - If packages are not up to date, use %matplotlib notebook when running files on jupyter notebook. In this case on Jupyter lab you might get the following error: Javascript Error: IPython is not defined. 
    - If you get the above error either run all cells with %matplotlib inline or follow https://stackoverflow.com/questions/51922480/javascript-error-ipython-is-not-defined-in-jupyterlab for instructions for updating. You may need to uninstall pillow, MatplotLib and ipympl and resinstall all with conda-forge. Than run jupyter lab build, kill the kernel, close your jupyter lab and reopen everything from the beginning
    - After updating all packages you may get a javascript error, this is a dependancy issue:https://github.com/matplotlib/ipympl/issues/460
        In this case downgrade jupyterlab-widgets and ipywidgets:
        https://github.com/jupyterlab/jupyterlab/issues/12977
        Than run jupyter lab build, kill the kernel, close your jupyter lab and reopen everything from the beginning
        
        
        
- The cm.get_cmap function was deprecated in Matplotlib 3.7, if you are running this code on ubc hub, the matplotlib version is 3.5.2 so you can use this function with no warning. If you run this file on another environment wih a more up to date matplotlib version, use col = matplotlib.colormaps.get_cmap("rainbow")(np.linspace(0, 1, len(t))) and no need to import matplotlib.cm

### Plotly
- animations:

Currently have issue where pressing reset while the animation is playing will erase existing traces, but animation will continue, trace names in this scenario still align to correct trace. The play->pause->reset sequence works great and the play->wait for end of animation->reset also works. https://community.plotly.com/t/overiding-button-action-in-animated-scatter-plot/72469
 


