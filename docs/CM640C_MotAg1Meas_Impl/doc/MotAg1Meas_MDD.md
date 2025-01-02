---
layout: default
title: MotAg1Meas_MDD
nav_order: 2
parent: Component Implementation
---
{% raw %}
**Motor Angle 1 Measurement**

**Module Design Document**

**VERSION:** **2.0**

**DATE:** **21-Dec-2016**

**Revision History**

|             |                           |                  |             |             |
|------|----------------------|----------------------|----------|-------------|
| **Sl. No.** | **Description**           | **Author**       | **Version** | **Date**    |
| 1           | Initial Version           | Avinash James    | 1.0         | 02-Nov-2016 |
| 2           | Updated acc to FDD v1.4.0 | Shruthi Raghavan | 2.0         | 21-Dec-2016 |

Table of Contents

[1 Abbrevations And Acronyms 5](#abbrevations-and-acronyms)

[2 References 6](#references)

[3 MotAg1Meas High-Level Description
7](#motag1meas-high-level-description)

[3.1 Design details of software module
7](#design-details-of-software-module)

[3.2 Graphical representation of CDD_MotAg1Meas
7](#graphical-representation-of-cdd_motag1meas)

[3.3 Data Flow Diagram 7](#data-flow-diagram)

[3.3.1 Module level DFD 7](#module-level-dfd)

[3.3.2 Sub-Module level DFD 7](#sub-module-level-dfd)

[3.4 COMPONENT FLOW DIAGRAM 7](#component-flow-diagram)

[4 Variable Data Dictionary 8](#variable-data-dictionary)

[4.1 User defined typedef definition/declaration
8](#user-defined-typedef-definitiondeclaration)

[4.2 Variable definition for enumerated types
8](#variable-definition-for-enumerated-types)

[5 Constant Data Dictionary 9](#constant-data-dictionary)

[5.1 Program(fixed) Constants 9](#programfixed-constants)

[5.1.1 Embedded Constants 9](#embedded-constants)

[5.1.1.1 Local 9](#local)

[5.1.1.2 Global 9](#global)

[5.1.2 Module specific Lookup Tables Constants
9](#module-specific-lookup-tables-constants)

[6 Software Module Implementation 10](#software-module-implementation)

[6.1 Sub-Module Functions 10](#sub-module-functions)

[6.1.1 Motor Control Periodic: MotAg1MeasPer1
10](#motor-control-periodic-motag1measper1)

[6.1.1.1 Design Rationale 10](#design-rationale)

[6.2 Initialization Functions 10](#initialization-functions)

[6.2.1 Init: MotAg1MeasInit1 10](#init-motag1measinit1)

[6.2.1.1 Design Rationale 10](#design-rationale-1)

[6.2.1.2 Module Outputs 10](#module-outputs)

[6.2.1.3 Module Internal 10](#module-internal)

[6.3 PERIODIC FUNCTIONS 10](#periodic-functions)

[6.3.1 Per: MotAg1MeasPer2 10](#per-motag1measper2)

[6.3.1.1 Design Rationale 10](#design-rationale-2)

[6.3.1.2 Store Module Inputs to Local copies
10](#store-module-inputs-to-local-copies)

[6.3.1.3 (Processing of function)……… 10](#processing-of-function)

[6.3.1.4 Store Local copy of outputs into Module Outputs
10](#store-local-copy-of-outputs-into-module-outputs)

[6.3.2 Per: MotAg1MeasPer3 11](#per-motag1measper3)

[6.3.2.1 Design Rationale 11](#design-rationale-3)

[6.3.2.2 Store Module Inputs to Local copies
11](#store-module-inputs-to-local-copies-1)

[6.3.2.3 (Processing of function)……… 11](#processing-of-function-1)

[6.3.2.4 Store Local copy of outputs into Module Outputs
11](#store-local-copy-of-outputs-into-module-outputs-1)

[6.4 Interrupt Functions 11](#interrupt-functions)

[6.5 Server runnables 11](#server-runnables)

[6.5.1.1 MotAg1CoeffTblRead_Oper 11](#motag1coefftblread_oper)

[6.5.1.1.1 Design Rationale 11](#design-rationale-4)

[6.5.1.1.2 Store Module Inputs to Local copies
11](#store-module-inputs-to-local-copies-2)

[6.5.1.1.3 (Processing of function)……… 11](#processing-of-function-2)

[6.5.1.1.4 Store Local copy of outputs into Module Outputs
11](#store-local-copy-of-outputs-into-module-outputs-2)

[6.5.1.2 MotAg1CoeffTblWr_Oper 11](#motag1coefftblwr_oper)

[6.5.1.2.1 Design Rationale 11](#design-rationale-5)

[6.5.1.2.2 Store Module Inputs to Local copies
11](#store-module-inputs-to-local-copies-3)

[6.5.1.2.3 (Processing of function)……… 11](#processing-of-function-3)

[6.5.1.2.4 Store Local copy of outputs into Module Outputs
12](#store-local-copy-of-outputs-into-module-outputs-3)

[6.6 Local Function/Macro Definitions
12](#local-functionmacro-definitions)

[6.6.1 Local Function \#1 12](#local-function-1)

[6.6.1.1 Design Rationale 12](#design-rationale-6)

[6.6.2 Local Function \#2 12](#local-function-2)

[6.6.2.1 Design Rationale 12](#design-rationale-7)

[6.6.3 Local Function \#3 12](#__RefHeading___Toc470081222)

[6.6.3.1 Design Rationale 12](#__RefHeading___Toc470081223)

[6.7 GLObAL Function/Macro Definitions
12](#global-functionmacro-definitions)

[6.8 TRANSIENT FUNCTIONS 12](#transient-functions)

[7 Known Limitations With Design 13](#known-limitations-with-design)

[8 UNIT TEST CONSIDERATION 14](#unit-test-consideration)

[9 Appendix 15](#appendix)

# Abbrevations And Acronyms

|              |                            |
|--------------|----------------------------|
| Abbreviation | Description                |
| DFD          | Design functional diagram  |
| MDD          | Module design Document     |
| FDD          | Functional Design Document |

# References

This section lists the title & version of all the documents that are
referred for development of this document

|         |                               |                                   |
|----------|----------------------------------------------|-----------------|
| Sr. No. | Title                         | Version                           |
| 1       | MDD Guidelines                | Software Process Release 04.20.01 |
| 2       | Software Naming Conventions   | Software Process Release 04.20.01 |
| 3       | Design and Coding standards   | Software Process Release 04.20.01 |
| 4       | FDD: CM640C_MotAg1Meas_Design | See Synergy subproject version    |

# MotAg1Meas High-Level Description

The CDD_MotAg1Meas component is the complex driver for the motor angle 0
measurement subsystem. This function initializes the registers for CSIH1
SPI channel for communicating with the motor angle 0 measurement sensor
board. The SPI transmission is triggered periodically by the component.
This function receives the RAW sensor data at 62.5uS rate. The component
contains two source files, both described in this MDD: CDD_MotAg1Meas.c
contains the RTE runnables and services; CDD_MotAg1Meas_MotCtrl.c
contains the motor control runnable.

## Design details of software module

*See FDD.*

## Graphical representation of CDD_MotAg1Meas

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CM640C_MotAg1Meas_Impl/doc/mediax/media/image1.png"
style="width:4.57153in;height:3.11736in" />

## Data Flow Diagram

*See FDD.*

## Module level DFD

*See FDD.*

## Sub-Module level DFD

*See FDD.*

## COMPONENT FLOW DIAGRAM

*See FDD.*

# Variable Data Dictionary

## User defined typedef definition/declaration 

*NA*

<table>
<colgroup>
<col style="width: 34%" />
<col style="width: 31%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Typedef Name</td>
<td>Element Name</td>
<td>User Defined Type</td>
<td><p>Legal Range</p>
<p>(min)</p></td>
<td><p>Legal Range</p>
<p>(max)</p></td>
</tr>
<tr class="even">
<td>NA</td>
<td>NA</td>
<td>NA</td>
<td>NA</td>
<td>NA</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

## Variable definition for enumerated types

|           |              |       |
|-----------|--------------|-------|
| Enum Name | Element Name | Value |
| NA        | NA           | NA    |

# Constant Data Dictionary

## Program(fixed) Constants

## Embedded Constants

## Local

|                                                          |            |       |                                                             |
|------------------------|-------------|---------|---------------------------|
| Constant Name                                            | Resolution | Units | Value                                                       |
| MAX16BIT_CNT_U32                                         | 1          | Cnt   | 65535U                                                      |
| PimMotAg1CoeffTbl                                        |            |       | ( \*(Ary1D_f32_26 \*) (Rte_Pim_MotAg1CoeffTbl()) )          |
| dPimMotAg1RawReg                                         |            |       | ( \*(Ary1D_u32_10 \*) (Rte_Pim_dMotAg1MeasMotAg1RawReg()) ) |
| **Also see see FDD – CM640C_MotAg1Meas_DataDict.m file** |            |       |                                                             |

## Global

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Constant Name</td>
</tr>
<tr class="even">
<td><blockquote>
<p>See FDD – CM640C_MotAg1Meas_DataDict.m file</p>
</blockquote></td>
</tr>
<tr class="odd">
<td></td>
</tr>
<tr class="even">
<td></td>
</tr>
</tbody>
</table>

## Module specific Lookup Tables Constants

|               |            |       |                  |
|---------------|------------|-------|------------------|
| Constant Name | Resolution | Value | Software Segment |
| NA            | NA         | NA    | NA               |

# Software Module Implementation

## Sub-Module Functions

## Motor Control Periodic: MotAg1MeasPer1

See FDD MotAg1MeasPer1 model block.

## Design Rationale

> For run time efficiency in the motor control loop the **Offset** &
> **Compensate MechMtrPos** block is implemented in a optimized way in
> the code by letting a uint16 variable be overflown.

## Initialization Functions

## Init: MotAg1MeasInit1

## Design Rationale

All register initialization that is allowed at the register level (see
Register/Field coloumn of the
CM640C_MotAg1Meas_RegisterConfiguration.xlsm spreadsheet in the FDD) is
done at the register level to save execution time as compared to the
read/modify/writes that would be needed to initialize at the field
level. Field level initialization done only where required by the
spreadsheet.

## Module Outputs

See FDD: MotAg1MeasInit1 model block.

## Module Internal 

See FDD: MotAg1MeasInit1 model block for Per Instance Memory.

## PERIODIC FUNCTIONS 

##  Per: MotAg1MeasPer2

## Design Rationale

None

## Store Module Inputs to Local copies

See FDD: MotAg1MeasPer2 model block.

## (Processing of function)………

See FDD: MotAg1MeasPer2 model block.

## Store Local copy of outputs into Module Outputs

See FDD: MotAg1MeasPer2 model block

## Per: MotAg1MeasPer3

## Design Rationale

None

## Store Module Inputs to Local copies

See FDD: MotAg1MeasPer3 model block.

## (Processing of function)………

See FDD: MotAg1MeasPer3 model block.

## Store Local copy of outputs into Module Outputs

See FDD: MotAg1MeasPer3 model block

## Interrupt Functions

None

## Server runnables

## MotAg1CoeffTblRead_Oper

## Design Rationale

*None*

## Store Module Inputs to Local copies

*None*

## (Processing of function)………

*See* MotAg1CoeffTblRead *block in the FDD*

## Store Local copy of outputs into Module Outputs

*See* MotAg1CoeffTblRead *block in the FDD*

## MotAg1CoeffTblWr_Oper

## Design Rationale

*None*

## Store Module Inputs to Local copies

*See* MotAg1CoeffTblWr *in the FDD*

## (Processing of function)………

*See* MotAg1CoeffTblWr *in the FDD*

## Store Local copy of outputs into Module Outputs

*See* MotAg1CoeffTblWr *in the FDD*

## Local Function/Macro Definitions

##  Local Function \#1

|                      |              |      |     |     |
|----------------------|--------------|------|-----|-----|
| **Function Name**    | CalcCorrnTbl | Type | Min | Max |
| **Arguments Passed** | None         | N/A  | N/A | N/A |
| **Return Value**     | N/A          | N/A  | N/A | N/A |

## Design Rationale

See “Calculate Correction Table” block in the Simulink model of the
design.

## Local Function \#2

|                      |                          |         |       |         |
|----------------------|--------------------------|---------|-------|---------|
| **Function Name**    | CalcNtcPrm               | Type    | Min   | Max     |
| **Arguments Passed** | MotAg1StatReg_Cnt_T_u32, | Uint32  | 0     | 2\^32-1 |
|                      | MotAg1SyncErr_Cnt_T_lgc  | Boolean | False | True    |
| **Return Value**     | N/A                      | N/A     | N/A   | N/A     |

## Design Rationale

See “SetParamByte” block in the Simulink model of the design.

## Local Function \#3

|                      |                              |        |     |                |
|--------------|-----------------------------|----------|----------|-----------|
| **Function Name**    | GetMechMtrPos                | Type   | Min | Max            |
| **Arguments Passed** | MotAg1SpiMecl_MotRev_T_u0p16 | u0p16  | 0   | 65535 (counts) |
| **Return Value**     | MechMtrPosOut_MotRev_T_s32   | sint32 | 0   | 65535          |

## Design Rationale

Static Path of Per2 function was near the limit and the if condition was
not possible to add to the main body. So the newly added logic to
subtract a cal from the MotAg1SpiMecl and then check it for negative
values and adjust accordingly was written in this new function

## GLObAL Function/Macro Definitions

None

## TRANSIENT FUNCTIONS 

None

# Known Limitations With Design

> None.

# UNIT TEST CONSIDERATION

Following variables are used as rolling counters, so the overflow of
these variables is intentional.

Rte_Pim_MotAg1PrevSpiErrFltCntr

Rte_Pim_MotAg1PrevRollgCntr

There is an unreachable code in the SinCos_f32() function, because the
input of this function is always positive. This is ok as the
SinCos_f32() is a library function.

For run time efficiency in the motor control loop the **Offset** &
**Compensate MechMtrPos** block is implemented in a optimized way in the
code by letting a uint16 variable be overflown.

# Appendix

*NA*

{% endraw %}