@def title = "PalmStudio project"
@def tags = ["syntax", "code"]

# The PalmStudio research project


The PalmStudio project aims at developing a functional-structural plant model (FSPM) for the oil palm (*Elaeis guineensis*). The FSPM is built using three sub-models: VPalm to build 3D mock-ups, ARCHIMED to compute the biophysics such as the light interception, temperature and photosynthesis at organ scale, and XPalm to simulate the plant development, growth and yield.

The project is funded by our partner the SMART research institute from Indonesia. The first phase of the project was set from 2016 to 2019. We are currently on the second phase of the project starting from 2021 to 2024.

\note{The softwares developed in the frame of the project are available from the [Github repository](https://github.com/PalmStudio) of the project. The data is not publicly available, and securely stored on CIRAD-owned servers. See below for more information.}

---

# Structure overview

Here is an overview of where to find the code and data for the different tasks/sub-projects in PalmStudio.

The code is stored on the [Github repository](https://github.com/PalmStudio) of the project, and the associated data can be found in the `Data` folder of the Alfresco page of the project [here](https://collaboratif.cirad.fr/share/page/site/PALMstudio/documentlibrary#filter=path%7C%2FData%7C&page=1).

The code/data are structured so each specific task of the project has its own repository. This allows for a better reproducibility of the results and an easier access for the users. In essence, each repository has one -and only one- specific objective, such as fitting the parameters for the \cite{farquhar1980} model.

The data in Alfresco follows the same structure as the Github repository so the user can download / clone the repository from Github, and then just drag and drop the `0-data` folder from the eponym project in Alfresco at the root of the project on its computer.

Here is a list of all projects and the links to the corresponding code and data (click on the Github logo to access the code, or the Alfresco logo to access the data):

\tableofcontents

## VPalm

### Vpalm model \badgegithub{https://github.com/PalmStudio/Vpalm}

VPalm is the model used to build virtual 3D mock-ups of oil palm plants using allometric relationships fed by field data. Two versions are currently available: the classic one and the one with a biomechanical model for leaves bending and torsion.

The main advantage of the classic one is that it does not need information about the leaf mass because it uses an allometry to compute the bending and torsion of the leaves. But for this reason it is also much less realistic than the version with the biomechanical model because it cannot well simulate the plasticity of the plant to its environment.

### Vpalmr \badgegithub{https://github.com/PalmStudio/Vpalmr}

Vpalmr is an R package used to ease the process of making virtual palm plants from field data. It can help to compute the parameter values for VPalm from field data, call VPalm to make the OPF (Open Plant Format) files, and even make the OPS (OPen Scene) files, all from R.

### VPalm-IDE \badgegithub{https://github.com/PalmStudio/VPalm_IDE} \badgealfresco{https://collaboratif.cirad.fr/share/page/site/PALMstudio/documentlibrary#filter=path%7C%2FData%2FVPalm_IDE%7C&page=1}

VPalm-IDE is used to compute the architectural parameters from field data using a graphical interface, and build 3D plant mock-ups arranged in a scene using VPalm. The output files are in OPF (Open Plant Format) and OPS (OPen Scene) format.

### paper\_inSilicoPlants\_2021 \badgegithub{https://github.com/PalmStudio/paper_inSilicoPlants_2021} \badgealfresco{https://collaboratif.cirad.fr/share/page/site/PALMstudio/documentlibrary#filter=path%7C%2FData%2Fpaper_InSilicoPlants_2021%7C&page=1}

This is the projet containing the scripts and data of the paper following the FSPM 2020 conference. It presents the new version of VPalm that integrates a new biomechanical model to compute the bending and torsion of the leaves from their biomass and two parameters: `elastic_modulus` and `shear_modulus`.

The paper also present a case-study where we simulate the biophysical processes of oil palm plants to better understand the effect of the architectural plasticity in response to increased planting density.

### biomech \badgegithub{https://github.com/PalmStudio/biomech}

`biomech` is an R package that implements the biomechanical model now found in VPalm to compute bending and torsion of beams following the Euler-Bernoulli beam theory. It is specifically designed to be applied on palm plant leaves, but can be applied to any other beam-shaped structure.

This package is mainly used to compute the parameters of the model from field data, namely `elastic_modulus` and `shear_modulus`, and to check the results interactively at leaf scale.

## Archimed

### Shiny\_fit\_photosynthesis \badgegithub{https://github.com/PalmStudio/Shiny_fit_photosynthesis} \badgealfresco{https://collaboratif.cirad.fr/share/page/site/PALMstudio/documentlibrary#filter=path%7C%2FData%2FShiny_fit_photosynthesis%7C&page=1}

This is an R Shiny application used to fit the parameters for the \cite{farquhar1980} and the \cite{medlyn2011} models using `A~Ci` and `Gs~VPD` response curves. The first tab is used to visualise the responses curves according to the plant and measurement dates, while the second tab is used to fit the model parameters on the data. The parameter values can then be exported to a table found in the third and last tab.

### Conductance \badgegithub{https://github.com/PalmStudio/Conductance} \badgealfresco{https://collaboratif.cirad.fr/share/page/site/PALMstudio/documentlibrary#filter=path%7C%2FData%2FConductance%7C&page=1}

This is an R project set-up to compute the parameters of the stomatal conductance model from \cite{medlyn2011} using field data on mature palm plants.


### Shiny\_design\_ops \badgegithub{https://github.com/PalmStudio/Shiny_design_ops}

This is an R Shiny application used to interactively set-up a quincunx planting design using intra- and interrow distances. The resulting design can then be saved in an `.ops` file.

\note{The path to the `.opf` files has to be updated manually after saving.}

### Light\_interception\_vs\_ages \badgegithub{https://github.com/PalmStudio/Light_interception_vs_ages} \badgealfresco{https://collaboratif.cirad.fr/share/page/site/PALMstudio/documentlibrary#filter=path%7C%2FData%2FLight_interception_vs_ages%7C&page=1}

This project aims at comparing the light interception of oil palm plants of different ages in a regular quincunx planting design using ARCHIMED. The simulation parameterization is available on the Alfresco repository.

### N_mapping \badgegithub{https://github.com/PalmStudio/N_mapping} \badgealfresco{https://collaboratif.cirad.fr/share/page/site/PALMstudio/documentlibrary#filter=path%7C%2FData%2FN_mapping%7C&page=1}

This project aims at interpreting the N content distribution according to oil palm leaf rank and extract a correction factor for the parameters of the \cite{farquhar1980} photosynthesis model.

### Farquhar \badgegithub{https://github.com/PalmStudio/Farquhar} \badgealfresco{https://collaboratif.cirad.fr/share/page/site/PALMstudio/documentlibrary#filter=path%7C%2FData%2FFarquhar%7C&page=1}

This project aims at fitting the \cite{farquhar1980} model parameters using field data on oil palm plants.

### PLPE \badgegithub{https://github.com/PalmStudio/PLPE} \badgealfresco{https://collaboratif.cirad.fr/share/page/site/PALMstudio/documentlibrary#filter=path%7C%2FData%2FPLPE%7C&page=1}

This is a repository to simulate the biophysical properties of a palm oil plantation trial to study the effect of the planting design on production.

### Biophysics\_database\_palm \badgegithub{https://github.com/PalmStudio/Biophysics_database_palm}

This is the repository used for our experimentation in the [Ecotron](https://www.ecotron.cnrs.fr/) for the evaluation of the ARCHIMED model. We measured the temperature, CO2 and water fluxes of four young palm plants in a microcosm with different climate scenarios, *i.e.* different conditions for air temperature, humidity, radiation and CO2 concentration. The 3D architecture of the plants was also measured using two methods: LiDAR scanning, and photogrammetry.

The data will be published as a data paper very soon, and will be hosted on CIRAD's dataverse.

## XPalm

Projects about XPalm will be available here soon.

## References

* \biblabel{farquhar1980}{Farquhar et al. (1980)} Farquhar, G. D., S. von von Caemmerer, et J. A. Berry. 1980. « A biochemical model of photosynthetic CO2 assimilation in leaves of C3 species ». Planta 149 (1): 78‑90.
* \biblabel{medlyn2011}{Medlyn et al. (2011)}Medlyn, Belinda E., Remko A. Duursma, Derek Eamus, David S. Ellsworth, I. Colin Prentice, Craig V. M. Barton, Kristine Y. Crous, Paolo De Angelis, Michael Freeman, et Lisa Wingate. 2011. « Reconciling the optimal and empirical approaches to modelling stomatal conductance ». Global Change Biology 17 (6): 2134‑44. https://doi.org/10.1111/j.1365-2486.2010.02375.x.
