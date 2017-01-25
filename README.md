The COBRAToolbox - COnstraint-Based Reconstruction and Analysis Toolbox
=======================================================================

|  Code Coverage |  MATLAB R2016b | MATLAB R2015b | MATLAB R2014b |
|--------|--------|--------|--------|
| [![codecov](https://codecov.io/gh/opencobra/cobratoolbox/branch/develop/graph/badge.svg)](https://codecov.io/gh/opencobra/cobratoolbox/branch/develop) | [![Build Status](https://prince.lcsb.uni.lu/jenkins/buildStatus/icon?job=COBRAToolbox-branches-auto/MATLAB_VER=R2016b)](https://prince.lcsb.uni.lu/jenkins/job/COBRAToolbox-branches-auto/MATLAB_VER=R2016b/) | [![Build Status](https://prince.lcsb.uni.lu/jenkins/buildStatus/icon?job=COBRAToolbox-branches-auto/MATLAB_VER=R2015b)](https://prince.lcsb.uni.lu/jenkins/job/COBRAToolbox-branches-auto/MATLAB_VER=R2015b/) | [![Build Status](https://prince.lcsb.uni.lu/jenkins/buildStatus/icon?job=COBRAToolbox-branches-auto/MATLAB_VER=R2014b)](https://prince.lcsb.uni.lu/jenkins/job/COBRAToolbox-branches-auto/MATLAB_VER=R2014b/) |

Installation
------------

1. Clone this repository
  ```bash
  git clone https://github.com/opencobra/cobratoolbox.git cobratoolbox
  ```

2. Initialize submodules

  For convenience, we provide the [`SBMLToolbox 4.1.0`](http://sbml.org/Software/SBMLToolbox), and [`glpk_mex`](https://github.com/blegat/glpkmex) in `external/toolboxes`, [`libSBML-5.13.0-matlab`](http://sbml.org/Software/libSBML) in `io/utilities`.
  Binaries for these librairies are provided in a [submodule](https://github.com/opencobra/COBRA.binary) for Mac OS X 10.6 or later (64-bit), GNU/Linux Ubuntu 10.0 (64-bit), and Microsoft Windows 7 (64-bit).
  For unsupported OS, please refer to their respective building instructions ([`glpk_mex`](https://github.com/blegat/glpkmex#instructions-for-compiling-from-source), [`libSBML`](http://sbml.org/Software/libSBML/5.13.0/docs//cpp-api/libsbml-installation.html)).
  ```bash
  git submodule init
  ```

3. Update submodules
  ```bash
  git submodule update
  ```

4. From MATLAB, run
  ```Matlab
  initCobraToolbox
  ```
  NOTE: If you do not have `gurobi_mex` and `tomlab` installed on your machine, you will get some warnings and some errors. The `COBRAToolbox` will try to use `glpk` if it cannot find `gurobi` for LP / MILP.  To solve any NLP problems you need `tomlab_snopt`.

5. Test your installation, run
  ```Matlab
  testAll
  ```
  to see what functions will work with your current configuration.
  Note, it is likely that one or more functions will not work unless you have `tomlab` with `snopt` installed.


Citation policy
---------------

When citing `The COBRA Toolbox`, it is important to cite the original paper where an algorithm was first reported, as well as its implementation in `The COBRA Toolbox`. This is important, because the objective of `The COBRA Toolbox` is to amalgamate and integrate the functionality of a wide range of COBRA algorithms and this will be undermined if contributors of new algorithms do not get their fair share of citations. The following is one example how to approach this within the methods section of a paper (**not** the supplemental material please):

*To generate a context-specific model the FASTCORE algorithm [1], implemented in The COBRA Toolbox [2], was employed.*

>[1] = Vlassis N, Pacheco MP, Sauter T (2014) Fast Reconstruction of Compact Context-Specific Metabolic Network Models. PLoS Comput Biol 10(1): e1003424.
>

>[2] = Schellenberger J, Que R, Fleming RMT, Thiele I, Orth JD, Feist AM, Zielinski DC, Bordbar A, Lewis NE, Rahmanian S, Kang J, Hyduke DR, Palsson BØ. 2011 Quantitative prediction of cellular metabolism with constraint-based models: The COBRA Toolbox v2.0. Nature Protocols 6:1290-1307.
>

[Read more on the compatibility with SBML-FBCv2](NOTES.md)
