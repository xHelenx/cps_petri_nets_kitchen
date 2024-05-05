# cps_petri_nets_kitchen
A collection of petri nets modelling a robot kitchen

---- 

## Installation
Before running the model, it is necessary to install [RENEW](www.renew.de)

## Running experiments

1. Start the RENEW GUI
1. In order to execute the net, select the formalism type "timed java compiler" 
2. Then initialize the experiment you would like to execute, by opening the kitchen net
3. navigate to the init transition in the bottom left corner
4. edit the init transition: 
	- You can edit the tool assignment for each robot 1-4: When initializing the robot set the value to 1 for each tool the robot should be able to handle. 

            #The order is (knife, masher, cstation, hand, peeler,feet)
            station1:new robot;
            station1:init(1,1,0,0,1,0);

	- You can select a heuristic ("lastTool", "random", "minTime", "minBookings" like this
            
            heuristic = "minBookings";

    - You can edit the amount of meals to be cooked by navigating further down in the kitchen on the left side to the place "incoming Orders" - adjust the meals by adding  a "1" for recipe 1 and a 2 for recipe. You can then also have change the place #totalOrders to the chosen number of meals. 
    - 
5. Now run the simulation (Ctrl+R). 
6. To obtain the results copy the last step of the simulation trace and store them as a .txt file with the naming rule
    
        <heuristic>_<experimentRun>_<totalTime>.txt - e.g. random_01_3333.txt

7. Run the **analysis.ipynb** notebook to analyse the results. 
