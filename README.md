# varying-surface-forcing

Jupyter notebooks to reproduce figures for the paper:

Bhagtani, D., Hogg, A. McC., Holmes, R. M., and Constantinou, N. C. (2023) Surface heating steers planetary-scale ocean circulation., J. Phys. Oceanogr., (submitted on January 2023; arXiv:2301.11474, doi:[10.48550/arXiv.2301.11474](https://doi.org/10.48550/arXiv.2301.11474)).

## Contents

`Figures`: Figures produced by jupyter notebooks in home directory.

`NETCDF`: Data files containing: (i) (Gyre_95th) gyre strength estimated using isopycnal outcropping method, and (ii) (SST_expts) pre-calculated globally integrated sea surface temperatures to create Fig. 1 in the paper.

`Expt_config_figures.ipynb`: Notebook to create Fig. 1 in the paper.

`Wind_figures.ipynb`: Notebook to create Figs. 2 and 3 in the paper.

`Red_heat_figures.ipynb`: Notebook to create Figs. 4, 5, 6 and 7 in the paper.

`Inc_heat_figures.ipynb`: Notebook to create Figs. 8, 9, 10, 11 and 12 in the paper.

`Uniform_warming_figures.ipynb`: Notebook to create Fig. 13 in the paper.

## Numerical model information 

We run ACCESS-OM2 (Kiss et al 2020) containing:

(i) MOM v5.1: https://github.com/dhruvbhagtani/MOM5/tree/f3f05e7700ca29ed1baa5f1c8d1f411ae9a40ae3 with LIBACCESS-OM2 modules used: https://github.com/COSIMA/libaccessom2/tree/392dce398e985843cc6488af4c3498138373838b

(ii) CICE v5.2: https://github.com/russfiedler/cice5/tree/26e61591c985ee76a10366dcba51fb99e6d84f61 with LIBACCESS-OM2 modules used: https://github.com/COSIMA/libaccessom2/tree/a9d4b678166642f0a7639a8a878afcfec1f35c4f
