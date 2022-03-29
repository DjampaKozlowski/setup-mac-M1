# setup-mac-M1

## brew

"Homebrew supports the Mac M1 chip (Apple silicon) beginning with the release of Homebrew 3.0.0 in February 2021. On Apple silicon, Homebrew installs files into the /opt/homebrew/ folder, which is not part of the default shell $PATH. You'll need to configure your shell environment so Homebrew packages are found and take priority over pre-installed tools."
https://mac.install.guide/homebrew/index.html

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```


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
conda install -c conda-forge jupyter 
conda install -c conda-forge jupyter_contrib_nbextensions
```
or run the following command with the requirements.txt file from this repo
```
conda install -y -q --name work_env -c conda-forge --file requirements.txt
```
5) Pimp your jupyter notebooks with awesome extensions : 
```
jupyter contrib nbextension install --user
jupyter nbextension enable code_prettify/code_prettify
jupyter nbextension enable notify/notify
jupyter nbextension enable ruler/main
jupyter nbextension enable toc2/main
jupyter nbextension enable execute_time/ExecuteTime
jupyter nbextension enable comment-uncomment/main
jupyter nbextension enable freeze/main
jupyter nbextension enable keyboard_shortcut_editor/main
jupyter nbextension enable spellchecker/main
jupyter nbextension enable move_selected_cells/main
jupyter nbextension enable rubberband/main

```
Et voila !

