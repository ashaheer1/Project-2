# CHE2410 Project 2

# Optimization, Bifurcation and Sensitivity Analysis

## Kinetic Modeling and Optimization of a Batch Ethanol Fermentation Process

Doing an Analysis on this paper to determine the best fit for the parameters used in the paper and comparing it to what is described in the paper.

The paper I chose for the analysis is listed above. The citation of paper is as follow:

Oliveira, S. C., Oliveira, R. C., Tacin, M. V., & Gattás, E. A. L. 
(2016). Kinetic modeling and optimization of a batch ethanol fermentation process. 
J. Bioprocess. Biotech, 6(266), 2. DOI: 10.4172/2155-9821.1000266

Because of the high demand of  ethanol in fuel and other uses, there are various processes that are being studied. The aim of these studies is to determine the ideal and optimal conditions for the reactor to be in to produce the most ethanol. Therefore, this paper studies the production of ethanol by the use of a bioreactor containing bacteria cells and substrate. Essentially, in this paper, a mathematical model was used to determine and interpret experimental data from a batch alcohol fermentation process. Moreover in this paper substrate limitations and product inhibition were taken into account when determining the cell concentration and product concentration. Essentially, the substrate (S) is used by the cells (X) to produce the product (E). The paper proposes a kinetic model with a set of coupled ordinary differential equations. These ordinary differential equations have a whole set of parameters which affect the ODEs. Figure 1 shows the set of ordinary differential equations and the parameters that these equations depend on.

<div align="center">
  <img src="https://github.com/ashaheer1/Project-2/assets/147550852/f44ee7e2-efb7-4878-a066-02d381605db7" width="400">
</div>

**Figure 1. Set of Coupled Ordinary Differential Equations studied in the paper**
########################### Figure 1 Here

Again, in this S is the substrate concentration, X is the cell concentration, and P is the product ethanol concentration. $\hat{\mu}$ is considered the Maximum specific growth rate in the absence of inhibitory effects parameter, $K_S$ is the saturation constant, $K_i$ is the inhibition parameter of sugars, $P_{max}$ is the inhibition parameter for product ethanol, and $n$ is ethanol toxic power. These parameters significantly affect this system of coupled ordinary differential equations.

**The paper had the following values for the parameters:**


<table align="center" border="1">
  <tr>
    <th>Notation</th>
    <th>Unit</th>
    <th>Estimated Value</th>
  </tr>
  <tr>
    <td>$\hat{\mu}$</td>
    <td>$h^{-1}$</td>
    <td>0.5</td>
  </tr>
  <tr>
    <td>$K_s$</td>
    <td>$\frac{g}{L}$</td>
    <td>$6.1\cdot 10^{-3}$</td>
  </tr>
  <tr>
    <td>$K_i$</td>
    <td>$\frac{g}{L}$</td>
    <td>139.7</td>
  </tr>
  <tr>
    <td>$P_{max}$</td>
    <td>$\frac{g}{L}$</td>
    <td>94.2</td>
  </tr>
  <tr>
    <td>$n$</td>
    <td>-</td>
    <td>4.12</td>
  </tr>
</table>




Morover, some parameters were calculated beforehand and compared to other literature, for example: $\alpha$ = 4.87 g/g. Similarly, $Y_{P/S}$ = 0.4 g/g. My analysis used the same value for these prior calculated parameters and only focused on the 5 parameters mentioned in table 1.

First, I decided to replicate the plot using the parameters provided in the paper. I was able to properly and accurately able to replicate using the plot shown in the paper. Figure 2 shows the concentration of Substrate, Cell and Product as the time change.

<div align="center">
  <img src="https://github.com/ashaheer1/Project-2/assets/147550852/3f1442e4-f48d-444d-a22f-7a34485a0df9" width="400">
</div>

**Figure 2. Plot of Substrate, Cell and Product Concentration. Added is the experimental Data**
########################### Figure 2 Here, Plot of All 3.

However, for my analysis, I decided to focus on product production since the point of attention in this paper is the production of ethanol the product. Therefore, Figure 3 shows only the plot of product with experimental data from the parameters provided in the paper.

<div align="center">
  <img src="https://github.com/ashaheer1/Project-2/assets/147550852/7f7499ff-5660-40d6-b24f-bb2f7d859d3a" width="400">
</div>

**Figure 3. Plot of Product Concentration along with experimental Data**
########################### Figure 3 Here, Plot of only Product.


# Minimizing the Parameters to Find the Ideal Fit to the Data

After determining the plot of the product with respect to the parameters defined in the paper, I decided to see if the model fit can be made better. Therefore, I decided to perform a minimize function on the parameters to determine an ideal fit for these parameters and which would lead to the best plot on the experimental data.

After setting the bounds, I was able to determine to the minimized function which produced the ideal fit and gave me the values of the parameters. This led to the following Figure 4.

<div align="center">
  <img src="https://github.com/ashaheer1/Project-2/assets/147550852/ed39d7b7-7506-4876-8f68-82a3b556e8fd" width="400">
</div>

**Figure 4. The Optimized Fit with new Set of Parameters**
########################## Figure 4 Here, Minimized Fit.

As figure 4 shows, the fit is not the most perfect fit. However, it is much better than the fit the paper had, improving the parameters to a much higher degree. The reason for that might be that the paper only performed nonlinear regression on these values to determine the parameters. Therefore, using the numerical methods of odeint and the minimize function led to much better results.

**After minimizing, these were the following parameters:**

<table align="center" border="1">
  <tr>
    <th>Notation</th>
    <th>Unit</th>
    <th>Estimated Value</th>
  </tr>
  <tr>
    <td>$\hat{\mu}$</td>
    <td>$h^{-1}$</td>
    <td>0.4943</td>
  </tr>
  <tr>
    <td>$K_s$</td>
    <td>$\frac{g}{L}$</td>
    <td>$0.8934$</td>
  </tr>
  <tr>
    <td>$K_i$</td>
    <td>$\frac{g}{L}$</td>
    <td>128.348</td>
  </tr>
  <tr>
    <td>$P_{max}$</td>
    <td>$\frac{g}{L}$</td>
    <td>98.564</td>
  </tr>
  <tr>
    <td>$n$</td>
    <td>-</td>
    <td>4.89</td>
  </tr>
</table>

## Flow on a Line and Bifurcation Analysis

After determining the ideal set of parameters. I decided to do a Flow on a Line Analysis and Bifurcation Analysis.

First, a Flow on a Line Analysis led me to the following Figure 5:

<div align="center">
  <img src="https://github.com/ashaheer1/Project-2/assets/147550852/9dd7b5db-6fd7-47c2-aee9-c197db83fe2d" width="400">
</div>

**Figure 5. Flow on a Line Analysis. Showing Steady State**
######################### Figure 5 Here, Flow on a Line Analysis.

Figure 5 shows that all the lines are nearing to a 0 around 98 which led me to believe there is a steady state for the product around 98. Therefore, I decided to do an fsolve analysis and it showed me that the equation is 0 around 98.56, thus confirming that the steady state is around 98.56. Figure 6 shows the result for the fsolve analysis:

<div align="center">
  <img src="https://github.com/ashaheer1/Project-2/assets/147550852/f75310d4-00e0-447a-a38e-da4e8a494667" width="500">
</div>

**Figure 6. Fsolve Analysis showing the value of steady state at optimize parameters**
######################### Figure 6 Here, Fsolve Analysis.

After determining steady state, I decided to do a bifurcation analysis on the system. At first I want to see how the change in Ki would affect the system and how the steady state would change. It led to the following Figure 7 a) . It shows that the system changes steady state. However, the change occurs around -111. Which is out of physical bounds of Ki. I did a similar bifurcation analysis for Ks shown in Figure 7 b), and it led to a similar result around -208, which again is out of physical bounds for Ks. Thus the system does not change steady state as far as Ks and Ki are concerned. However, more complex Bifurcation analysis were done and are shown in the python file.

<div style="display: flex; justify-content: space-between;">
  <img src="https://github.com/ashaheer1/Project-2/assets/147550852/5736d2d7-c9b5-4334-85ae-6a84a341f8a9" width="500">
  <img src="https://github.com/ashaheer1/Project-2/assets/147550852/57836bb1-b743-4e11-9de5-3b79aa21cb76" width="500">
</div>

**Figure 7 a) Bifurcation Analysis of Ki. b) Bifurcation Analysis of Ks.**

######################### Figure 7 Here, a and b, The two bifurcation Analysis.

## Sensitivity Analysis on the System

Lastly, I performed a sensitivity analysis on the system by changing the parameters values by **1%**, **5%**, and **10%**. I changed the parameters in both directions, by negative percentage and positive percentage. The plots' legends show the appropriate direction change the parameters. 


### 1% Sensitivity.

Figure 8 show how the system changes by 1% change in each parameter. As it can be seen, there is not much visibile difference and the the plot was zoomed in in the appropriate area. Figure 9 shows the zoomed in plot showing the sensitivity of each parameter at 1%.

<div style="display: flex; justify-content: space-between;">
  <img src="https://github.com/ashaheer1/Project-2/assets/147550852/5d5c173c-6fe9-465f-a8e6-6bb480717328" width="500">
  <img src="https://github.com/ashaheer1/Project-2/assets/147550852/3db3f3df-04eb-4503-9dbe-091f933397dc" width="500">
</div>

**Figure 8. 1% Sensitivity Analysis on the Parameters in both directions**

######################### Figure 8 Here, 1% change


<div style="display: flex; justify-content: space-between;">
  <img src="https://github.com/ashaheer1/Project-2/assets/147550852/7926d266-d63d-4c6b-9462-24329b08a04e" width="500">
  <img src="https://github.com/ashaheer1/Project-2/assets/147550852/7a4ec444-48b9-492d-8308-ab1783020181" width="500">
</div>

**Figure 9. 1% Sensitivity Analysis zoom to show where the most deviation occurs**

######################### Figure 9 Here, zoomed in 1% change.


### 5% Sensitivity

Similarly, 5% change in the parameter values were plotted to see which one is the most sensitive. This is shown in Figure 10

<div style="display: flex; justify-content: space-between;">
  <img src="https://github.com/ashaheer1/Project-2/assets/147550852/2a6271b8-4c08-4dc7-a761-f0cb02904d05" width="500">
  <img src="https://github.com/ashaheer1/Project-2/assets/147550852/c6988e33-2646-455a-bc10-6abe40ecd826" width="500">
</div>

**Figure 10. 5% Sensitivity Analysis on the Parameters in both directions**

######################### Figure 10 Here, 5% change

### 10% Sensitivity

Lastly, 10% change in the parameter values in both directions were plotted as shown in Figure 11.

<div style="display: flex; justify-content: space-between;">
  <img src="https://github.com/ashaheer1/Project-2/assets/147550852/bebe398b-b579-474e-a087-ff77bd0ebc87" width="500">
  <img src="https://github.com/ashaheer1/Project-2/assets/147550852/f5b6ebd7-a0d0-4fd3-b88e-5fb4238656ff" width="500">
</div>

**Figure 11. 10% Selectivity Analysis on the Parameters. Percent changes in both direction**

######################### Figure 11. 10% change.


## Global Sensitivity Analysis

After local sensitivity analysis, Global sensitivity analysis was conducted. Figure 12 shows the plot for 20% variation in the parameters which were considered in this analysis. Moreover, Figure 13 shows the uniform distribution for all the parameters that are in the analysis and were thus considerd in the global sensitivity. 

<div align="center">
  <img src="https://github.com/ashaheer1/Project-2/assets/147550852/797e3a0a-ebd5-4d4f-ad0f-602a0258d152" width="500">
</div>

**Figure 12. Global Sensitivity Plot for the parameters.**

############################ Figure 12. Global Sensitivity Plot

<div align="center">
  <img src="https://github.com/ashaheer1/Project-2/assets/147550852/f69087e2-5b9c-4842-8a62-0474c371f042" width="500">
</div>

**Figure 13. Uniform Distribution Plot in order to perform Global Sensitivity Analysis on the System.**
########################### Figure 13. uniform distribution plot


These two figures led me to perform least square regression to estimate the normalized parameters. This equation shows which parameter has the most and least effect on our system. Figure 14 shows the result of the least square regression through linear algebra and OLS Analysis. The result agrees with the local sensitivity analysis that $P_{max}$ and $n$ has the highest effect on the system since their value is the highest and $K_s$ and $K_i$ have the least effect since their value is so low. Moreover, the p-value of $K_s$ and $K_i$ is too high and thus they must be discarded.

<div align="center">
  <img src="https://github.com/ashaheer1/Project-2/assets/147550852/faac8f93-a95b-4ad4-96a1-aa1c97e135dc" width="500">
</div>

**Figure 14. Linear Algebra and OLS Analysis result of Global Sensitivity Analysis.

########################### Figure 14. OLS Analysis



### Sensitivity Analysis Conclusion

As it can be seen from the plots, Parameter $P_{max}$ and $n$ have the highest sensitivity to the system of differential equations. Therefore, these parameters must be studied more. Moreover, it is also evident from the plot that $K_s$ is least sensitive since even changing it 10% did not affect the system at all. Therefore, it can be concluded that $K_s$ is not an important parameter and could be disregarded in some cases.



## Conclusion

Overall, the analysis looked at a set of coupled ordinary differential which were a kinetic model for production of ethanol in a biomass batch reactor with substrate and cell present. We first plotted the data using the parameters estimated by the paper. Then we minimized the parameters and fitted the experimental data, producing better parameters. Then we did a bifurcation analysis to determine how the steady state changes with change in a parameter. Lastly, we did sensitivity analysis to determine which parameter change affect the system the most. The result showed that the parameters $P_{max}$ and $n$ were the most sensitive parameter and must be studied more. On the other hand parameter $K_s$ had the least effect on the system and thus the system is not sensitive to change in $K_s$ parameter.

Further analysis must be done on this system and the parameters minimzed using other tools to exclusively determine the best parameter fit to the data. Moreover, in this analysis, only a simple bifurcation analysis was conducted. In the future, more in-depth bifurcation analysis could be conducted on all the parameters to better understand how the system's steady state changes with changes in the parameter values.


