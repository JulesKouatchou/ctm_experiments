# <span style="color: red">GEOS CTM Experiments</span>

## [Description](#)

The settings below provide general information on how to identify a GEOS CTM experiment.

| Experiment Info | Setting                            |
|             --- | ---                                |
| GEOS CTM Tag    | Icarus-3_2_p9_CTM_MEM_16-r4-SLES12 |
| Forcing Data    | MERRA2                             |
| Configuration   | TR+GCT                                 |
| Experiment Type | Transport                          |
| Beginning Date  | 20000101  |
| Model Resolution| C180                               |
| Restart Source  | MERRA2_GMI at C180                 |
| Experiment Name | M2_TR-GCT_Trans_20000101               |
| Working Directory | /discover/nobackup/jkouatch/GEOS_CTM/Icarus-3_2_p9_CTM_MEM_16-r4-SLES12/M2_TR-GCT_Trans_20000101 |
| History Resolution |  360x181 (lat-lon grid)             |
| Archive Directory | /archive/u/jkouatch/GEOSctm/M2_TR-GCT_Trans_20000101 |

- The 01January2000 restart file was created by running the Icarus-3_2_p9_CTM_MEM_16-r3-SLES12 tag (starting from a MERRA2-GMI 16June1999 restart - see the end of this document). 
- The 01January2000 restart file was modified by setting `aoa_bl` to `aoa`.

## [Changes in the RC Files](#)

The following RC files were modified (with respect to the default settings)

* `CTM_GridComp.rc`: The variable output_forcingData was set to T.

* `GEOS_ChemGridComp.rc1: The variables ENABLE_PCHEM, ENABLE_GOCART and ENABLE_TR were all set to TRUE.

* `Chem_Registry.rc`: Use the 24 TR tracers listed in the `tavg3d_tracers` HISTORY collection

* `TR_ExtData.rc`:

     - SF6 Emissions:   M2G (576x361, covering 1998–2020)
     - Rn222 Emissions: **Zhang, Liu et al** (there is also the option to use **Jacob et al**)

* In the files `TR_GridComp---Be10.rc`,  `TR_GridComp---Be7.rc`, `TR_GridComp---Be10s.rc`, 
  `TR_GridComp---Be7s.rc`, `TR_GridComp---Pb210.rc`, `TR_GridComp---Pb210s.rc`,
  the radionuclides will use the GOCART schemes for convection and scavenging
  
* `TR_GridComp---Rn222.rc`: `surface_constraint_count` remains set to 0.

## [HISTORY Collections](#)

- `tavg3d_tracers_p` (460 Mb/day)
     * **Mode**: Time averaged
     * **Frequency**: 24 hours
     * **Duration**:  24 hours
     * **Pressure levels**: 1000 975 950 925 900 875 850 825 800
                         775 750 725 700 650 600 550 500 450
                         400 350 300 250 200 150 125 100  85
                          70  50  40  30  20  10   7   5   4
                           3   2   1 0.7 0.5 0.4 0.3 0.1
     * **Fields**:  CO_25, CO_50,  CO_50_ea, CO_50_na, CO_50_eu, CO_50_sa
                    e90,   e90_n,  e90_s,    nh_5,     nh_50,    st80_25
                    aoa,   aoa_nh, aoa_bl,   Pb210,    Pb210s,   CH4I
                    Be7,   Be7s,   Be10,     Be10s,    SF6,      Rn222
                    CO_GLB, CO_GLB_BB, CO_GLB_BB_NMVOC, CO_GLB_BIOG_NMVOC
                    CO_GLB_ANTHRO, CO_NAM_ANTHRO, CO_EUR_ANTHRO, CO_SAS_ANTHRO
                    CO_EAS_ANTHRO, CO_SEA_ANTHRO, CO_GLB_ANTHRO_NMVO, CO_NAM_ANTHRO_NMVOC
                    CO_EUR_ANTHRO_NMVOC, CO_SAS_ANTHRO_NMVOC, CO_EAS_ANTHRO_NMVOC, CO_SEA_ANTHRO_NMVOC

- `tavg3d_tracers_v` (300 Mb/day)
     * **Mode**: Time averaged
     * **Frequency**: 24 hours
     * **Duration**:  24 hours
     * **Fields**:  PS, CO_GLB, CO_GLB_BB, CO_GLB_BB_NMVOC, CO_GLB_BIOG_NMVOC
                    CO_GLB_ANTHRO, CO_NAM_ANTHRO, CO_EUR_ANTHRO, CO_SAS_ANTHRO
                    CO_EAS_ANTHRO, CO_SEA_ANTHRO, CO_GLB_ANTHRO_NMVO, CO_NAM_ANTHRO_NMVOC
                    CO_EUR_ANTHRO_NMVOC, CO_SAS_ANTHRO_NMVOC, CO_EAS_ANTHRO_NMVOC, CO_SEA_ANTHRO_NMVOC
                    
 - `tavg3d_trdiag_v` (680 Mb/day)
     * **Mode**: Time averaged
     * **Frequency**: 24 hours
     * **Duration**:  24 hours
     * **Fields**:  Rn222, Pb210,  Be7, Be10, Pb210s, Be7s, Be10s
                    AIRDENS, AIRDENS_DRYP, DELP, LWI, PS, LWI, PHI, TROPP
                    EM_Rn222, EM_Be7, EM_Be7s, EM_Be10, EM_Be10s
                    PRtend_Pb210, PRtend_Pb210s
                    DK_Be7, DK_Be7s, DK_Be10, DK_Be10s, DK_Pb210, DK_Pb210s, DK_Rn222
                    DD_Be7, DD_Be7s, DD_Be10, DD_Be10s, DD_Pb210, DD_Pb210s
                    WRtend_Be7, WRtend_Be7s, WRtend_Be10, WRtend_Be10s, WRtend_Pn210, WRtend_Pb210s
                    WD_Be7, WD_Be7s, WD_Be10, WD_Be10s, WD_Pb210, WD_Pb210s
                    CVtend_Be7, CVtend_Be7s, CVtend_Be10, CVtend_Be10s, CVtend_Pb210, CVtend_Pb210s, CVtend_Rn222
 
 
 - `tavg3d_aer_p` (252 Mb/day)
     * **Mode**: Time averaged
     * **Frequency**: 24 hours
     * **Duration**:  24 hours
     * **Pressure levels**: 1000 975 950 925 900 875 850 825 800
                         775 750 725 700 650 600 550 500 450
                         400 350 300 250 200 150 125 100  85
                          70  50  40  30  20  10   7   5   4
                           3   2   1 0.7 0.5 0.4 0.3 0.1
     * **Fields**:   LWI, PS, RH, AIRDENs
                     DU, SS, BC, OC, CO, CO2, SO2, SO4, NH3, NH4, NI
                     HNO3CONC, NICONC


 - `tavg3d_aer_v` (778 Mb/day)
     * **Mode**: Time averaged
     * **Frequency**: 24 hours
     * **Duration**:  24 hours
     * **Fields**:   ps, delp, LWI, RH
                     CO2, CO, du001, du002, du003, du004, du005, ss001, ss002, ss003, ss004, ss005
                     DMS, SO2, SO4, MSA, NH3, NH4a, NO3an1, NO3an2, NO3an3
                     BCphobic, BCphilic, OCphobic, OCphilic, pSO4tot, pSO4, pSO4g, pSO4aq, pSO4wt

 - `tavg3d_aerdiag_v` (634 Mb/day)
     * **Mode**: Time averaged
     * **Frequency**: 24 hours
     * **Duration**:  24 hours
     * **Fields**:   ps, delp, LWI, RH, AIRDENS
                     DUCONC, DUEXTCOEF, DUSCACOEF, SSCONC, 
                     SSEXTCOEF, SSSCACOEF, NH4CONC, NH3CONC, HNO3CONC, NICONC, 
                     NIEXTCOEF, NISCACOEF, SUCONC, SUEXTCOEF, SUSCACOEF, SUCONCanth, BCCONC
                     BCEXTCOEF, BCSCACOEF, BCCONCanth, BCCONCbiob, OCCONC, OCEXTCOEF, OCSCACOEF

 - `tavg2d_chm_x` ( 2.8 Mb/day)
     * **Mode**: Time averaged
     * **Frequency**: 24 hours
     * **Duration**:  24 hours
     * **Fields**:    LWI
                     CO2EM001, CO2SC001, CO2CL001, COEM, COPD, COLS, COSC, COCL

 - `tavg2d_aer_x` (77 mb/days)
     * **Mode**: Time averaged
     * **Frequency**: 24 hours
     * **Duration**:  24 hours
     * **Fields**:   LWI, TOTEXTTAU, TOTSCATAU, TOTANGSTR, 
                     DUEM001, DUEM002, DUEM003, DUEM004, DUEM005
                     DUSD001, DUSD002, DUSD003, DUSD004, DUSD005
                     DUDP001, DUDP002, DUDP003, DUDP004, DUDP005
                     DUWT001, DUWT002, DUWT003, DUWT004, DUWT005
                     DUSV001, DUSV002, DUSV003, DUSV004, DUSV005
                     DUSMASS, DUCMASS, DUEXTTAU, DUSCATAU, DUANGSTR, DUEXTTFM, DUSCATFM
                     DUSMASS25, DUCMASS25, DUEXTT25, DUSCAT25, DUAERIDX, DUFLUXU, DUFLUXV
                     SSEM001, SSEM002, SSEM003, SSEM004, SSEM005
                     SSSD001, SSSD002, SSSD003, SSSD004, SSSD005
                     SSDP001, SSDP002, SSDP003, SSDP004, SSDP005
                     SSWT001, SSWT002, SSWT003, SSWT004, SSWT005
                     SSSV001, SSSV002, SSSV003, SSSV004, SSSV005
                     SSSMASS, SSCMASS, SSEXTTAU, SSSCATAU, SSANGSTR, SSEXTTFM, SSSCATFM
                     SSSMASS25, SSCMASS25, SSEXTT25, SSSCAT25, SSAERIDX, SSFLUXU, SSFLUXV
                     SUEM001, SUEM002, SUEM003, SUEM004, SUSD001, SUSD002, SUSD003, SUSD004
                     SUDP001, SUDP002, SUDP003, SUDP004, SUWT001, SUWT002, SUWT003, SUWT004
                     SUSV001, SUSV002, SUSV003, SUSV004, SO2SMASS, SO2CMASS, SO4SMASS, SO4CMASS
                     DMSSMASS, DMSCMASS, SUPSO2, SUPSO4G, SUPSO4AQ, SUPSO4WT, SUPMSA, SUEXTTAU
                     SUSCATAU, SUANGSTR, SO4EMAN, SO2EMAN, SO2EMBB, SO2EMVN, SO2EMVE, SUFLUXU
                     SUFLUXV, BCEM001, BCEM002, BCSD001, BCSD002, BCDP001, BCDP002, BCWT001, BCWT002
                     BCSV001, BCSV002, BCSMASS, BCCMASS, BCEXTTAU, BCSCATAU, BCANGSTR, BCHYPHIL
                     BCEMBB, BCEMBF, BCEMAN, BCFLUXU, BCFLUXV, OCEM001, OCEM002, OCSD001, OCSD002
                     OCDP001, OCDP002, OCWT001, OCWT002, OCSV001, OCSV002, OCSMASS, OCCMASS, OCEXTTAU
                     OCSCATAU, OCANGSTR, OCEMBB, OCEMBF, OCEMAN, OCEMBG, OCHYPHIL, OCFLUXU, OCFLUXV
                     HNO3SMASS, NH3SMASS, NH4SMASS, NISMASS, NISMASS25, HNO3CMASS, NH3CMASS', NH4CMASS
                     NICMASS, NICMASS25, NIEXTTFM, NISCATFM, NIEXTTAU, NISCATAU, NIANGSTR, NIFLUXU
                     NIFLUXV, NIPNO3AQ, NIPNH4AQ, NIPNH3AQ, NIHT001, NIHT002, NIHT003, NISD001, NISD002
                     NISD003, NIDP001, NIDP002, NIDP003, NIWT001, NIWT002, NIWT003, NISV001, NISV002
                     NISV003, NH3EM, NH3DP, NH3WT, NH3SV, NH4SD, NH4DP, NH4WT, NH4SV

 - `inst2d_hwl_x` (230 Mb/day)
     * **Mode**: instantaneous
     * **Frequency**: 01 hours
     * **Duration**:  24 hours
     * **Fields**:   TOTEXTTAU, TOTSCATAU, TOTANGSTR, DUEXTTAU, SSEXTTAU,  SUEXTTAU,  BCEXTTAU
                     OCEXTTAU,  NIEXTTAU,  DUSMASS,   SSSMASS,  DUSMASS25, SSSMASS25, 
                     SO4SMASS,  SO2SMASS,  BCSMASS,   OCSMASS,  NISMASS,   NISMASS25, PM, PM25
                


## [Changes in the TR Restart File](#)

The MERRA2_GMI restart file for TR was modified in the following way:

**Conversion from mol/mol to kg/kg**:

     Be10   = 10.0*Be10/28.965
     Be7    = 7.0*Be7/28.965
     Pb210  = 210.0*Pb210/28.965
     Rn222  = 222.0*Rn222/28.965

**Scaling of nh_5 and nh_50**:

     nh_5   = 0.001*nh_5
     nh_50  = 0.001*nh_50
     
**Addition of new tracers**:

     Be7s   = Be7
     Be10s  = Be10
     Pb210s = Pb210
