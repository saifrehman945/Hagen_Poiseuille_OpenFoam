# Hagen_Poiseuille_OpenFoam

This is a clone to OpenFOAM tutorials provided by [Joel Guerrero](https://wiki.openfoam.com/Hagen_Poiseuille_by_Joel_Guerrero) for version v12 OpenFAOM.
Initially these tutorials are available for OpenFOAM v6, creating issues running for latest versions. The following major changes are made for each case

* The following files are modified

  * controlDict
  * python notebooks
  * gnuplot scripts
  
* The following Files are removed as they are redundant for v12

  * constant/transportProperties
  * system/decomposeParDict
  * system/modifyMeshDict
  * system/sampleDict
  
* For Post Processing, postProcessing Utility is replaced by runtime sampling, creating sets in controlDict
* For case3, the mesh is now modified in blockMeshDict instead of modifyMesh utility

Runtime postprocessing is achieved using functions

```
    #includeFunc cellMax
        (
            name=maxdomain,
            p,
            U
        )
```
