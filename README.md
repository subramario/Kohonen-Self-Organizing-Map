# Kohonen Self-Organizing Map (KSOM)

This project implements a Kohonen Self Organizing Map that clusters an input set of colors based on their features over a 100 by 100 grid of neurons. The training input set that will be fed to the map is a set of 24 randomly chosen RGB colors, with shades of red, green, blue, teal, pink and yellow. A time varying learning rate is used which is defined as follows:

$\alpha(k) = \alpha_0 exp{(-\frac{k}{T})}$, where $k$ is the current epoch and $T$ is the total number of epochs and  $\alpha_0$ is 0.8


The topological neighbourhood, $N_{i,j}(k)$ of neuron $j$ around the winning neuron $i$ is defined as follows:

$N_{i,j}(k) = exp{(-\frac{d^2_{i,j}}{2 \sigma ^2 (k)})}$, where $\sigma (k) =  \sigma_0 exp{(-\frac{k}{T})}$


In order to explore the effect of $\sigma_0$ (the spread parameter) on the clustering capability of the SOM, the network was trained over the 24 inputs for 1000 epochs for different values of $\sigma_0$, specifically for $\sigma_0 = 1, 10, 30, 50, 70$. The map was then plotted at various epochs to visualize its transition into clustering the input colors.  The SOM transitions can be seen at the bottom of the Jupyter Notebook.