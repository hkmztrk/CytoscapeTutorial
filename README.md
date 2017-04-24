# Cytoscape Tutorial

This tutorial aims to help to beginners in the Bioinformatics fields to use Cytoscape and utilize some important network parameters such as centrality and clustering. 

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

### Centrality
[Centrality](https://cs.hse.ru/data/2015/05/14/1098547089/4._Centrality_Metrics.pdf) metrics decide how important an actor in the network based on its position. 

#### Degree

![image](https://cloud.githubusercontent.com/assets/4271817/25327381/97a26a90-28dc-11e7-86ed-4f0554c53891.PNG)

#### Betweenness
![image](https://cloud.githubusercontent.com/assets/4271817/25327379/979b1b6e-28dc-11e7-9512-bfc033ab1aef.PNG)

#### Closeness
![image](https://cloud.githubusercontent.com/assets/4271817/25327380/979ba1b0-28dc-11e7-8d8a-ebfe381e5447.PNG)


### Clustering

## Example Task
1. Go to [PDB](http://www.rcsb.org/pdb/software/rest.do) database. Type “Diabetes Mellitus" in the searchbox and choose Meshtree code C19.246 and go.

2. You might filter the results by selecting a specific organism.

3. Go to Reports menu and select Custom Reports > Customizable Table.


