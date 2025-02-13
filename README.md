# Using GROMACS for non-standard systems
A tutorial showing how to edit GROMACs force field files for a custom, non-standard protein.

GROMACs package is an incredibly useful tool for running molecular dynamics (MD) simulations, however, I have found that running MD for a system with complex cofactors requires significant editting of force field (FF) files and no online resource offers a thorough description of exactly which files must be editted. This is a problem for me, as my work requires just that. In this guide, I will walk through everything needed to simulate photosystem 1 using the GROMACs software. Other software used in this guide include Qchem, IQmol, WinCoot, Pymol, VMD, and CHARMM-GUI. 
## SF4 


********
I realize now that I need to make informal notes for the procedure until I know that the prcoess is down. Trying to write a formal walkthrough when I don't yet know how to walk in the first place is impossible.

From PDB (OPM, really): 
-Note which HIS residues are close to CLAs, be certain to protonate accordingly.
-Note CYS residues that bind SF4 clusters, new amino acid "ACYS" added to topology (protonation, bonds added "in post," charges and topology taken from literature and added).
-SF4 topology taken from literature and added to topology. New "amino-acid" called SF4 added.
-Cofactor topologies generated from CHARMMGUI, LibParGen, or any similar FF building tool (C, N, O, H cofactors. Nothing troublesome like with SF4); protonated in IQmol then added back to structure.
-Protein+SF4 topology generated all together. Can cofactors be added to topology the same way? No need to do this, but I wonder if it could be simplified.


