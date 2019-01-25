# MXFP SimilaritySearch

This application is running at http://similaritysearch.gdb.tools/

The MXFP similarity search is a python Flask app which uses Annoy (Approximate Nearest Neighbors Oh Yeah, by Erik Bernhardsson, https://github.com/spotify/annoy) to search the MXFP non-Lipinski PubChem and non-Lipinski ChEMBL chemical spaces.

In each similarity search instance, the user chooses to search non-Lipinski PubChem or non-Lipinski ChEMBL, and the previously created correspondent Annoy file is selected. The Annoy file is used by the web app to retrieve the compound IDs of a pool of n° (user choice) of nearest neighbors. Then with a previously created ‘pickle saved’ python dictionary, the compound IDs are associated back to the correspondent PubChem or ChEMBL SMILES. The results are displayed using SmilesDrawer.

Annoy files and pickled saved python dictionaries have been created using `create_tree_dict.py`, amd they can be downloaded at https://cloud.gdb.tools/s/m9odqsS2JDZPs3N

To run the app locally:
- clone this repository
- paste your chemaxon license file in the main folder as license.cxl
- download the SimilaritySearchData (dictionaries and annoy files, 11.1 Gigabyte) at https://cloud.gdb.tools/s/m9odqsS2JDZPs3N. 
- pull the docker image `docker pull alicecapecchi/similaritysearchnew:latest`
- run `docker run -p 8080:8080 --mount type=bind,target=/license.cxl,source=/your/explicit/path/license.cxl  --mount type=bind,target=/SimilaritySearchData,source=/your/explicit/path/SimilaritySearchData --mount type=bind,target=/app,source=/data/alice/SimilaritySearch/Flask --name similaritysearch alicecapecchi/similaritysearchnew:latest`
- MXFP similarity search will be running at http://0.0.0.0:8080/
