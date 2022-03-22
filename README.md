# setup-mac-M1

## conda environment

We'll install miniforge-3 from conda-forge (https://github.com/conda-forge/miniforge) rather than miniconda from conda. The reason is Miniforge have a dedidated version for ARM64 processor which is convenient to this date (20/03/2022) as little to no official support exist for such platform. 

1) Download the miniforge-3 installer in /tmp (the downloaded installer file will be deleted after a while)
```
wget https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-arm64.sh -P /tmp
```
2) 

wget https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-arm64.sh
