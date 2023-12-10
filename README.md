# Kinetic Modeling and Optimization of a Batch Ethanol Fermentation Process

Doing an Analysis on this paper to determine the best fit for the parameters used in the paper and comparing it to what is described in the paper.

The paper I chose for the analysis is listed above. The citation of paper is as follow:

Oliveira, S. C., Oliveira, R. C., Tacin, M. V., & Gattás, E. A. L. 
(2016). Kinetic modeling and optimization of a batch ethanol fermentation process. 
J. Bioprocess. Biotech, 6(266), 2. DOI: 10.4172/2155-9821.1000266

Because of the high demand of  ethanol in fuel and other uses, there are various processes that are being studied. The aim of these studies is to determine the ideal and optimal conditions for the reactor to be in to produce the most ethanol. Therefore, this paper studies the production of ethanol by the use of a bioreactor containing bacteria cells and substrate. Essentially, in this paper, a mathematical model was used to determine and interpret experimental data from a batch alcohol fermentation process. Moreover in this paper substrate limitations and product inhibition were taken into account when determining the cell concentration and product concentration. Essentially, the substrate (S) is used by the cells (X) to produce the product (E). The paper proposes a kinetic model with a set of coupled ordinary differential equations. These ordinary differential equations have a whole set of parameters which affect the ODEs. Figure 1 shows the set of ordinary differential equations and the parameters that these equations depend on.


########################### Figure 1 Here

Again, in this S is the substrate concentration, X is the cell concentration, and P is the product ethanol concentration. $\hat{\mu}$ is considered the Maximum specific growth rate in the absence of inhibitory effects parameter, $K_S$ is the saturation constant, $K_i$ is the inhibition parameter of sugars, $P_{max}$ is the inhibition parameter for product ethanol, and $n$ is ethanol toxic power. These parameters significantly affect this system of coupled ordinary differential equations.

The paper had the following values for the parameters

############################ Table of Parameters Here.


Morover, some parameters were calculated beforehand and compared to other literature, for example: $\alpha$ = 4.87 g/g. Similarly, $Y_{P/S}$ = 0.4 g/g. My analysis used the same value for these prior calculated parameters and only focused on the 5 parameters mentioned in table 1.

First, I decided to replicate the plot using the parameters provided in the paper. I was able to properly and accurately able to replicate using the plot shown in the paper. Figure 2 shows the concentration of Substrate, Cell and Product as the time change.

########################### Figure 2 Here, Plot of All 3.

However, for my analysis, I decided to focus on product production since the point of attention in this paper is the production of ethanol the product. Therefore, Figure 3 shows only the plot of product with experimental data from the parameters provided in the paper.

########################### Figure 3 Here, Plot of only Product.

