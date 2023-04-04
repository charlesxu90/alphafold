# AlphaFold usage

# Install dependencies

## Create conda environment

```shell
conda env create -f environment.yml -p ./env
conda activate ./emv
```
By default, if will install the requirements in `requirements.txt` file. In case the installation is not successful, run the following command.

```shell
pip install -r requirements.txt
```

## Install jaxlib

```shell
pip install jaxlib==0.3.25+cuda11.cudnn805 -f https://storage.googleapis.com/jax-releases/jax_cuda_releases.html
```


## Install AlphaFold
```shell
python setup.py install
```

# Download datasets

Download the following datasets
- uniref100  Default is uniref90. Because I have downloaded uniref100, so use it instead.
- smallbfd
- mgnify
- uniprot
```shell
mkdir seq_dbs
ln -s /home/xiaopeng/Desktop/Enzyme_design/Subt_design/ref_works/fitness-modeling/data/uniref100/uniref100.fasta uniref100.fasta

bash scripts/download_small_bfd.sh seq_dbs/
bash scripts/download_mgnify.sh seq_dbs/
bash scripts/download_uniprot.sh seq_dbs/
```

# Run jupyter notebook in conda environment

It's easy to try AlphaFold Multimer using [this notebook in CodeLab](https://colab.research.google.com/github/deepmind/alphafold/blob/main/notebooks/AlphaFold.ipynb?pli=1#scrollTo=3zGsJuVoM44V). However, if we were to predict multiple sequence in batch, it's better to have a local version.

