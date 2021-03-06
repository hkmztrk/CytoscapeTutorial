# Cytoscape Tutorial

This tutorial aims to help to beginners in the Bioinformatics fields to use Cytoscape and utilize some important network parameters such as centrality and clustering. Cytoscape version 3.2.1 was used in this tutorial.

Some other useful tutorials, [Analysis and Visualization of BiologicalNetworks with Cytoscape](http://www.cgl.ucsf.edu/Outreach/Workshops/NIH-Oct-2012/Cytoscape/Analysis%20and%20Visualization%20of%20Biological%20Networks%20with%20Cytoscape%20v6.pdf) and [Introduction to Cytoscape 3.1](http://www.cgl.ucsf.edu/home/scooter/NCI2016/Tutorial2_Networks_Data_Styles_Layouts_and_App_Manager.pdf). 

## Tools

*  [Cytoscape](http://www.cytoscape.org) is an open source environment for the analysis and
integration of biological networks.
*  Cytoscape enables use of broad range of plugins targeting clustering, graph analysis,
ontology analysis and more. You can find the available plugins here,
[Cytoscape App Store](http://apps.cytoscape.org/) .
*  [Network Analyzer](http://apps.cytoscape.org/apps/networkanalyzer) is a built-in plugin of Cytoscape, which provides statistical parameters of the network as well as central nodes.
*  [ClusterMaker2](http://apps.cytoscape.org/apps/clustermaker2) provides a wide range of algorithms to find the densely connected clusters for the given network.
*  [MCODE](http://apps.cytoscape.org/apps/mcode) is one of the specific methods to identify clusters.

## Data
### General Data
* [Example data sets](http://www-personal.umich.edu/~mejn/netdata/)
### Biological/Chemical Data
* [Protein Data Bank (PDB)](http://www.rcsb.org/pdb/software/rest.do)
* [CHEMBL](https://www.ebi.ac.uk/chembl/)
*  [STRING](http://string-db.org) is a protein-protein interaction database which integrates both
known and predicted interactions.
*  [STITCH](http://stitch.embl.de/) provides three different interaction types to invesgate, chemical-chemical, protein-chemical and protein-protein. 
* [GLASS](http://zhanglab.ccmb.med.umich.edu/) is a GPCR-ligand interaction database.
* [DrugBank]()
* [Chem2bio2rdf Data sets](https://chem2bio2rdf.wikispaces.com/Datasets)

## Understanding the Network

[Zachary Karate Club](https://en.wikipedia.org/wiki/Zachary%27s_karate_club), a well-known social network data set of university karate club, is used for demonstration. Data set contains total 34 actors (nodes) with 78 interactions (edges). 

### Centrality
[Centrality](https://cs.hse.ru/data/2015/05/14/1098547089/4._Centrality_Metrics.pdf) metrics decide how important an actor in the network based on its position. In the examples below, size  and color of the nodes indicate importance. Importance decreases in the following direction: bigger, red --> smaller, green. 

#### Degree
 Degree centrality is simply measured by the number of ties that a node has.
 
![image](https://cloud.githubusercontent.com/assets/4271817/25327381/97a26a90-28dc-11e7-86ed-4f0554c53891.PNG)



#### Betweenness
 Betweenness centrality quantifies the number of times a node acts as a bridge along the shortest
path between two other nodes.

![image](https://cloud.githubusercontent.com/assets/4271817/25327379/979b1b6e-28dc-11e7-9512-bfc033ab1aef.PNG)

#### Closeness
In the closeness centrality, the node that spread information to the others as fast as possible is the most central one in this case where the fast defined as short paths.

![image](https://cloud.githubusercontent.com/assets/4271817/25327380/979ba1b0-28dc-11e7-8d8a-ebfe381e5447.PNG)


### Clustering

Clustering is the task of dividing a set of objects into groups/clusters/cliques so that the  objects with similar properties are placed together. 

Clustering helps us to identify densely connected nodes.

![image](https://cloud.githubusercontent.com/assets/4271817/25387772/a942d3fe-29d4-11e7-843f-2b9fce610295.PNG)


## Example Tasks

### Protein-Ligand Interaction Data
1. Go to [PDB](http://www.rcsb.org/pdb/software/rest.do) database. Select advanced Search under Search box.

   Set the first parameter as **Text**, then type __Diabetes Mellitus__.
   
   Set the second parameter as **HasLigand(s)** then select __Yes__
   
   By this way, we make sure that each protein in this data set binds to at least one ligand.

2. You might filter the results by selecting a specific organism.

3. Go to Reports menu and select **Custom Reports > Customizable Table**.

4. Choose the parameters you are interested in. To be able to define an interaction we need source and target nodes. 
   Since we want to build a protein-ligand interaction network, our source/target node is protein whereas target/source node is chemical. We need to select at least two parameters __protein name/id__ and __chemical name/id__.
  
 5. Create the report and download it one of the given formats. Now we have a file that we can investigate!
 
### Protein-Protein Interaction Data
1.	Go to [STRING](http://string-db.org/) database.

2.	Search for **Protein name**: "Alzheimer" and set the **organism**: “homo sapiens”. Choose the first of the offered options.

3.	You’ll see a small network of 10 interacting proteins. Expand the network by following the steps, **Data settings > max number of interactors > custom value > max interactors = 60**. 

4.	To download the data, follow **Tables/Exports > simple tabular text output**.


### Cytoscape
 
1. Open Cytoscape and import the downloaded file into the tool by **Import > Network > File**. 
 
2. To create the network we should state Source Interaction and Target Interaction. These refer to the proteins and ligands that that we want to connect. Interaction Type is protein-ligand interaction (PLI).  However, if you have different kinds of networks that you give different ids/names/codes to the edges, you should specify the corresponding column as an interaction type.
 
 ![image](https://cloud.githubusercontent.com/assets/4271817/25359484/23ff9726-294e-11e7-8240-4269bd1aa3f6.PNG)
   
3.  **Style** Tab on the Control Panel will help you to customize network style. You can change node size and color, arrange edge width as well as other visual properties.

4. To get information about the topology of the network such as the number of edges, clusteringcoefficient, network diameter and more, we will use Network Analyzer. 
 **Tools > Network Analysis > Analyze Network**
 
5. Network Analyzer also allows us to pick central nodes with several different ranking methods. To visualize the central nodes use Visualize Parameters button on Results Panel. 
 
 ![image](https://cloud.githubusercontent.com/assets/4271817/25359482/23fb1700-294e-11e7-9e43-5a319c7b8625.PNG)
 
 Then choose the type of visualization and the parameter you want to investigate.
 
 ![image](https://cloud.githubusercontent.com/assets/4271817/25359483/23fdb898-294e-11e7-93d3-71204646c113.PNG)
 
6. ClusterMaker2 is not a build-in plugin, so you need to integrate it to Cytoscape.  
 **Apps > AppManager > Type ClusterMaker2 > Select ClusterMaker2 from list > Install**
 
 ![image](https://cloud.githubusercontent.com/assets/4271817/25437718/f1cda3da-2a9f-11e7-9416-8e23b5d020d9.PNG)

7. Go **Apps > ClusterMaker2 > MCODE.**
    Before starting, you can change the parameters according to your need using **Advanced Options**. For instance, increasing the number of K-cores will increase the threshold of number of nodes to be included in the communities. You can perform MCODE for a small area of the network as well as the whole one.

