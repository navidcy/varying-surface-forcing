# varying-surface-forcing

Jupyter notebooks to reproduce figures for the paper:

Bhagtani, D., Hogg, A. McC., Holmes, R. M., and Constantinou, N. C. (2023) Surface heating steers planetary-scale ocean circulation., J. Phys. Oceanogr., (submitted on January 2023; arXiv:2301.11474, doi:[10.48550/arXiv.2301.11474](https://doi.org/10.48550/arXiv.2301.11474)).

## Contents

`Figures`: Figures produced by jupyter notebooks in home directory.

`NETCDF`: Data files containing:
  * `Gyre_95th`: gyre strength estimated using isopycnal outcropping method, and
  * `SST_expts`: pre-calculated globally integrated sea surface temperatures used for Fig. 1.

`Expt_config_figures.ipynb`: Notebook to create Fig. 1.

`Wind_figures.ipynb`: Notebook to create Figs. 2 and 3.

`Red_heat_figures.ipynb`: Notebook to create Figs. 4, 5, 6, and 7.

`Inc_heat_figures.ipynb`: Notebook to create Figs. 8, 9, 10, 11, and 12.

`Uniform_warming_figures.ipynb`: Notebook to create Fig. 13.

## Numerical model information 

We run ACCESS-OM2 (Kiss et al 2020) at 0.25 degree resolution which comprises of:

(i) MOM v5.1: https://github.com/dhruvbhagtani/MOM5/tree/f3f05e7700ca29ed1baa5f1c8d1f411ae9a40ae3 with LIBACCESS-OM2 modules used: https://github.com/COSIMA/libaccessom2/tree/392dce398e985843cc6488af4c3498138373838b.

(ii) CICE v5.2: https://github.com/COSIMA/cice5/tree/26e61591c985ee76a10366dcba51fb99e6d84f61 with LIBACCESS-OM2 modules used: https://github.com/COSIMA/libaccessom2/tree/a9d4b678166642f0a7639a8a878afcfec1f35c4f.

Please note that the MOM5 code used above has the following additions:

(i) An implementation of resolved shear parameterisation for mixing layer depth, and 

(ii) A script to input a mask and place it on top of wind forcing.

This eddy-permitting model is run for 200 years (more details present in Section 2 of the paper), after which the following set of MOM5-only perturbation experiments are branched off using:

| Expt short name    | Expt long name | Wind Factor | Surface buoyancy flux contrast (W m⁻²) | Region | 
| ------------------ | ----------- | ----------- | -------------------------------------- | ------ |
| Control            | `025deg_jra55_ryf_control` | 1 | 0 | G |
| 0.5xW            | `025deg_jra55_ryf_fluxS_050x_20yr_avg` | 0.5 | 0 | G |
| 1.5xW            | `025deg_jra55_ryf_fluxS_150x_20yr_avg` | 1.5 | 0 | G |
| -15 W m⁻²            | `025deg_jra55_ryf_fluxH_neg10W` | 1 | -15 | G - T |
| -7.5 W m⁻²            | `025deg_jra55_ryf_fluxH_neg5W` | 1 | -7.5 | G - T |
| +7.5 W m⁻²            | `025deg_jra55_ryf_fluxH_pos5W` | 1 | +7.5 | G - T |
| +15 W m⁻²            | `025deg_jra55_ryf_fluxH_pos10W` | 1 | +15 | G - T |
| +30 W m⁻²            | `025deg_jra55_ryf_fluxH_pos20W` | 1 | +30 | G - T |
| Uniform warming      | `025deg_jra55_ryf_fluxH_pos5W_globe` | 1 | 0, instead spatially uniform +5 | G |

Outputs for each experiment can be found on the National Computational Infrastructure in the following directory: `/g/data/hh5/tmp/db6174/mom/archive`. Access to these outputs requires one to be a member of this infrastructure. Therefore, a copy of these files will be made available in a Zenodo repository after acceptance of this manuscript.

The MOM5 version used for the perturbation experiments is: https://github.com/dhruvbhagtani/MOM5/tree/d7d72278a11ed9e2d88be3cb8d780b8efba629c5.

References:
1. Kiss, A. E., Hogg, A. McC., Hannah, N., Boeira Dias, F., Brassington, G. B., Chamberlain, M. A., Chapman, C., Dobrohotoff, P., Domingues, C. M., Duran, E. R., England, M. H., Fiedler, R., Griffies, S. M., Heerdegen, A., Heil, P., Holmes, R. M., Klocker, A., Marsland, S. J., Morrison, A. K., Munroe, J., Nikurashin, M., Oke, P. R., Pilo, G. S., Richet, O., Savita, A., Spence, P., Stewart, K. D., Ward, M. L., Wu, F., and Zhang, X.: ACCESS-OM2 v1.0: a global ocean–sea ice model at three resolutions, _Geosci. Model Dev._, **13**, 401–442, doi:[10.5194/gmd-13-401-2020](https://doi.org/10.5194/gmd-13-401-2020), 2020.
