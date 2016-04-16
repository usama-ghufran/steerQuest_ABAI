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

UPDATE THE MAKE FILE WITH THIS COMMAND INSTEAD:

	g++ main.cpp Boid.cpp Flocking.cpp Simulation.cpp MapLoader.cpp -std=c++0x -D__LINUX_COMPILE -o ../runtime/flock-solve -lopenvdb -lHalf -ltbb -lpthread -lX11 -ldynamic -I./ -L./


##############################
Collision Detection
##############################
1. Use the Scene.h objects/pointers in the files to access start/end positions and other data. Flocking.cpp has a handle to Scene object called sceneMap. getCell(x,y) tells you if there is an obstacle in x,y or not. 
2. Use collisionSDF[x][y] to know how far away x,y  is form the nearest obstacle. Value of 0 mean x,y is on the edge of the obstacle and negative means it's inside . Flocking.cpp
3. use partialDerivatives[x][y] to know the direction away from the nearest osbtacle at positino x,y. Flocking.cpp







