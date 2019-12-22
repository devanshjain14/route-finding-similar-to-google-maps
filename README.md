# Route Finding Similar To Google Maps

#### This was implemented under the valuable guidance of Prof David Crandall at Indiana University in B551 Elements of AI during Fall 2019.

This part had 4 parts. It optimizes segments, distance, time, Mileage per gallon. One major challenge was to extract and store all the road segments and city gps to a python list and at the same time handling all the cases of inconsistency in data. We also had to  list the back and forth routes, for example, if a route is given from city A to B, we had to make sure our algorithm includes the path from B to A as well. In this process, we also avoided the loop of going from A to B and then again B to A.

To maximize/minimize the cost function(s), we implemented this problem using the Priority Queue. We created four different functions for each of the cost functions and called them according to the command line input.

Our successor function returned the set of all possible destinations from the current city. And then, each of these cities was added to the fringe and checked for their optimality in the corresponding cost function.

### Optimizing Segments
We minimize the number of segments by choosing the route segment which minimizes the total number of segments traversed.

### Optimizing Distance
We optimize the distance by choosing the route segment which minimizes the total distance traversed.

### Optimizing Time
We minimize the time by choosing the route segment which minimizes the total travel time, given the car, travels at full speed throughout the journey.

### Optimizing Mileage Per Gallon( MPG )
We maximize the MPG by choosing the route segment which maximizes the Mileage. Since, MPG is a function of velocity and average velocity is the total distance traveled upon total time, which is used to maximize the MPG


### To run the code

./route.py [start-city] [end-city] [cost-function]

where 

where:
 start-city and end-city are the cities we need a route between.
 cost-function is one of:
- segments tries to nd a route with the fewest number of \turns" (i.e. edges of the graph)
- distance tries to nd a route with the shortest total distance
- time tries to nd the fastest route, for a car that always travels at the speed limit
- mpg tries to nd the most economical route, for a car that always travels at the speed limit and whose mileage per gallon (MPG) is a function of its velocity (in miles per hour).

Output will be corresponding to : [total-segments] [total-miles] [total-hours] [total-gas-gallons] [start-city] [city-1] [city-2] ... [end-city]
