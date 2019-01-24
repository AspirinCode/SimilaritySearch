# MXFP SimilaritySearch

This application can be found at http://similaritysearch.gdb.tools/

To run this Flask application with your own data follow the steps below (a Chemaxon license is necessary):

- Clone this repository

- Copy your chemaxon license in the repository folder as 'license.cxl'

- Create your annoy file and the corresponding dictionary by running `python create_tree_dict.py your-file.fp your-ID-SMILES-dictionary`, 
where `your-file-fp` has the following format: SMILES ID MXFP, and `your-ID-SMILES-dictionary` is {ID:SMILES}.
To calculate MXFP refer to https://github.com/reymond-group/MXFP.
If the SMILES in your-file.fp are the ones to be visualized omit the dictionary and run `python create_tree_dict.py your-file.fp`
The created files are LARGE. Using 7 million molecules and MXFP leads to a 10 Gigabyte annoy file and a 1 Gigabyte dictionary. Use an appropriate folder.

- Paste the path to the created annoy file and dictionary files in 'Flask/app/functs.py' (data_path).

- `python run.py` will run the application locally.

A docker image (alicecapecchi/similaritysearchnew) of the application is available here https://cloud.docker.com/u/alicecapecchi/repository/docker/alicecapecchi/similaritysearchnew



