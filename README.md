# Lauderdale_etal_2017_CD

MITgcm input and pickup files for 3 degree simulations with variable KGM parameterizations according to:

• Visbeck, Marshall, Haine and Spall, 1997, JPO (VMHS97), using a upper ocean average of the Richardson number to vary KGM, 

• Ferreira, Marshall and Heimbach, 2005, JPO (FMH2005), using a vertically varying relationship between N2 and KGM,

• Hofmann and Morales Maqueda, 2011, GRL (HMM2011), using the depth-varying Richardson number to vary KGM.

Each parameterization has 7 experiments associated with it: a control and 6 Southern Hemisphere Westerly wind (SHW) perturbations (50% increased, 50% decreased, 10° north-shift, 10° south-shift, 3° north-shift and slight decrease, 3° south-shift and slight increase) each run for 10,000 model years. The control spin up covers iterations 0014400000 to 0021600000 (20 kyr to 30 kyr) and the perturbations cover iterations 0021600000 to 0028800000 (30 kyr to 40 kyr).

The code for these parameterizations can be found in my "mitgcm_mods" repo (https://github.com/seamanticscience/mitgcm_mods) under "gm_variable_k"  - probably best to check out the "Checkpoint66j" version (although the original experiments were done with the much older "Checkpoint63m" release). Make sure "GM_VISBECK_VARIABLE_K" is defined in GMREDI_OPTIONS.h before compiling and that "gm_variable_k" is included in your "mods" list in the "Genmake2" step. For VMHS97 runs, that is all you need to do - the parameter values GM_Visbeck_alpha, GM_Visbeck_length, GM_Visbeck_minDepth, GM_Visbeck_depth, GM_Visbeck_maxVal_K and GM_Visbeck_minVal_K are set in "data.gmredi" to the values used in the paper. For FMH2005 and HMM2011 experiments, one or the other of "GM_useFMH2005" or "GM_useHMM2011" is set to ".TRUE." in data.gmredi and the GM_Visbeck_alpha, GM_Visbeck_length, GM_Visbeck_minDepth, GM_Visbeck_depth, GM_Visbeck_maxVal_K and GM_Visbeck_minVal_K values are set for the HMM2011 parameterization (they are ignored in the FMH2005 calculations). These were tested using the skew-flux form of the GMREDI package, but they should work with the flux-form too.

If you use these code/config/pickup files, please cite:
Lauderdale, Williams, Munday and Marshall, 2017, The impact of Southern Ocean residual upwelling on atmospheric CO2 on centennial and millennial timescales, Climate Dynamics, 48, 1611–1631, http://dx.doi.org/10.1007/s00382-016-3163-y.

Please let me know if you find any errors, or have trouble compiling!
