# SourceData&Code for manuscript
Exploring Single-Cell Biosynthesis Dynamics for Enhanced Production of Proteins and Chemicals

Software:  Wolfram Mathematica 12 or 14 (https://www.wolfram.com/mathematica/trial/)

Download all the data and .nb scripts to your local device. You may need to change the address in the "Import" command line in the .nb scripts to process and plot the data.
# To process experimental data:
Step 1: Open file: "Experimental Data Process Methods.nb";

           Click "Evaluation"
           Click "Evaluate Notebook"    
           
Step 2: Open file"Experimental data plotting of figure 2&3"

           Click "Evaluation"
           Click "Evaluate Notebook"
            
# To run simulation:
Step 1: Open file: "sub-functions.nb";

Total time of fermentation (hours) and initial number of cells (numcells) can be set here in the function "metabsetparameters". These two parameters significantly affect the time of simulation. It takes around 3 hours to simulate 500 cells for 24h. To make a quick test, you can set small values of hours and number of cells. 

           Click "Evaluation"
           Click "Evaluate Notebook"    

Step 2: Open file: "main-functions.nb"; Repeat "Evaluate Notebook".

Step 3: Open file "Simulation.nb"; 

This notebook is organized in the order of Openloop, Egos, Megos, Grofee, and Mefee. You can select any section to evaluate. Each section is comprised with three main functions and it is critical that the evaluation follows the order of "generate", "keep", and "kill", as the later function uses the output of previsou function as the input. The data generated from these simulations were uploaded as .mx file, which can be imported to the plotting scripts.

# To check ploting:
Open the figure you want to check and repeat "Evaluate Notebook".
