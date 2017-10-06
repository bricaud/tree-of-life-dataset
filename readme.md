#1 Tree of life dataset


This repository provides a [tree of life](https://en.wikipedia.org/wiki/Tree_of_life_(biology)), or phylogenetic tree, under different file formats. In this tree, each node is a species (living or extinct) of the earth. Links between nodes represent ancestor/descendant relationship between species. The tree has been made by biologists and is constantly evolving with research.
The original data has been collected on the [Tree Of Life Project website](http://tolweb.org/tree/home.pages/downloadtree.html) as a xml file (old xml version of the tree). Details about the data can be found on the same page.

The xml file available on the above website is licensed under the [Attribution Creative Commons 3.0](https://creativecommons.org/licenses/by/3.0/), the copyright is owned by the [Tree Of Life Project](http://tolweb.org/tree/home.pages/tolcopyright.html). It is available at `data/tolskeletaldumpUTF8.xml` (The original file has been converted to UTF8).

The data has been extracted and saved as JSON and graphml files to be easily loaded in a graph database.

The python script performing this task is provided as a Jupyter notebook `scripts/tree_of_life_xml_tol.ipynb` (APACHE 2.0 licence).

The content of the data files available in the `data` folder are licenced under the same license as the original xml file [Attribution Creative Commons 3.0](https://creativecommons.org/licenses/by/3.0/). Except for the `xml` file, the copyright is owned by Benjamin Ricaud. Copies, redistributions, modifications are allowed. These files can be recreated using the Python script.

## Details on the data in the xml file

Nodes of the tree have different properties:
| Property | value | Comment |
| --- | --- | --- |
| NAME | String | Name of the species or empty string if unknown |
| CONFIDENCE | 0, 1 or 2 | Confidence of placement in the tree structure. 0 - confident,1 - incertae sedis in putative position,2 - incertae sedis position unspecified (no putative position in parent group) |
| LEAF | Boolean | Whether or not the node is a leaf |
| CHILDCOUNT | Integer | Number of child nodes |
| PHYLESIS | 0, 1 or 2 |  0 - monophyletic, 1 - monophyly uncertain, 2 - not monophyletic |
| HASPAGE | Boolean | whether or not there is a page on the website tolweb.org describing this species |
| EXTINCT | 0 or 2 | 0 - living or 2 - extinct species |
| ID | Integer | Id of the species in the tree (tolweb.org identifier) |

There are no properties associated to the links between nodes.
