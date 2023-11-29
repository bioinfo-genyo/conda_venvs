# conda_venvs

Conda envs for bioinformatics analysis

## Install conda

```bash
## Download and install
wget https://repo.anaconda.com/archive/Anaconda3-2023.09-0-Linux-x86_64.sh
bash Anaconda3-2023.09-0-Linux-x86_64.sh

## Answer the questions and open new terminal

# Configuration
conda config --add channels defaults
conda config --add channels conda-forge
conda config --add channels bioconda
conda config --set channel_priority flexible
conda install -n base -c defaults conda=23.10
conda config --set solver libmamba
conda update -n base -c defaults conda

# Check that version is 23.10
```

## Create envs

```bash

# Create env with default python or specific python
conda create -n rna-seq
conda create -n rna-seq python=3.10

# Create env to download and install R and useful packages
cat r_packages.txt | xargs conda install -n R

# List all envs
conda env list

# Activate env
conda activate rna-seq

# Install packages
conda install PACKAGE

# Example
conda install -c bioconda samtools

# List all installed packages in an env
conda list

# Deactivate
conda deactivate

# Remove env
conda remove -n rna-seq --all

```

## Export envs

```bash
# Export env as .yml
conda env export > environment.yml
```

## Import envs

```bash
# Import the .yml file in other pc
conda env create -f environment.yml
```