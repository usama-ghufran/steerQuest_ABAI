######################
GENERAL INSTRUCTIONS
#######################

This is a sample stub, to help you get started with the problem.
YOU DO NOT NEED TO USE THIS. BUT, MAKE SURE YOU SEND THE DATA REQUIRED IN THE RIGHT FORMAT FOR BLENDER.

We are using Blender as our Viewport. 
A server listens on localhost:8010 from blender, expecting a vector of 'Boid' objects.


##########################
SEND DATA TO BLENDER
###########################
It is mandatory to use the function 'Simulation.ToBlender()' for visualization.

Mandatory fields to populate
- vector<Boid> boids
---- boids.loc
---- boids.orient
---- boids.reachedDestination

###############################

LEVELS	

################################
Level 0

Take the sheep moving from source to destination. Make sure they follow the rules of flocking!
Populate the vector of 'Boid'.

Level 1

The sheep must navigate static obstacles, as they go from source to destination, while maintaining the flock.
Use MapLoader.cpp for accessing the VDB library. The scene/obstacles information is supplied as a VDB.

Level 2

There is a moving obstacle now. Remember the sheep code.
Use the vector 'obstacles' to get your dynamic obstacle position at each time step.

Level 3

Navigate to the destination by crossing more obstacles. How much do your sheep love the Fellowship?


##############################
COMPILING INSTRUCTIONS
##############################

1. Build your code - make
2. Run the run_scene<level>.sh
If you get linker errors, make sure you set LD_LIBRARY_PATH to path of the dynamic .so file.




