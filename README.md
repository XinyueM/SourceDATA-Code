# SourceData&Code for manuscript
Exploring Single-Cell Biosynthesis Dynamics for Enhanced Production of Proteins and Chemicals

Software:  Wolfram Mathematica 12 or 14 (https://www.wolfram.com/mathematica/trial/)

Download all the data and .nb scripts to your local device. You may need to change the address in the "Import" command line in the .nb scripts to process and plot the data.
# To process experimental data:
Step 1: Open file: "Experimental Data Process Methods.nb";

           Click "Evaluation"
           Click "Evaluate Notebook"    
           
Step 2: Open folder "PlotScripts" and check Figure2 and supplementary figure 4 where experimental data were plotted.

           Click "Evaluation"
           Click "Evaluate Notebook"
            
# To run simulation:
Step 1: Open file: "sub-functions.nb";

This file contains all the functions needed for the simulation. Total time of fermentation (hours) and initial number of cells (numcells) can be set here in the function "metabsetparameters". These two parameters significantly affect the time of simulation. It takes around 3 hours to simulate 500 cells for 24h. To make a quick test, you can set small values of hours and number of cells. 

           Click "Evaluation"
           Click "Evaluate Notebook"    

Step 2: Open file: "main-functions.nb"; Repeat "Evaluate Notebook".

This file executes the simulation step by step. 

First, the function "metabgensteadystate" simulates the initial steady state of all the cells. The output can be used to obtain plots of protein and metabolite distributions and doubling time distributions.  

Second, function "keepallmetabmaintainsteadystate" keeps simulating the steadystate cells for the number of hours you set. The output of this function is mainly used for plotting the auto and cross correlation functions of protein, metabolite, and growth.  

Finally, function "mxcontkilling", simulates the actual fermentation scenario with limited glucose. The output of this function is further used to calculate titer, yield, and productivity. 


Step 3: Open file "Simulation Script.nb"; 

This notebook is organized in the order of Openloop, Egos, Megos, Grofee, and Mefee. You can select any section to evaluate. Each section has three main functions, and it is critical that the evaluation follow the order of "generate," "keep," and "kill," as the later function uses the output of the previous function as the input. The data generated from these simulations were uploaded as a .mx file, which can be imported into the plotting scripts.

# To run simulation with perturbations on protein and growth:
Step 1: Open file Figure 3 and find codes under the red title (*constant protein copy number*) or (*constant growth factor*).

Step 2: Open file "Constant protein sub.nb" and "Constant protein main.nb" if you want to preturb protein copy number. Or, "Constant growth sub.nb" and "Constant growth main.nb" if you want to preturb growth factor.

Similar to the original stochastic model, preturbation simulations use the same main functions with modified sub-functions. To get the cross-correlation you only need to run "metabgensteadystate" and "keepallmetabmaintainsteadystate", while "metabproteinmemfast" is only a sub-function that facilitates plotting. In the sub function notebook you can change the number of cells (numcells) or time for simulation (hours or the fisrt input to call function) or fix protein copy number at a different constant (p=Table[50, {numcells}]). The change we made to the simulation is to keep p at initial value throught all the processes without updating it in the gillespie algorithm as well as before and after cell division. Similarly, in sub-functions of growth pertubation, we fixed growth factor change to be a constant instead of a random draw from a geometic distribution. 

 Step 3: Click "Evaluate Notebook" for both sub and main function notebooks after you made changes.

 Step 4: Go back to Figure 3.nb and evaluate the codes one by one and you can see the result of perturbations. 


# To check plotting:
Open the figure you want to check and repeat "Evaluate Notebook". If you import the data we provided, you can get the exact same plot as shown in the manuscript. However,  if you want to re-run the simulation and make new plots, given the stochastic nature of the simulation, the same command can generate different new data every time you re-run the simulation, especially when the number of cells is small. 
