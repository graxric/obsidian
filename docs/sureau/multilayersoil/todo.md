TODOs for getting a SurEau-Ecos version that is independent of the number of soil layers

>[!note] Todo Notiz
> asdsadsad
> asdsad

> [!NOTE] TODO Notiz
> Text


> [!NOTE]- Ausklappbare TODO Notiz
> Ausklapptext

## Input and parameterization
* [ ] get rid of input parameters like depth1, depth2, depth3 and instead make it one parameter whose length determines the amount of layers, e.g. "depth;0.2;0.5;1" indicating 3 layers of lengths 0.2, 0.5, and 1 meters, respectively
* [ ] instead of vegetation and soil parameter inputs, it would be easier to each have a function that contains all default parameters and where you can adjust the ones needed, e.g. soil_paras(depth=c(0.2,0.5,1), n_vg=c(1.1,1.5,1), Kat_vg=30, RFC=c(0.3,0.6,0.5), ...). parameters will either have to be the length of the amount of layers or 1 (in which case they are recycled)

## Output
* [ ] flexible output independent of number of soil layers, e.g. fluxSoilToStem1_mm, ...2, ... fluxSoilToStemN_mm and other output columns

## Soil functions
* [ ] vectorization-compatible functions (i.e. in functionsWBsoil.R) to flexibly work with any amount of rows in WBsoil (i.e. soil layers)
	* [ ] functionsWBsoil.R
	* [ ] create.soil.parameters.R
* [ ] full richards(on)
	* [ ] incorporate capillary uptake
	* [ ] account for excess water when theta>1, e.g. in pptSoil to let it re-infiltrate when possible or re-allocate to different soil layer. what about ponding water at the surface when no surface runoff exists? this will introduce too much infiltration, especially in heavy rainfall events.
* [ ] introduce a lower boundary condition to account for a (fully) saturated bottom layer, e.g. groundwater that can also influence above soil layers through capillary uptake

## Plant functions
* [ ] root water uptake via beta root profile to work with any amount of layers
* [ ] fluxes of each soil layer to stem

## misc
* [ ] check "TODO:" tags in the R files to solve additional TODOs
