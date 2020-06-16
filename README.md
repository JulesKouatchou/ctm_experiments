# <span style="color: red">GEOS CTM Experiments</span>

## [Description](#)

The settins below provide general information on how to identify a GEOS CTM experiment.

| Experiment Info | Setting                            |
|             --- | ---                                |
| GEOS CTM Tag    | Icarus-3_2_p9_CTM_MEM_16-r3-SLES12 |
| Forcing Data    | MERRA2                             |
| Configuration   | TR+GCT                                 |
| Experiment Type | Transport                          |
| Beginning Date  | 20000101                           |
| Model Resolution| C180                               |
| Restart Source  |                                    |
| Experiment Name | M2_TR-GCT_Trans_20000101               |
| Working Directory | /discover/nobackup/jkouatch/GEOS_CTM/Icarus-3_2_p9_CTM_MEM_16-r3-SLES12/M2_TR-GCT_Trans_20000101 |
| History Resolution |  360x181 (lat-lon grid)             |
| Archive Directory | /archive/u/jkouatch/GEOSctm/M2_TR-GCT_Trans_20000101 |

## [Changes in the RC Files](#)

The following RC files were modified (with respect to the default settings)

* `Chem_Registry.rc`: Use the 24 TR tracers listed in the `tavg3d_tracers` HISTORY collection

* `TR_ExtData.rc`:

     - SF6 Emissions:   M2G (576x361, covering 1998–2020)
     - Rn222 Emissions: **Jacob et al** or **Zhang, Liu et al**

* In the files `TR_GridComp---Be10.rc`,  `TR_GridComp---Be7.rc`, `TR_GridComp---Be10s.rc`, 
  `TR_GridComp---Be7s.rc`, `TR_GridComp---Pb210.rc`, `TR_GridComp---Pb210s.rc`,
  the radionuclides will use the GOCART schemes for convection and scavenging

## [HISTORY Collections](#)

- `tavg3d_tracers_p`
     * **Mode**: Time averaged
     * **Frequency**: 24 hours
     * **Duration**:  24 hours
     * **Pressure levels**: 1000 975 950 925 900 875 850 825 800
                         775 750 725 700 650 600 550 500 450
                         400 350 300 250 200 150 125 100  85
                          70  50  40  30  20  10   7   5   4
                           3   2   1 0.7 0.5 0.4 0.3 0.1
     * **Tracers**: CO_25, CO_50,  CO_50_ea, CO_50_na, CO_50_eu, CO_50_sa
                e90,   e90_n,  e90_s,    nh_5,     nh_50,    st80_25
                aoa,   aoa_nh, aoa_bl,   Pb210,    Pb210s,   CH4I
                Be7,   Be7s,   Be10,     Be10s,    SF6,      Rn222
 
 - `tavg3d_aer_p`
     * **Mode**: Time averaged
     * **Frequency**: 24 hours
     * **Duration**:  24 hours
     * **Pressure levels**: 1000 975 950 925 900 875 850 825 800
                         775 750 725 700 650 600 550 500 450
                         400 350 300 250 200 150 125 100  85
                          70  50  40  30  20  10   7   5   4
                           3   2   1 0.7 0.5 0.4 0.3 0.1
     * **Aerosols**: DU, SS, BC, OC, CO, CO2,  SO2, SO4, NH3, NH4, NI
                HNO3CONC,   NICONC


 - `tavg3d_aer_v`
     * **Mode**: Time averaged
     * **Frequency**: 24 hours
     * **Duration**:  24 hours
     * **Aerosols**: CO2, CO, COBBAE, COBBNA, COBBLA, COBBAF, COBBGL, CONBAS, CONBNA, CONBEU, CONBGL
                du001, du002, du003, du004, du005, ss001, ss002, ss003, ss004, ss005
                DMS, SO2, SO4, MSA, NH3, NH4a, NO3an1, NO3an2, NO3an3
                BCphobic, BCphilic, OCphobic, OCphilic, pSO4tot, pSO4, pSO4g, pSO4aq, pSO4wt
