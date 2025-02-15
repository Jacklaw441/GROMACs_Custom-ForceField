# Using GROMACS for non-standard systems
A tutorial showing how to edit GROMACs force field files for a custom, non-standard protein.

GROMACs package is an incredibly useful tool for running molecular dynamics (MD) simulations, however, I have found that running MD for a system with complex cofactors requires significant editting of force field (FF) files and no online resource offers a thorough description of exactly which files must be editted. This is a problem for me, as my work requires just that. In this guide, I will walk through everything needed to simulate photosystem 1 using the GROMACs software. Other software used in this guide include Qchem, IQmol, WinCoot, Pymol, VMD, and CHARMM-GUI. 
## SF4 


********
I realize now that I need to make informal notes for the procedure until I know that the prcoess is down. Trying to write a formal walkthrough when I don't yet know how to walk in the first place is impossible.

From PDB (OPM, really): 
-Note which HIS residues are close to CLAs, be certain to protonate accordingly.

-Note CYS residues that bind SF4 clusters, new amino acid "ACYS" added to topology (protonation, bonds added "in post," charges and topology taken from literature and added to database of known AAs).

-SF4 topology taken from literature and added to topology. New "amino-acid" called SF4 added.

-Cofactor topologies generated from CHARMMGUI, LibParGen, or any similar FF building tool (C, N, O, H cofactors. Nothing troublesome like with SF4); protonated in IQmol then added back to structure.

-Protein+SF4 topology generated all together. Can cofactors be added to topology the same way? No need to do this, but I wonder if it could be simplified.

-Manually add in "bridged" topology parameters. ACYS-SF4 bonds, angles, dihedrals must be added. Alternatively, define a "super-residue" that is 4 ACYS and SF4 all in one. BUT, this will then require adding in the protein backbone bonds for the ACYS alpha and carbonyl carbons. I like the current apporach.

-573PRO and 574ACYS creates a chain break... I have no idea why? 573PRO must be editted to be regular, and bonds, angles, dihedrals between the two should be defined manually.
    - Huzzah. The first ACYS will always cause a chain break. The workaround is to label all ACYS as CYS2, a disulfide CYS instead. The proper protonation and chains are made by GROMACS, however, you will need to edit the charges and atomtypes of these residues manually. Bridge bonds will still be added manually, but that is not different anyway.
