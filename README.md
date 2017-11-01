# Lauderdale_etal_2017_CD

MITgcm input and pickup files for 3 degree simulations with variable KGM parameterizations according to:
• Visbeck, Marshall, Haine and Spall, 1997, JPO (VMHS97), using a upper ocean average of the Richardson number to vary KGM, 
• Ferreira, Marshall and Heimbach, 2005, JPO (FMH2005), using a vertically varying relationship between N2 and KGM,
• Hofmann and Morales Maqueda, 2011, GRL (HMM2011), using the depth-varying Richardson number to var KGM.

The code for these parameterizations can be found in my "mitgcm_mods" repo under "gm_variable_k" https://github.com/seamanticscience/mitgcm_mods - probably best to use the "Checkpoint66j" version...

Each parameterization has 7 experiments associated with it: a control and 6 Southern Hemisphere Westerly wind (SHW) perturbations (50% increased, 50% decreased, 10° north-shift, 10° south-shift, 3° north-shift and slight decrease, 3° south-shift and slight increase) each run for 10,000 model years. The control spin up covers iterations 0014400000 to 0021600000 (20 kyr to 30 kyr) and the perturbations cover iterations 0021600000 to 0028800000 (30 kyr to 40 kyr).

http://dx.doi.org/10.1007/s00382-016-3163-y
