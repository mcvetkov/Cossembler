# Cossembler
Cossembler - rapid prototyping tool for co-simulations of energy systems

Cossembler is written in Python 3 and published under GPL 2.0.

Cossembler is intended for rapid prototying of co-simulations for energy system integration studies. Co-simulation is a combination of two or more simulation tools or computational models, and Cossembler provides easy means of their integration. Cossembler goal is not high computational performance, but instead, fast assembly of a co-simulation prototype.

Cossembler architecture is minimalistic, defining only the most relevant features. The user is welcomed to extend its capabilities as needed.

Cossembler is a block-modeling tool, and hence, it is intended to be used by defining and connecting blocks into a co-simulation. These blocks link to different tools in the background.

Cossembler architecture is developed in layers, with each layer serving a different purpose: the engine layer, the adapter layer, the functionality layer and the application layer.

Engine layer - This is the Cossembler engine which enables block modeling phylosophy. The user or developer will very likely never have to go here.

Adapter layer - Cossembler currently integrates adapters for the following tools
1) Matlab
2) FMPy
3) CERTI HLA
These adapters allow integartion of the mentioned tools.

Functionality layer - Cossembler can be used to engage different functionalities of the previously mentioned tools. The functionalities are engaged through function calls. Currently, this layer is used to engage:
1) MatPower (Matlab)
2) MatPower-MOST (Matlab)
3) Modelica-OpenIPSL (FMPy)
This layer is not indented to be used directly by the user, but it serves as a bridge between the application layer and the adapter layer. In case one needs to extend the functionalities of Cossembler, one might have to work with this layer. 

Application layer - Cossembler provides different blocks relevant for energy system co-simulations. These blocks link through the functionality layer to different simulation tools and are intended to be used for rapid prototyping. The blocks include, for example, power flow block (based currently on MatPower), dynamic simulation block (based currently on OpenIPSL), optimal power flow block, etc.

The tool can directly integrate simulation tools if they have Python 3 API and can be installed on the same operating system. If this is not possible, the user/developer has to perform integration using a co-simulation master. Currently, only CERTI HLA is supported as a master. The blocks for its integration are available in Cossembler and have to be connected with other blocks in the same way.
