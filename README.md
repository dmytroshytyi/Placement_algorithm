# Placement_algorithm
## Introduction
Increasing demand on different network services makes network operators and big companies to increasethe number and variety of complex proprietary hardware. The combination of increasing operational costs,complex integration and maintenance of such hardware is strong limitation of increasing services. Networkfunction vitalization introduces the different way to architect networks. This technology aims to convertdifferent  network  hardware  with  specific functions  as  a  virtual  services  that  are  running  on the  generalpurpose servers (GPS), network nodes such that those services could be moved to a different locations inthe network instead of needing the installation of new equipment.To make available the transition from the various complex proprietary hardware to easy managed software(virtual  functions/services)  on  the  GPS,  Network  Function  Virtualization  platforms  as  OpenStack appeared. While services require to be properly managed, coordinated, arranged and resources require to be aggre-gated, problems related to automation of network, storage, performance and provisioning appear. Frequentlyautomation closely relates to an orchestration (coordination of the resources and networks needed to set upcloud-based services, applications). Correspondingly the entity responsible for orchestration tasks withoutrequiring direct human interaction is defined as orchestrator.To be able to perform orchestration tasks OpenStack includes the orchestration (Manegement and Or-chestration) service based on MANO framework. Normally orchestrators could be responsible(supervision) for multiple OpenStack clusters. 

## In this repository we provide an implementation of placement algorithm for VNF orchestrators. 
In practice, the most common approach to solve the type of such problems, is described in method that iscalled "Lloyd’s Algorithm". This method could give an optimal solution with NP-hard complexity. On each iteration the the center of mass of the k domains that are represented by k orchestrators is a solution. These centers are used for a re-clustering. The iterations repeat until the algorithm is converged. We combine "Voronoi iteration" solution with the Relative Point Centrality (RPC). Where:

	- "Voronoi iteration" - is a partitioning of a plane into regions based on distance to points in a specificsubset of the plane.
	- relative point centrality was suggested by Beauchamp.

## How to choose the topology:
The program can generate a topology based on the described in the paper(Augmenter la disponibilité des orchestrateurs VNF-Dmytro Shytyi et Luigi Iannone) model or you may feed the topology in the csv file in the next format:

	NODE1, NODE2, Latency between NODE1 and NODE2
	NODE3, NODE2, Latency between NODE3 and NODE2
	NODE4, NODE3, Latency between NODE4 and NODE3



*Note that nodes (NODE1 and NODE2) can have as digits as characters in the name. Latency between nodes is a numeric value.


## Dependecies:
ARCHLINUX:

	- pacman -S tk

	- yaourt python-networkx-1.11 1.11-1

 	- yaourt install decorator
	
	- yaourt python-numpy

	- sudo pip install "matplotlib<3"
UBUNTU:
	
	- #apt-get install python3-tk
	- #apt-get install python3-networkx
	- #apt-get install python3-venv
	- #pip install "matplotlib<3"
	
## Other
Autors:

	Dmytro Shytyi;
	Luigi Iannone;
	
		site: https://dmytro.shytyi.net
		
		mail: contact.dmytro@shytyi.net
		
License: 

	GPL.
## Screenshots
Initial window where we set the parameters:
![alt text](https://github.com/dmytroshytyi/Placement_algorithm/blob/master/Screenshot1.png "Screenshot 1")
The topology is displayed in the screen below:
![alt text](https://github.com/dmytroshytyi/Placement_algorithm/blob/master/Screenshot2.png "Screenshot 2")
Result of the placement is presented below. In the appeared rectangle you may find the place(name of the nodes) where you should place the orchestrators:
![alt text](https://github.com/dmytroshytyi/Placement_algorithm/blob/master/Screenshot3.png "Screenshot 3")
