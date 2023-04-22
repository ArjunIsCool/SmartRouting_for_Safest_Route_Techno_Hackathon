# SmartRouting_for_Safest_Route_Techno_Hackathon

A Hackathon Project intended to find the safest route from Point A to Point B based on the regional crime data associated with the route.

For the project we use a openly available crime dataset from the New York Police Department. https://data.cityofnewyork.us/Public-Safety/NYC-crime/qb7u-rbmr
The 2.5 GB Dataset of all New York Crime data was condensed into a 811 KB file which incudes crime/data ratings of 14000 nodes on the map of Manhattan. 
We removed all crimes unrelated to the safety of valuable truck or a car carrying a person of significance. 
We also removed all data before 2016(40% of entries) as well as all data related to age/sex/race of the victim as well as the suspect, description/time/case status/process/case number/jurisdiction code/nearby parks as well as other non required column. 
The Data was limited to Manhattan area as include other boroughs of New York was complicating the mapping
For the remaining type of crimes we assigned a rating between 1-10.0. These crimes had a latitude longitude coordinate which we termed as nodes, these nodes are at intersection of roads and middle of roads.uu We take a cumulative sum of the ratings of all the crime happening at each of these nodes, then took a log of the ratings and normalized that data to a rating from 1-10 (where 1 signifies a safe road, and 10 is an extremely dangerous road).
For the path we use these normalized crime-rating nodes simialar to speed limiters in a shortest route algorithm, where in a car is hypothetically allowed to go at a speed of 100/node-rating kmph on the particular node, so on a safe road (1 rating) it can go at 100 kmph and just and 10 kphm on a dangerous (10 rating) road. After this the Shortest Time algorithm to find the fastest( safest) route for the vehicle.  
We would provide 3 possible routes, The Shortest distance route, the Safest route and a compromise between the two.
We were unable to link our crime-rating dataset with any API to display the maps    