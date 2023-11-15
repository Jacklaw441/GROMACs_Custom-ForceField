# GROMACs_Custom-ForceField
A tutorial showing how to edit GROMACs force field files for a custom, non-standard protein.

GROMACs package is an incredibly useful tool for running molecular dynamics (MD) simulations, however, I have found that running MD for a system with complex cofactors requires significant editting of force field (FF) files and no online resource (that I could find) offers a thorough description of exactly which files must be editted. This is a problem for me, as my work requires modelling photosynthetic proteins. In this guide, I will walk through everything needed to simulate photosystem 1 using the GROMACs software. Other software used in this guide include Qchem, Chimera, and CHARMM-GUI. The challenge of fitting photosystem 1 into GROMACs is that several cofactors are not defined in the standard FFs. Of these cofactors, the iron-sulfur clusters (SF4, contains 4 Fe and 4 S) are the trickiest. SF4 will be discussed first. If you are only interested in adding organic cofactors that do not contain troublesome metals, you may want to skip to the 'Organic Cofactors' section below. 
## SF4 
![image](https://github.com/Jacklaw441/GROMACs_Custom-ForceField/assets/74787968/6e160941-d69d-4a5d-a957-4289e69faf24)
Each SF4 cluster rests between 4 cystine (CYS) residues, coordinated by the CYS sulfur. The first order of business with any cofactor is to add the force field so GROMACs knows how to handle bond distances, angles, dihedrals, and non-bonded interactions. For later cofactors, I use CHARMM-GUI to generate this information; for SF4, we found a group that previously generated force fields for several Fe-S clusters including the one found in photosystem 1. Force field information for SF4 is found in the supplemental information of this link:https://pubs.acs.org/doi/10.1021/ct800342w. 
