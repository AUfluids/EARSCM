# EARSCM
Explicit algebraic Reynolds stress correction model (EARSCM) enhanced for the prediction of secondary flows based on RANS $k-\omega$ SST turbulence model.
Developed by Fluid Physics & Turbulence research group at Aarhus University.

EARSCM - Implementation of the EARSCM RANS model
         as proposed by Rincón and Amarloo (2023) for OpenFOAM.

Copyright Information
    Copyright © 2004-2018 OpenCFD Ltd (ESI Group)

## License
    This program is free software: you can redistribute and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.

## Description
Implementation of the Explicit algebraic Reynolds stress correction model (EARSCM)
enhanced for the prediction of secondary flows based on standard RANS $k-\omega$ SST.
The model has been developed for 2D flows but its applicability has been tested on 3D
flows, yielding similar results.
Three coefficients can be modified by the user to change the model's performance.
Standard optimised values are given by default in the model.

## Target platform
The code is known to work with OpenFOAM v2212.

## Authors
Mario Javier Rincón <mjrp@mpe.au.dk>
Ali Amarloo <amarloo@mpe.au.dk>

## Instructions

1. Download the source code using git:

         git clone https://github.com/AUfluids/EARSCM.git

2 .Enter the directory where the source code has been extracted, and compile it by typing: 

         wmake

3. Add the following line to the _controlDict_ of your case:

         libs ( "libEARSCMIncompressibleTurbulenceModels" ) ;

4. Specify

         RASModel kOmegaSSTEARSCM2D;

in _turbulentProperties_.

5. Add the subdictionary

         EARSCM 2;  // 0: off | 1: ModelI | 2: ModelII
z
to _turbulentProperties_.

NOTE: You might have to define the bijDelta term in fvSchemes, here you have an example:

         divSchemes
         {
                  div(dev(((2*k)*bijDelta)))          Gauss linear;
         }

## Test results

For more details, refer to the publication at: LINK Progressive augmentation of Reynolds stress tensor models for secondary flow prediction by computational fluid dynamics driven surrogate optimisation

Qualitative results for a duct flow of aspect ratio 1 at bulk Reynolds number 3500 for Model **II**:
![alt text](https://github.com/AUfluids/EARSCM/blob/main/testCases/ductFlowAR1Reb3500/SD_u.png)
Quantitative results:
![alt text](https://github.com/AUfluids/EARSCM/blob/main/testCases/ductFlowAR1Reb3500/SD_profiles.png)

## How to cite
Please, cite this library using the following DOI: DOI.

Rincón and Amarloo (2023)

         @article{rinconAmarloo2023progressive,
           title={Progressive augmentation of Reynolds stress tensor models for secondary flow prediction by computational fluid dynamics driven surrogate optimisation},
           author={Rinc{\'o}n, Mario Javier and Amarloo, Ali and Reclari, Martino and Yang, Xiang and Abkar, Mahdi},
           journal={Internaltional Journal of Heat and Fluid Flow(submitted)},
           volume={000},
           pages={0000},
           year={2023},
           publisher={Elsevier}
         }

(under review)

For release-specific DOIs, click on the badge and find the DOI corresponding to the desired version in the version list.

## Disclaimer
This offering is not approved or endorsed by OpenCFD Limited, the producer of the OpenFOAM software and owner of the OPENFOAM® and OpenCFD® trade marks.

Detailed information on the OpenFOAM trademark can be found at

http://www.openfoam.com/legal/trademark-policy.php
http://www.openfoam.com/legal/trademark-guidelines.php
For further information on OpenCFD and OpenFOAM, please refer to

http://www.openfoam.com
