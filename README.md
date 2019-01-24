# MXFP SimilaritySearch

This application can be found at http://similaritysearch.gdb.tools/

To run this Flask application with your own data follow the steps below (a Chemaxon license is necessary):

- Clone this repository

- Copy your chemaxon license in the repository folder as 'license.cxl'

- This application uses Annoy (Approximate Nearest Neighbors Oh Yeah) by Erik Bernhardsson, to install it, refer to https://github.com/spotify/annoy

- To run this app rdkit, flask, numpy, scikit-learn, flask_wtf, flask_restful, java, have to be installed

- Calculate the MXFP of `your-data.smi`: run `java -cp 2Dtopoguassfp.jar bin.write_topoguassfp2 -i your-data.smi -o your-data.smi -scaleFactors 0.5_1_0.5_1_1_1_1` (for the source code refer to https://github.com/reymond-group/MXFP)

- For both ChEMBL and PubChem, create your annoy file and the corresponding dictionary by running `python create_tree_dict.py your-file.fp your-ID-SMILES-dictionary`, where `your-file.fp` has the following format: SMILES ID MXFP, `your-ID-SMILES-dictionary` is a python dictionary saved with pickle {ID:SMILES}, and ID is an unique identifier.
If the SMILES in your-file.fp are the ones to be visualized omit the dictionary and run `python create_tree_dict.py your-file.fp`.
The created files are LARGE. Using 7 million molecules and MXFP leads to a 10 Gigabyte annoy file and a 1 Gigabyte dictionary. Use an appropriate folder.

- Rename your annoy and dictionary files as: Non-Lipinski-ChEMBL.MXfp_dictionary, Non-Lipinski-ChEMBL.MXfp_annoy, Non-Lipinski-PubChem.MXfp_dictionary, Non-Lipinski-PubChem.MXfp_annoy

- Paste the path to the created annoy file and dictionary files in 'Flask/app/functs.py' (data_path).

- `python run.py` will run the application locally.

A docker image (alicecapecchi/similaritysearchnew) of the application is available here https://cloud.docker.com/u/alicecapecchi/repository/docker/alicecapecchi/similaritysearchnew



