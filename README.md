# Alveolar macrophage-expressed Plet1 is a driver of lung epithelial repair after viral pneumonia

This Jupyter Notebook contains the essential steps in order to reproduce the findings of the scRNA-seq based analysis in [Pervizaj-Oruqaj, et. al](https://pubmed.ncbi.nlm.nih.gov/38167746/). 

# Data Availability
Raw data, as well as the final h5ad file, can be downloaded from [GEO (GSE208294)](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE208294). 
If you want to perform the analysis yourself, but do not want to perform the alignment step, you can download the Star output files from our [S3 storage](). 

# Usage of the notebook
To reproduce the exact findings from the publications you will need to install the according python package versions (for versions either see methods section or the end of the jupyter notebook).
Either you have your own python environment with the same python package versions. Small variations will influence the outcome (not necessarily in a negative way, but you will not end up with the exact plots from the publication).
To circumvent the hassle of installing all packages, we offer an easy to use docker image.

## Docker file usage
Download docker image
```
docker pull agbartkuhn/pervizaj-oruqaj_plet1_sc_analysis
```
Run the docker image from the folder which contains all Star alignment and the csv file. 
```
docker run --interactive --tty --rm --name sc_analysis_r_py_210114 --publish 8888:8888 --volume "$(pwd)":/root/host_home --workdir /root agbartkuhn/pervizaj-oruqaj_plet1_sc_analysis:latest /bin/bash
```
Finally, start the jupyter notebook from inside the docker image and host it on the given port.
```
jl --port=8888
```

# Cellxgene
The final h5ad file can be interactively browsed using cellxgene. A detailed instruction can be found [here](https://github.com/chanzuckerberg/cellxgene).
There is also an extension for cellxgene, enabling the user to gather and exploit information from their sc data, by calculating and creating great plots using a graphical user interface! You can find more information [here](https://github.com/interactivereport/cellxgene_VIP).
