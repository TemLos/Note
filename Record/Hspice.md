Name Alias Description MOSFET Level
L LV1 Channel Length (L)
This is also the effective channel length for all MOSFET models except Levels 54, 57, and 70. All
W LV2 Channel Width (W)
This is also the effective channel width for all MOSFET models except Levels 54 57, and 70. All
AD LV3 Area of the drain diode (AD) All
AS LV4 Area of the source diode (AS) All
ICVDS LV5 Initial condition for the drain-source voltage (VDS) All
ICVGS LV6 Initial condition for the gate-source voltage (VGS) All
ICVBS LV7 Initial condition for the bulk-source voltage (VBS) All except 57, 58, 59, 70, 71
ICVES LV7 Initial condition for the substrate-source voltage (VES) 57, 58, 59, 70, 71
- LV8 Device polarity:
1 = forward
-1 = reverse (not used after HSPICE release 95.3).
All
VTH LV9 Threshold voltage (bias dependent) All
VDSAT LV10 Saturation voltage (VDSAT) All
PD LV11 Drain diode periphery (PD) All
PS LV12 Source diode periphery (PS) All
RDS LV13 Drain resistance (squares) (RDS) All
RSS LV14 Source resistance (squares) (RSS) All
XQC LV15 Charge-sharing coefficient (XQC). All
GDEFF LV16 Effective drain conductance (1/RDeff), rgeoMod is not 0 All
GSEFF LV17 Effective source conductance (1/RSeff), rgeoMod is not 0 All
CDSAT LV18 Drain-bulk saturation current, at -1 V bias. All
CSSAT LV19 Source-bulk saturation current, at -1 V bias. All
VDBEFF LV20 Effective drain bulk voltage. All
BETAEFF LV21 BETA effective All
GAMMAEFF LV22 GAMMA effective All
DELTAL LV23 L (MOS6 amount of channel length modulation) 1, 2, 3, 6
UBEFF LV24 UB effective 1, 2, 3, 6
VG LV25 VG drive 1, 2, 3, 6
VFBEFF LV26 VFB effective. All
- LV31 Drain current tolerance (not used in HSPICE releases after 95.3). All
IDSTOL LV32 Source-diode current tolerance. All
IDDTOL LV33 Drain-diode current tolerance. All
COVLGS LV36 Gate-source overlap and fringing capacitances All
COVLGD LV37 Gate-drain overlap and fringing capacitances All
COVLGB LV38 Gate-bulk overlap capacitances All except 57, 59, 70, 71
COVLGE LV38 Gate-substrate overlap capacitances 57, 59, 70, 71
VBD L0 Bulk-drain voltage All
VBS LX1 Bulk-source voltage (VBS) All except 57, 59, 70, 71
VES LX1 Substrate-source voltage (VES) 57, 59, 70, 71
VGS LX2 Gate-source voltage (VGS) All
VDS LX3 Drain-source voltage (VDS) All
CDO LX4 Channel current (IDS) All
CBSO LX5 DC source-bulk diode current (CBSO) All
CBDO LX6 DC drain-bulk diode current (CBDO) All
GMO LX7 DC MOSFET gate transconductance (GMO)
Current is Ids, from drain-to-source,
Voltage is vgs
All
GDSO LX8 DC drain-source conductance (GDSO) All
GMBSO LX9 DC substrate transconductance (GMBSO) All except 57, 58, 59, 70, 71
GMESO LX9 DC substrate transconductance (GMBSO/GMESO) 57, 58, 59, 70, 71
GBDO LX10 Conductance of the drain diode (GBDO) All
GBSO LX11 Conductance of the source diode (GBSO) All
QB LX12 Total bulk (body) charge (QB)-Meyer and Charge Conservation All
CQB LX13 Bulk (body) charge current (CQB)-Meyer and Charge Conservation All
QG LX14 Total Gate charge (QG)-Meyer and Charge Conservation All
CQG LX15 Gate charge current (CQG)-Meyer and Charge Conservation All
QD LX16 Total Drain charge (QD) 49, 53
QD LX16 Channel charge (QD)-Meyer and Charge Conservation All except 49 and 53
CQD LX17 Drain charge current (CQD) 49, 53
CQD LX17 Channel charge current (CQD)-Meyer and Charge Conservation All except 49 and 53
CGGBO LX18 CGGBO = dQg/dVg = CGS + CGD + CGB - Meyer and Charge Conservation All except 54, 57, 59, 60, 70, 71
CGGBO LX18 Intrinsic gate capacitance 54, 57, 59, 60, 66, 70, 71
CGDBO LX19 CGDBO = -dQg/dVd - Meyer and Charge Conservation All except 54, 57, 59, 60, 66, 70, 71
CGDBO LX19 Intrinsic gate-to-drain capacitance 54, 57, 59, 60, 66, 70, 71
CGSBO LX20 CGSBO = -dQg/dVd - Meyer and Charge Conservation All except 54, 57, 59, 60, 66, 70, 71
CGSBO LX20 Intrinsic gate-to-source capacitance 54, 57, 59, 60, 66, 70, 71
CBGBO LX21 CBGBO = -dQb/dVg - Meyer and Charge Conservation All except 54, 57, 59, 60, 66, 70, 71
CBGBO LX21 Intrinsic bulk-to-gate capacitance 54, 66
CBGBO LX21 Intrinsic floating body-to-gate capacitance 57, 59, 60, 70, 71
CBDBO LX22 CBDBO = -dQb/dVd - Meyer and Charge Conservation All except 54, 57, 59, 60
CBDBO LX22 Intrinsic bulk-to-drain capacitance 54, 66
CBDBO LX22 Intrinsic floating body-to-drain capacitance 57, 59, 60, 70, 71
CBSBO LX23 CBSBO = -dQb/dVs - Meyer and Charge Conservation All except 54, 57, 59, 60, 66, 70, 71
CBSBO LX23 Intrinsic bulk-to-source capacitance 54, 66
CBSBO LX23 Intrinsic floating body-to-source capacitance 57, 59, 60, 70, 71
QBD LX24 Drain-bulk charge (QBD) All
- LX25 Drain-bulk charge current (CQBD), (not used in HSPICE releases after 95.3). All
QBS LX26 Source-bulk charge (QBS) All
- LX27 Source-bulk charge current (CQBS), (not used after HSPICE release 95.3). All
CAP_BS LX28 Extrinsic drain to substrate Capacitances-Meyer and Charge Conservation.CAP_BS=csbox+csesw
csbox is the substrate-to-source bottom capacitance
csesw is the substrate-to-source sidewall capacitance
57, 58, 70, 71
CAP_BS LX28 Bias dependent bulk-source capacitance All except 57, 58, 70, 71
CAP_BD LX29 Extrinsic source to substrate Capacitances-Meyer and Charge Conservation.CAP_BD=cdbox+cdesw
cdbox is the substrate-to-drain bottom capacitance
cdesw is the substrate-to-drain sidewall capacitance
57, 58, 70, 71
CAP_BD LX29 Bias dependent bulk-drain capacitance All except 57, 58, 70, 71
CQS LX31 Channel-charge current (CQS). All
CDGBO LX32 CDGBO = -dQd/dVg - Meyer and Charge Conservation All except 54, 57, 59, 60, 66, 70
CDGBO LX32 Intrinsic drain-to-gate capacitance 54, 57, 59, 60, 66, 70
CDDBO LX33 CDDBO = dQd/dVd - Meyer and Charge Conservation All except 54, 57, 59, 60, 66, 70, 71
CDDBO LX33 Intrinsic drain capacitance 54, 57, 59, 60, 66, 70, 71
CDSBO LX34 CDSBO = -dQd/dVs
Drain-to-source capacitance - Meyer and Charge Conservation All
QE LX35 Substrate charge (QE)-Meyer and Charge Conservation 57, 58, 59, 70, 71
CQE LX36 Substrate charge current (CQE)-Meyer and Charge Conservation 57, 58, 59, 70, 71
CDEBO LX37 CDEBO = -dQd/dVe intrinsic drain-to-substrate capacitance 57, 59, 70, 71
CBEBO LX38 CBEBO = -dQb/dVe intrinsic floating body-to-substrate capacitance 59, 70, 71
igso LX38 Gate-to-Source Current 54, 69
CEEBO LX39 CEEBO = dQe/dVe intrinsic substrate capacitance 59, 70, 71
igdo LX39 Gate-to-Drain Current 54, 69
CEGBO LX40 CEGBO = -dQe/dVg intrinsic substrate-to-gate capacitance 57, 59, 70, 71
CEDBO LX41 CEDBO = -dQe/dVd intrinsic substrate-to-drain capacitance 57, 59, 70, 71
CESBO LX42 CESBO = -dQe/dVs intrinsic substrate-to-source capacitance 57, 59, 70, 71
VBSI LX43 Body-source voltage (VBS)-Meyer and Charge Conservation 57, 58, 59, 70, 71
ICH LX44 Channel current-Meyer and Charge Conservation 57, 58, 59, 70, 71
IBJT LX45 Parasitic BJT collector current-Meyer and Charge Conservation 57, 58, 59, 70, 71
III LX46 Impact ionization current-Meyer and Charge Conservation 57, 58, 59, 70, 71
IGIDL LX47 GIDL current-Meyer and Charge Conservation 57, 58, 59, 70, 71
ITUN LX48 Tunneling current-Meyer and Charge Conservation 57, 58, 59, 70, 71
Qbacko LX49 Internal body charge 57, 59, 70, 71
Ibp LX50 Body contact current 57, 59, 70, 71
Sft LX51 Value of the temperature node with shmod=1 57, 59, 70, 71
VBFLOAT LX52 Internal body node voltage, if you do not specify the terminal 57, 59, 70, 71
Rbp LX53 Combination of rbody and rhalo 57, 59, 70, 71
IGB LX54 Gate tunneling current 57, 59, 70, 71
QSRCO LX55 Total Source charge (Charge Conservation: QS=-(QG+QD+QB)) 49, 53
QSRCO LX55 Total Source charge (Charge Conservation: QS=-(QG+QD+QB+QE)) 57, 59, 70, 71
CQs LX56 Source charge current 57, 59, 70, 71
CGEBO LX57 CGEBO = -dQg/dVe intrinsic gate-to-substrate capacitance 57, 59, 70, 71
CSSBO LX58 CSSBO = dQs/dVs intrinsic source capacitance 57, 59, 70, 71
CSGBO LX59 CSGBO = -dQs/dVg intrinsic source-to-gate capacitance 57, 59, 70, 71
CSDBO LX60 CSDBO = -dQs/dVd intrinsic source-to-drain capacitance 57, 59, 70, 71
CSEBO LX61 CSEBO = -dQs/dVe intrinsic source-to-substrate capacitance 57, 59, 70, 71
weff LX62 Effective channel width 54, 57, 66, 69, 70
leff LX63 Effective channel length 54, 57, 66, 69, 70
weffcv LX64 Effective channel width for CV 54, 66, 69
leffcv LX65 Effective channel length for CV 54, 66, 69
igbo LX66 Gate-to-Substrate Current (Igb = Igbacc + Igbinv) 54, 69
igcso LX67 Source Partition of Igc 54, 69
igcdo LX68 Drain Partition of Igc 54, 69
iimi LX69 Impact ionization current 54, 69
igidlo LX70 Gate-induced drain leakage current 54, 69
igdt LX71 Gate Dielectric Tunneling Current (Ig = Igs + Igd + Igcs + Igcd + Igb) 54, 69
igc LX72 Gate-to-Channel Current at zero Vds 54, 69
igbacc LX73 Determined by ECB (Electron tunneling from the Conduction Band); significant in the accumulation 54
igbinv LX74 Determined by EVB (Electron tunneling from the Valence Band); significant in the inversion 54
vfbsd LX75 Flat-band Voltage between the Gate and S/D diffusions 54, 66
vgse LX76 Effective Gate-to-Source Voltage 54, 66
vox LX77 Voltage Across Oxide 54, 66
rdv LX78 Asymmetric and Bias-Dependent Source Resistance, (rdsMod = 1) 54, 66
rsv LX79 Asymmetric and Bias-Dependent Drain Resistance, (rdsMod = 1) 54, 66
cap_bsz LX80 Zero voltage bias bulk-source capacitance 54, 66
cap_bdz LX81 Zero voltage bias bulk-drain capacitance 54, 66
CGGBM LX82 Total gate capacitance (including intrinsic), and all overlap and fringing components 54, 57, 59, 60, 66, 70, 69, 71
CGDBM LX83 Total gate-to-drain capacitance (including intrinsic), and overlap and fringing components 54, 57, 59, 60, 66, 69, 70, 71
CGSBM LX84 Total gate-to-source capacitance (including intrinsic), and overlap and fringing components 54, 57, 59, 60, 66, 69, 70, 71
CDDBM LX85 Total drain capacitance (including intrinsic), overlap and fringing components, and junction capacitance 54, 57, 59, 60, 66, 69, 70, 71
CDSBM LX86 Total drain-to-source capacitance 54, 57, 60, 66, 69, 70, 71
CDGBM LX87 Total drain-to-gate capacitance (including intrinsic), and overlap and fringing components 54, 57, 59, 60, 66, 69, 70, 71
CBGBM LX88 Total bulk-to-gate (floating body-to-gate) capacitance, including intrinsic and overlap components 54, 57, 59, 60, 66, 70, 71
CBDBM LX89 Total bulk-to-drain capacitance (including intrinsic), and junction capacitance 54, 66
CBDBM LX89 Total floating body-to-drain capacitance (including intrinsic), and junction capacitance. 57, 59, 60, 70, 71
CBSBM LX90 Total bulk-to-source capacitance (including intrinsic), and junction capacitance 54, 66
CBSBM LX90 Total floating body-to-source capacitance (including intrinsi)c, and junction capacitance. 57, 59, 60, 70, 71
CAPFG LX91 Fringing capacitance 54, 66
CDEBM LX92 Total drain-to-substrate capacitance (including intrinsi)c, and junction capacitance. 57, 59, 60, 70, 71
CSGBM LX93 Total source-to-gate capacitance (including intrinsic), and overlap and fringing components. 57, 59, 60, 70, 71
CSSBM LX94 Total source capacitance (including intrinsic), overlap and fringing components, and junction capacitance. 57, 59, 60, 70, 71
CSEBM LX95 Total source-to-substrate capacitance (including intrinsic), and junction capacitance. 57, 59, 60, 70, 71
CEEBM LX96 Total substrate capacitance (including intrinsic), overlap and fringing components, and junction capacitance. 57, 59, 60, 70, 71
QGI LX97 Intrinsic Gate charge 49, 53
QSI LX98 Intrinsic Source charge 49, 53
QDI LX99 Intrinsic Drain charge 49, 53
QBI LX100 Intrinsic Bulk charge (Charge Conservation:
QBI= -(QGI+ QSI+ QDI)) 49, 53
CDDBI LX101 Intrinsic drain capacitance 49, 53
CBDBI LX102 Intrinsic bulk-to-drain capacitance 49, 53
CBSBI LX103 Intrinsic bulk-to-source capacitance 49, 53
VBDI LX109 Body-drain voltage(VBD)-Meyer and Charge Conservation 57, 58, 59, 70, 71
IGISLO LX110 Gate-induced source leakage current 54
GRII LX118 Intrinsic channel reflected gate conductance 54
GRGELTD LX119 Gate electrode conductance 54
bs1 LX120 Bulk to source diffusion current 57, 59, 60
Ibd1 LX121 Bulk to drain diffusion current 57, 59, 60
Ibs2 LX122 Bulk to source recombination/trap-assisted tunneling current 57, 59, 60
Ibd2 LX123 Bulk to drain recombination/trap-assisted tunneling current 57, 59, 60
Ibs3 LX124 Bulk to source recombination current in neutral body 57, 59, 60
Ibd3 LX125 Bulk to drain recombination current in neutral body 57, 59, 60
Ibs4 LX126 Bulk to source reversed bias tunneling leakage current 57, 59, 60
Ibd4 LX127 Bulk to drain reversed bias tunneling leakage current 57, 59, 60
b4_sca LX128 sca for WPE effect 54
b4_scb LX129 scb for WPE effect 54
b4_scc LX130 scc for WPE effect 54
b4_sc LX131 sc for WPE effect 54
Ueff LX132 Effective mobility at the specified analysis temperature 66
VGB LX133 Gate to bulk voltage All
VDG LX134 Drain to gate voltage All
mult LX135 Prints value of multiplier (M) for a specified MOSFET All
b4_sa LX136 sa for STI or LOD-induced mechanical stress-effects 54
b4_sb LX137 sb for STI or LOD-induced mechanical stress-effects 54
b4_sd LX138 sd for STI or LOD-induced mechanical stress-effects 54
b4_nf LX139 nf for STI or LOD-induced mechanical stress