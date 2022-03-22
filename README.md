# setup-mac-M1

## conda environment

### Install

We'll install miniforge-3 from conda-forge (https://github.com/conda-forge/miniforge) rather than miniconda from conda. The reason is Miniforge have a dedidated version for ARM64 processor which is convenient to this date (20/03/2022) as little to no official support exist for such platform. 

1) Download the miniforge-3 installer in /tmp (the downloaded installer file will be deleted after a while)
```
wget https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-arm64.sh -P /tmp
```
2) Install miniforge-3
```
bash /tmp/Miniforge3-MacOSX-arm64.sh
```
then type enter, then 'yes', then enter, then yes.
4) Close the terminal and quit the terminal application

### Creating a work environment with jupyter notebook

1) Open a terminal
2) Create a new environment (here named 'work_env') with python 3.9.9
```
conda create -n work_env python=3.9.9
```
3) Activate the environment 
``` 
conda activate work_env
```
4) Install jupyter notebook using conda (AND NOT PIP). 

Indeed, using pip (pip install jupyter), jupyter notebook kernel does not load. 
You can either run 
```
conda install jupyter 
```
or run the following command with the requirements.txt file from this repo
```
conda install -y -q --name work_env -c conda-forge --file requirements.txt
```
Et voila !

