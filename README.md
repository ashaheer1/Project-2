# Kinetic Modeling and Optimization of a Batch Ethanol Fermentation Process

Doing an Analysis on this paper to determine the best fit for the parameters used in the paper and comparing it to what is described in the paper.

The paper I chose for the analysis is listed above. The citation of paper is as follow:

Oliveira, S. C., Oliveira, R. C., Tacin, M. V., & Gattás, E. A. L. 
(2016). Kinetic modeling and optimization of a batch ethanol fermentation process. 
J. Bioprocess. Biotech, 6(266), 2. DOI: 10.4172/2155-9821.1000266

Because of the high demand of  ethanol in fuel and other uses, there are various processes that are being studied. The aim of these studies is to determine the ideal and optimal conditions for the reactor to be in to produce the most ethanol. Therefore, this paper studies the production of ethanol by the use of a bioreactor containing bacteria cells and substrate. Essentially, in this paper, a mathematical model was used to determine and interpret experimental data from a batch alcohol fermentation process. Moreover in this paper substrate limitations and product inhibition were taken into account when determining the cell concentration and product concentration. Essentially, the substrate (S) is used by the cells (X) to produce the product (E). The paper proposes a kinetic model with a set of coupled ordinary differential equations. These ordinary differential equations have a whole set of parameters which affect the ODEs. Figure 1 shows the set of ordinary differential equations and the parameters that these equations depend on.


########################### Figure 1 Here

Again, in this S is the substrate concentration, X is the cell concentration, and P is the product ethanol concentration. $\hat{\mu}$ is considered the Maximum specific growth rate in the absence of inhibitory effects parameter, $K_S$ is the saturation constant, $K_i$ is the inhibition parameter of sugars, $P_{max}$ is the inhibition parameter for product ethanol, and $n$ is ethanol toxic power. These parameters significantly affect this system of coupled ordinary differential equations.

**The paper had the following values for the parameters: $\hat{\mu}$ = 0.5, $K_S$ = 6.1 $\cdot$ 10 $^-3$, $K_i$ = 139.7, $P_{max}$ = 94.2, and $n$ = 4.12**


Morover, some parameters were calculated beforehand and compared to other literature, for example: $\alpha$ = 4.87 g/g. Similarly, $Y_{P/S}$ = 0.4 g/g. My analysis used the same value for these prior calculated parameters and only focused on the 5 parameters mentioned in table 1.

First, I decided to replicate the plot using the parameters provided in the paper. I was able to properly and accurately able to replicate using the plot shown in the paper. Figure 2 shows the concentration of Substrate, Cell and Product as the time change.

########################### Figure 2 Here, Plot of All 3.

However, for my analysis, I decided to focus on product production since the point of attention in this paper is the production of ethanol the product. Therefore, Figure 3 shows only the plot of product with experimental data from the parameters provided in the paper.

########################### Figure 3 Here, Plot of only Product.


# Minimizing the Parameters to Find the Ideal Fit to the Data

After determining the plot of the product with respect to the parameters defined in the paper, I decided to see if the model fit can be made better. Therefore, I decided to perform a minimize function on the parameters to determine an ideal fit for these parameters and which would lead to the best plot on the experimental data.

After setting the bounds, I was able to determine to the minimized function which produced the ideal fit and gave me the values of the parameters. This led to the following Figure 4.

########################## Figure 4 Here, Minimized Fit.

As figure 4 shows, the fit is not the most perfect fit. However, it is much better than the fit the paper had, improving the parameters to a much higher degree. The reason for that might be that the paper only performed nonlinear regression on these values to determine the parameters. Therefore, using the numerical methods of odeint and the minimize function led to much better results.

After minimizing, these were the following parameters: $\hat{\mu}$ = 0.4943, $K_S$ = 0.8934, $K_i$ = 128.348, $P_{max}$ = 98.564, and $n$ = 4.89.


## Flow on a Line and Bifurcation Analysis

After determining the ideal set of parameters. I decided to do a Flow on a Line Analysis and Bifurcation Analysis.

First, a Flow on a Line Analysis led me to the following Figure 5:

######################### Figure 5 Here, Flow on a Line Analysis.

Figure 5 shows that all the lines are nearing to a 0 around 98 which led me to believe there is a steady state for the product around 98. Therefore, I decided to do an fsolve analysis and it showed me that the equation is 0 around 98.56, thus confirming that the steady state is around 98.56. Figure 6 shows the result for the fsolve analysis:

######################### Figure 6 Here, Fsolve Analysis.

After determining steady state, I decided to do a bifurcation analysis on the system. At first I want to see how the change in Ki would affect the system and how the steady state would change. It led to the following Figure 7 a) . It shows that the system changes steady state. However, the change occurs around -111. Which is out of physical bounds of Ki. I did a similar bifurcation analysis for Ks shown in Figure 7 b), and it led to a similar result around -208, which again is out of physical bounds for Ks. Thus the system does not change steady state as far as Ks and Ki are concerned. However, more complex Bifurcation analysis were done and are shown in the python file.

######################### Figure 7 Here, a and b, The two bifurcation Analysis.

## Sensitivity Analysis on the System

Lastly, I performed a sensitivity analysis on the system by changing the parameters values by **1%**, **5%**, and **10%**. I changed the parameters in both directions, by negative percentage and positive percentage. The plots' legends show the appropriate direction change the parameters. 


### 1% Sensitivity.

Figure 8 show how the system changes by 1% change in each parameter. As it can be seen, there is not much visibile difference and the the plot was zoomed in in the appropriate area. Figure 9 shows the zoomed in plot showing the sensitivity of each parameter at 1%.

######################### Figure 8 Here, 1% change
######################### Figure 9 Here, zoomed in 1% change.


### 5% Sensitivity

Similarly, 5% change in the parameter values were plotted to see which one is the most sensitive. This is shown in Figure 10

######################### Figure 10 Here, 5% change

### 10% Sensitivity

Lastly, 10% change in the parameter values were plotted as shown in Figure 11.

######################### Figure 11. 10% change.


As it can be seen from the plots, Parameter $P_{max}$ and $n$ have the highest sensitivity to the system of differential equations. Therefore, these parameters must be studied more. Moreover, it is also evident from the plot that $K_s$ is least sensitive since even changing it 10% did not affect the system at all. Therefore, it can be concluded that $K_s$ is not an important parameter and could be disregarded in some cases.


Overall, the analysis looked at a set of coupled ordinary differential which were a kinetic model for production of ethanol in a biomass batch reactor with substrate and cell present. We first plotted the data using the parameters estimated by the paper. Then we minimized the parameters and fitted the experimental data, producing better parameters. Then we did a bifurcation analysis to determine how the steady state changes with change in a parameter. Lastly, we did sensitivity analysis to determine which parameter change affect the system the most. The result showed that the parameters $P_{max}$ and $n$ were the most sensitive parameter and must be studied more. On the other hand parameter $K_s$ had the least effect on the system and thus the system is not sensitive to change in $K_s$ parameter.


