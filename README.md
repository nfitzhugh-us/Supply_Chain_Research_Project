This repository includes most of my original contributions to a paper by Zahir Ballopora and Vijay Mehrotra. 
My alterations to programs writen by other people and adapted for this project as well as other relevent files that I don't have permission to share are omitted.

This project aim to identify patterns that lead to critical supply chain failures. 
In broad strokes, this is done by simulating a large number of supply chain states and caluculating the cost of operating under each state, then passing the results to an evolutionary computation algorithm (GAIA: Graph Classification Using Evolutionary Computation created by Ning Jin, Calvin Young, and Wei Wang of University of North Carolina) which identifies subgraph pattern which appear more frequently in high-cost states.
Finally, these subgraph patterns will be ran through a graph classification algorithm to identify strongly predictive combinations of features that lead to supply chain failure.

My role in this project has been to take the data output from the simulations through to the graph classification algorithm. The first step in this process was to write a script that would convert the simulation output (in the same format as the .xlsm files in this repository) to the format required by GAIA. This is the data_conversion_script.ipynb file in this repo. Next I had to edit the GAIA code to change the output parameters. GAIA generates a list of candidate subgraph patterns and then uses a classification algorith which is not sutable for our purposes to generate a set of graph classification rules from that candidate list; instead we needed the program to output the full candidate list. This code is not included in the repository. And finally, I wrote the GAIA_output_conversion.ipynb file to convert the .txt file output by this altered version of the GAIA program to a set of pandas dataframes that be input into a more fitting classification algorithm.