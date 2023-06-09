# GNR633Project_QGISPlugin

Created a first iteration (simplistic and preliminary version) of a QGIS Plugin to implement the fuzzy inference system directly within QGIS instead of the current method of exporting to MATLAB, performing computation, and then re-importing into GIS systems.


## Features of the plugin realized - 

1. Identify Factors : Identifying the factors that affect the system (inputs as number of factors and corresponding number of variables for each of them)
   - NOTE: Assumption here - 
      Hardcoded 2 input factors and 3 variables for each of these 2 factors as well as the output factor.
   - Reason and feasibility of the assumption to be overcome -
     - Reason - Researched a lot but couldn’t figure out how to make a dynamic GUI such that QLabels and QLineEdits appear on the plugin interface. The nearest I could get to a dynamic GUI was pasting in QLineEdits but that wouldn’t help here.
     - Feasibility to overcome - When we can figure out how to make the GUI dynamic.
 
 2. Membership Functions : Provision to label each of the variables for the inputs as well as output factor 
 
 3. Membership Functions (contd.) : Choosing a membership function for each of them from the following options - Piecewise Linear, Sigmoid, Gaussian, Quadratic and Cubic polynomial
    - NOTE - Assumption here - 
      Hardcoded Piecewise linear function=> y=0.1x (Domain: [0,10] and Range: [0,1]
    - Hardcoded parameters of the gaussian=> mean = 0  and standard deviation = 1
    - Reason and feasibility of the assumption to be overcome -
      - Reason - Just the time constraint
      - Feasibility to overcome - Can easily modify a few lines of code to allow users to define all parameters of the functions they want.

4. Fuzzy Rules : Provision to add fuzzy rules governing the system.
   - NOTE - Assumption here - 
     Hardcoded provision for only 1 fuzzy rule for now.
   - Reason and feasibility of the assumption to be overcome -
     - Reason - Just the time constraint
     - Feasibility to overcome - Very simple. All I have to do is add to the GUI and put a condition before calculation of the final fuzzy output to add up all of these answers from each fuzzy rule.

5. Feature Vector : Series of steps - Input data —-> calculate the fuzzy values for each factor —-> apply the operation defined in the fuzzy rule —-> get the fuzzy value of the output factor —-> Defuzzify by the centroid location method.
   - NOTE - Assumption here - 
   - Defuzzification by the centroid method is implemented only for the piecewise linear - piecewise linear - piecewise linear combination of the 2 input factors and 1 output factor. 
   - Reason and feasibility of the assumption to be overcome -
     - Reason - Couldn’t figure out how to implement the centroid method without extensive geometrical considerations and mathematical calculations. 
     - Feasibility to overcome - A little unclear to me at the moment, but I believe I can use integration and make the problem simpler in future iterations.

## Images of the working plugin - 
1. <img width="255" alt="image" src="https://github.com/PrakritiShetty/GNR633Project_QGISPlugin/assets/73118229/6bef3afa-0737-4b1d-93a8-583791634231">
2. <img width="255" alt="image" src="https://github.com/PrakritiShetty/GNR633Project_QGISPlugin/assets/73118229/c447c87e-a2c9-42c4-9b80-e10642dce503">
3. <img width="259" alt="image" src="https://github.com/PrakritiShetty/GNR633Project_QGISPlugin/assets/73118229/2f4753e6-b5ad-4e2e-a38d-10c009ffc26e">
4. <img width="255" alt="image" src="https://github.com/PrakritiShetty/GNR633Project_QGISPlugin/assets/73118229/9ebc6238-5067-4494-94e2-6cdc1a2fd090">
 
