# GCD RTL-to-GDSII Implementation Using OpenROAD

## Project Overview

This project demonstrates the RTL-to-GDSII physical design implementation of a Greatest Common Divisor (GCD) circuit using the OpenROAD automated RTL-to-GDS flow.

The design was implemented using the SkyWater 130nm High-Density (Sky130HD) standard-cell library. The flow covers logic synthesis, floorplanning, placement, clock-tree synthesis, routing, timing analysis and final GDSII generation.

The project provided hands-on experience with the digital ASIC physical design flow and analysis of key physical design metrics, including area, timing, routing and power.

## Tools

- **RTL Synthesis:** Yosys
- **Physical Design:** OpenROAD
- **Flow:** OpenROAD-flow-scripts (ORFS)
- **Technology Library:** Sky130HD
- **Layout Inspection:** KLayout
- **Environment:** Ubuntu on WSL2, Docker

## RTL-to-GDSII Flow

The following stages were executed:

1. **Logic Synthesis:** RTL converted into a gate-level netlist using Yosys.
2. **Floorplanning:** Die and core dimensions initialized.
3. **Power Distribution Network:** Power grid generation.
4. **Placement:** Global placement, optimization and detailed placement.
5. **Clock Tree Synthesis:** Clock distribution network generation.
6. **Global Routing:** Estimation of routing resources.
7. **Detailed Routing:** Signal routing and design-rule checking.
8. **Final Reports:** Timing, area and power analysis.
9. **GDSII Generation:** Final physical layout exported.

## Physical Design Results

The following metrics were obtained from the final OpenROAD reports.

| Parameter | Result |
|---|---:|
| Technology | Sky130HD |
| Die Area | 6,404 µm² |
| Core Area | 5,885.64 µm² |
| Standard Cell Area | 4,414.23 µm² |
| Final Utilization | 75% |
| Standard Cell Instances | 524 |
| Total Instances | 930 |
| Routed Wirelength | 7,425 |
| Routed Vias | 2,628 |
| Detailed Routing DRC Errors | 0 |

### Timing Analysis

| Parameter | Result |
|---|---:|
| Setup WNS | -1.20488 ns |
| Setup TNS | -54.4492 ns |
| Hold WNS | +0.429847 ns |
| Hold TNS | 0 ns |

### Power Analysis

| Component | Estimated Power |
|---|---:|
| Internal Power | 3.55 mW |
| Switching Power | 1.74 mW |
| Leakage Power | 1.88 nW |
| **Total Power** | **5.29 mW** |

*Power values are EDA estimates and not measurements from a fabricated chip.*

## Implementation Screenshots

### Floorplanning
![Floorplan](gcd-rtl-to-gds-openroad/gcd_flooplan.png)

### Placement
![Placement](gcd-rtl-to-gds-openroad/gcd_detailed_placement.png)

### Clock Tree Synthesis
![Clock Tree Synthesis](gcd-rtl-to-gds-openroad/cts.png)

### Final Physical Layout
![Final Layout](gcd-rtl-to-gds-openroad/gcd_final.png)

## Important Output Files

The implementation generated the following outputs:

- `6_final.gds` – Final GDSII layout.
- `6_final.def` – Final design exchange format.
- `6_final.odb` – Final OpenROAD database.
- `6_final.v` – Final gate-level netlist.
- `6_final.spef` – Extracted parasitic information.
- `6_finish.rpt` – Final timing and power report.
- `6_report.json` – Final implementation metrics.

## Disclaimer

This project uses the GCD benchmark design available in OpenROAD-flow-scripts. The generated GDSII is a design-layout output and does not represent a fabricated silicon chip.

## Acknowledgements

- [OpenROAD](https://github.com/The-OpenROAD-Project/OpenROAD)
- [OpenROAD-flow-scripts](https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts)
- [SkyWater SKY130 PDK](https://github.com/google/skywater-pdk)
