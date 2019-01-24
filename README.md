# MXFP SimilaritySearch

This application is running at http://similaritysearch.gdb.tools/

The MXFP similarity search is a python Flask app which uses Annoy (Approximate Nearest Neighbors Oh Yeah, by Erik Bernhardsson, https://github.com/spotify/annoy) to search the MXFP non-Lipinski PubChem and non-Lipinski ChEMBL chemical spaces.

In each similarity search instance, the user chooses to search non-Lipinski PubChem or non-Lipinski ChEMBL, and the previously created correspondent Annoy file is selected. The Annoy file is used by the web app to retrieve the compound IDs of a pool of n° (user choice) of nearest neighbors. Then with a previously created ‘pickle saved’ python dictionary, the compound IDs are associated back to the correspondent PubChem or ChEMBL SMILES. The results are displayed using SmilesDrawer.

Annoy files and pickled saved python dictionaries have been created using `create_tree_dict.py`.



