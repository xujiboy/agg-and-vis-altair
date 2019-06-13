# agg-and-vis-altair
An example repo showcases how to use pandas preprocessing and altair to visualize large dataset

## Intro
In this example, we carried out an experiment to see how fast the altair visualization output json file increases in size as we increase the size of input data.

## Visualization Target
We are using an Gaussian-like 2D array as our visualization target example. ![2d gaussian](/img/2d_gaussian.png)

 The targeted type of data we are concerned in general are those with 2D locational data (x, y) and one or more location-related attributes (value1, value2, ...), which can be ideally visualized as heatmaps. This sounds straight-forward enough as a visualization task with Altair, but as the input data becomes large (e.g. > 1,000,000 rows) the output `json` object (which I personally think is undeniably one of the most attractive features of Altair / Vega / Vega-Lite ecosystem) becomes quite large on-disk (hundreds of MB or even several GB), meanwhile the visualization runtime cost also becomes noticeably high. The large size of `json` files also makes it very inconvenient to port to or embed inside a frontend.

## Summary
For computation efficiency and porting convenience purposes, it is better to do some preprocessing to aggregate and reduce the input data size for charting.


## How to Run
- use virtualenv to install the requirement
``` 
virtualenv --python=3.7 .venv
source .venv/bin/activate
pip3 install -r reqirement.txt
```
- run `jupyter lab`:
```
jupyter lab
```
- open the ipynb and run all the cells in sequence.