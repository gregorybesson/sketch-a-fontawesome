# sketch-a-fontawesome
Using AI (a Deep Learning Convolutional Neural Net) to help you find fontawesome icons by drawing !

# Introduction
For those knowing http://fontawesome.io/, it's quite complicated to find the icon you want: Hundreds of icons exist and find the one can be tricky.

These icons have been tagged so that you can ease your search with keywords. But it's not a killer feature.

What if you could sketch rapidly what you want to see and dynamically display icons ressembling your sketch ?
This is the goal of this project :)

# How I will do it
A very good paper has been written on the subject, sketch-a-net: 
- https://arxiv.org/pdf/1501.07873.pdf
- http://www.eecs.qmul.ac.uk/~tmh/papers/yu2016sketchanet.pdf

I will build a Convolutional Neural Net to learn icons (see below) but before, I need to prepare my data. This will be the tricky part !

# Steps
## Prepare the data
The fontawesome set is composed by 675 SVG icons. Each of these icon will represent a label (ie. fa-rocket). But to train my AI, I need diversity in my dataset... So I'll have to build it.

- I will use the vector nature of the icons to deconstruct them and create 10 variations of each icon based on its strokes.
- I will then transform each icon as a png image and will rotate and blur(? maybe not) these images 24 times (8 rotations X 3 blur levels)
- For 1 label, I'll then have 240 different images, ready to be trained !

### Extract SVG from fontawesome
I use https://icomoon.io to extract individual SVG. I obtain 675 icons on svg format.

## Build the CNN
I will use Tensorflow to build the CNN. 
I need GPU's for performance of my training step. My CNN will be composed by several Convolutional layers which are CPU (GPU) intensive.

I will follow the YU, YANG, SONG, XIANG and HOSPEDALES study, the CNN will be built with these parameters:

![Screenshot](/screenshot.png?raw=true)

## Train the data (choose the hyperparameters)
TBD

## Test the AI
TBD

## Build the sketchpad
TBD (I'll use a canvas based project, don't know which one yet)

## Create the website to search fontawesome icons and offer it to the community
It will be based on Abe, of course :)

## Enjoy !

