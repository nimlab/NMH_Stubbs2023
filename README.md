# Heterogeneous neuroimaging findings across substance use disorders localize to a common brain network 

Supporting code for: Stubbs et al. (in press). Heterogeneous neuroimaging findings across substance use disorders localize to a common brain network. *Nature Mental Health* (DOI: TBD).

## Environment installation
It is recommended to use [mamba](https://github.com/mamba-org/mamba) to install the conda environment:
```
mamba env create -f environment.yml
conda activate nmh_stubbs2023
```
## Preparing the seeds
`sphere_maker.ipynb` can be used to generate spheres on a template brain from coordinates in a CSV file.

## Preparing the connectome

This code was written to be used with the [GSP1000 dataset](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/ILXIKS). The `format_connectome.py` script takes the 4D NiFTI files from the GSP1000 dataset, precomputes the algebraic norm per-voxel, and reshapes the data into 2D .npy files.

## Seed-based functional connectivity
`connectome_quick.py` accepts a text file where each line points to a different seed NiFTI and the directory of connectome files generated in the prior step. 
```
python connectome_quick.py \
    -r my_spheres.txt \
    -cs GSP1000_formatted \
    -o my_output
```

## Spatial permutation
Spatial permutation can be run with `spatial_permute.m`.

## Overall coordinate network results
SUD_CNM_FINAL.nii.gz contains the overall substance use disorder coordinate network shown in Figure 5a.

## References
- SUD atrophy studies: https://doi.org/10.1038/s41398-020-01128-2
- SUD fMRI studies: https://doi.org/10.1002/hbm.25085
- Specificity analysis atrophy studies: https://doi.org/10.1002/hbm.23772
- Nicotine use disorder lesion dataset: https://doi.org/10.7910/DVN/8BHHRS

