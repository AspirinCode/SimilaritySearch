# SimilaritySearch

This application can be found at http://similaritysearch.gdb.tools/

To run this Flask application with your own data follow the steps belowe (N.B. A Chemaxon license is necessary):

- Download the repository

- Copy your chemaxon license in the downloaded folder as 'license.cxl'

- Create your annoy file and the corrispondent dictionary running 'python create_tree_dict.py your-file.fp your-ID-SMILES-dictionary', 
where your-file-fp has the following format: SMILES ID fp, and your-ID-SMILES-dictionary is {ID:SMILES}.
If SMILES in your-file.fp are the one to be visualized omit the dictionary and run 'python create_tree_dict.py your-file.fp'
N.B. the created files are LARGE. Using 7 million molecules and MXFP leads to a 10 Gigabyte annoy file and a 1 Gigabyte dictionary. Use an appropriate folder.

- Paste the path to the created annoy file and dictionary files in 'Flask/app/functs.py' (data_path).

- 'python run.py' will run the application locally.

To dockerize this application use the doker image alicecapecchi/similaritysearchnew https://cloud.docker.com/u/alicecapecchi/repository/docker/alicecapecchi/similaritysearchnew



