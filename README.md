# EARSCM
Explicit algebraic Reynolds stress correction model (EARSCM) enhanced for the prediction of secondary flows based on k-omega SST

EARSCM - Implementation of the EARSCM RANS model
         as proposed by Rincón and Amarloo (2023) for OpenFOAM.

Copyright Information
    Copyright (C) 1991-2009 OpenCFD Ltd.

# License
    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.

# Description
Implementation of the Explicit algebraic Reynolds stress correction model (EARSCM)
enhanced for the prediction of secondary flows based on standard k-omega SST.
Three coefficients can be tuned by the user to change the model's performance.
Stardard optmised values are given by the model.

# Target platform
The code is known to work with OpenFOAM v2212.

# Authors
Mario Javier Rincón <mjrp@mpe.au.dk>
Ali Amarloo <amarloo@mpe.au.dk>

# Instructions

1. Download the source code using git:

         git clone git://github.com/AUfluids/EARSCM.git

2 .Enter the directory where the source code has been extracted, and compile it by typing: 

         wmake libso

3. Add the following line to the _controlDict_ of your case:

         libs ( "libOpenFOAM.so" "libEARSCM.so" ) ;

4. Specify

         RASModel EARSCM;

in _turbulentProperties_.

5. Add the subdictionary

         EARSCM { model PCA; c0 -0.17; c1 -0.18; c2 0.98; }

to _turbulentProperties_.

# How to cite
Please, cite this library using the following DOI: DOI.

         Rincón and Amarloo (2023)
         @article{rinconAmarloo2023progressive,
           title={Progressive augmentation of Reynolds stress tensor models for secondary flow prediction by computational fluid dynamics driven surrogate optimisation},
           author={Rinc{\'o}n, Mario Javier and Amarloo, Ali and Reclari, Martino and Abkar, Mahdi},
           journal={International Journal of Heat and Fluid Flow},
           volume={100},
           pages={109112},
           year={2023},
           publisher={Elsevier}
         }        

For release-specific DOIs, click on the badge and find the DOI corresponding to the desired version in the version list.

# Disclaimer
This offering is not approved or endorsed by OpenCFD Limited, the producer of the OpenFOAM software and owner of the OPENFOAM® and OpenCFD® trade marks.

Detailed information on the OpenFOAM trademark can be found at

http://www.openfoam.com/legal/trademark-policy.php
http://www.openfoam.com/legal/trademark-guidelines.php
For further information on OpenCFD and OpenFOAM, please refer to

http://www.openfoam.com
