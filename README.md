# Kohonen Self-Organizing Map (KSOM)

This project implements a Kohonen Self Organizing Map that clusters an input set of colors based on their features over a 100x100 grid of neurons. The training input fed to the map is a set of 24 randomly chosen RGB colors, with shades of red, green, blue, teal, pink and yellow. The RGB scale for each color was converted into an equivalent bounded scale between 0 and 1. A time varying learning rate is used which is defined as follows:

![equation](https://latex.codecogs.com/gif.latex?%5Calpha%28k%29%20%3D%20%5Calpha_0%20exp%7B%28-%5Cfrac%7Bk%7D%7BT%7D%29%7D)

where *k* is the current epoch, *T* is the total number of epochs and ![equation](https://latex.codecogs.com/gif.latex?%5Cfn_phv%20%5Calpha_o) is 0.8

The topological neighbourhood, N<sub>i,j</sub>(k) of neuron *j* around the winning neuron *i* is defined as follows:

![equation](https://latex.codecogs.com/gif.latex?N_%7Bi%2Cj%7D%28k%29%20%3D%20exp%7B%28-%5Cfrac%7Bd%5E2_%7Bi%2Cj%7D%7D%7B2%20%5Csigma%20%5E2%20%28k%29%7D%29%7D%5C%3B%5C%3Bwhere%5C%3B%5C%3B%5Csigma%20%28k%29%20%3D%20%5Csigma_0%20exp%7B%28-%5Cfrac%7Bk%7D%7BT%7D%29%7D)

In order to explore the effect of ![equation](https://latex.codecogs.com/gif.latex?%5Csigma_0) (the spread parameter) on the clustering capability of the SOM, the network was trained over the 24 inputs for 1000 epochs for different values of ![equation](https://latex.codecogs.com/gif.latex?%5Csigma_0), specifically for ![equation](https://latex.codecogs.com/gif.latex?%5Csigma_0) = 1, 10, 30, 50, 70. The map was then plotted at various epochs to visualize its transition into clustering the input colors.  The SOM transitions can be seen at the bottom of the Jupyter Notebook.

The spread parameter decreases as the number of epochs increases due to its decaying nature, which directly decreases the neighborhood size. As the neighborhood size decreases, the clusters become more distinct from one another. A higher spread parameter results in a larger cluster size for each color, which produces a finer map with seamless transitions between different clusters of colors. Conversely, a lower spread parameter results in smaller neighborhood sizes and more pronounced boundaries between clusters.
