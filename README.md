# Carnatic Raga Identification 

## Dataset 
 This project uses the CompMusic Raga Dataset. 
 The audio files are permission-restricted and are **not included** in this repository.

To reproduce experiments:

1. Obtain access to the CompMusic Raga audio dataset.
2. Download the dataset using `mirdata` or from the official Zenodo source.
3. Place the audio files in the appropriate local directory.

## Metadata Construction

The metadata CSV (`raga_20_dataset.csv`) was generated using the `mirdata` interface for the `compmusic_raga` dataset.

The notebook `notebooks/01_build_metadata.ipynb`:

- Loads the dataset using `compiam` / `mirdata`
- Extracts track_id, artist, and raga labels
- Filters a selected set of 20 ragas
- Rewrites audio paths to point to the local permissioned audio directory
- Exports the final CSV to `data/metadata/`

## Environment

The metadata notebook was executed in Google Colab.

To reproduce locally:

1. Create a Python 3.11 environment
2. Install dependencies:
   pip install compiam mirdata pandas numpy

3. Set `DATA_HOME` to the location of the CompMusic dataset.
4. Run `01_build_metadata.ipynb`