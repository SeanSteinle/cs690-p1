# MiniProject 1

Objective: The objective of this project is to get you oriented in modeling V2X systems using SUMO traffic simulation. Note that you do not need to use Carla in this project, but you should get familiar with it.

Here are some links to get you started:
*	SUMO installation: https://github.com/eclipse/sumo
*	CARLA installation: https://carla.readthedocs.io/en/latest/start_quickstart/#carla-installation (May require linking your Github Account with Epic Games and Joining their team EpicGames/developers)

How to begin:
1.	Download SUMO and install on your machine.
    *	There are many YouTube videos and tutorials on how to use SUMO.
2.	Select a part of the Open Street Map or select a town map from Carla.
    *	www.openstreetmap.org
    *	All Carla maps ares inside OpenDrive folder within content/Carla/Maps
    *	Become familiar with the notation and follow tutorials
3.	Ensure that vehicles can run on the map. This is because, being a contributed map, some aspects of the map are not complete. You will need to use NetEdit and complete all the intersections etc., so that all traffic can flow from the starting point to the ending point.
    *	https://sumo.dlr.de/docs/netedit.html
4.	Select day time; AM/PM (high traffic in one direction vs. the other) and low traffic rate traffic flows on the main roadway you choose and simulate the runs of traffic.
    *	Become familiar with the system
5.	If you can find traffic flows published by VDOT use them, else make up the flow rates.
Your Experiment:
1.	Change the signal phase timing under the default fixed cycle time from 90 Seconds to
    *	70 seconds
    *	110 seconds
    *	For each of these settings collect the following traffic characteristics on each of the (say northbound and southbound) directions for AM, PM and low traffic flow durations on the main arteries and all intersecting roads of a 4-way intersection.
        -	Average flow rate
        -	Average inter-vehicular distance
        -	Vehicular densities
2.	Do the same analysis for actuated signals and answer the question: Did signal articulation increase or decrease the congestion? Justify using your analytical results.
3.	EXTRA CREDIT: Can you implement synchronized signals on the main artery?
a.	Answer the question: Did signal synchronization increase or decrease congestion?
What to turn in:
1.	The OSM map.
2.	Traffic statistics (in tabular form)
3.	A writeup of your conclusions, including answers to questions listed under the “Your Experiment” section.


## Open Street Map

I [exported the area](https://www.openstreetmap.org/export#map=17/38.854096/-77.329170) near I66 in Fairfax where Route 50 and Route 29 merge.

```bash
# Convert to SUMO format
netconvert --osm-files Fairfax_50_29.osm -o Fairfax_50_29.net.xml
```

```bash
# To edit the network
netedit -s Fairfax_50_29.net.xml
```

Helpful doc: [Driving in Cirlces](https://github.com/eclipse-sumo/sumo/blob/main/docs/web/docs/Tutorials/Driving_in_Circles.md).

[Daily Traffic Data](https://www.arcgis.com/apps/mapviewer/index.html?webmap=bff29e1bc0fd4908b2c035fe67695088)


[Output Reference](https://sumo.dlr.de/docs/Simulation/Output/Lane-_or_Edge-based_Traffic_Measures.html)

## Setting the Flow


We are observing Braddock Rd outside of GMU, specifically the main intersection with Route 123.

Morning: east - 5000, west - 1000



Evening: east - 1000, est - 1000

Low: both 1000


```bash
sumo-gui -n Generated_Braddock_GMU.net.xml -r Generated_Braddock_GMU.rou.xml
```
