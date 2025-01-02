---
layout: default
title: MotCurrRegVltgLimr_MDD
nav_order: 2
parent: Component Implementation
---
{% raw %}
**Module Design Document**

**For**

**‘MotCurrRegVltgLimr’**

**VERSION:** **3.0**

**DATE: 7-Nov-2016**

**Prepared By:**

**Matthew Leser,**

**Nexteer Automotive,**

**Saginaw, MI, USA**

**  
Location:** The official version of this document is stored in the
Nexteer Configuration Management System.

**Revision History**

|             |                                                                       |                    |             |             |
|------|----------------------|----------------------|----------|-------------|
| **Sl. No.** | **Description**                                                       | **Author**         | **Version** | **Date**    |
| 1           | Initial Version                                                       | Selva Sengottaiyan | 1.0         | 26-May-2015 |
| 2           | Updated graphical representation and added local function information | Nick Saxton        | 2.0         | 13-Apr-2016 |
| 3           | Updated for FDD v2.1.0                                                | Matthew Leser      | 3.0         | 7-Nov-2016  |
|             |                                                                       |                    |             |             |
|             |                                                                       |                    |             |             |

**<u>  
Table of Contents</u>**

[1 Abbrevations And Acronyms [5](#abbrevations-and-acronyms)](\l)

[2 References [6](#references)](\l)

[3 High-Level Description [7](#high-level-description)](\l)

[4 Design details of software module
[8](#design-details-of-software-module)](\l)

[4.1 Graphical representation [8](#graphical-representation)](\l)

[4.2 Data Flow Diagram [8](#data-flow-diagram)](\l)

[4.2.1 Module level DFD [8](#module-level-dfd)](\l)

[4.2.2 Sub-Module level DFD [8](#sub-module-level-dfd)](\l)

[4.3 COMPONENT FLOW DIAGRAM [8](#component-flow-diagram)](\l)

[5 Variable Data Dictionary [9](#variable-data-dictionary)](\l)

[5.1 User defined typedef definition/declaration
[9](#user-defined-typedef-definitiondeclaration)](\l)

[5.2 Variable definition for enumerated types
[9](#variable-definition-for-enumerated-types)](\l)

[6 Constant Data Dictionary [10](#constant-data-dictionary)](\l)

[6.1 Program(fixed) Constants [10](#programfixed-constants)](\l)

[6.1.1 Embedded Constants [10](#embedded-constants)](\l)

[6.1.1.1 Local [10](#local)](\l)

[6.1.1.2 Global [10](#global)](\l)

[6.1.2 Module specific Lookup Tables Constants
[10](#module-specific-lookup-tables-constants)](\l)

[7 Software Module Implementation
[11](#software-module-implementation)](\l)

[7.1 Sub-Module Functions [11](#sub-module-functions)](\l)

[7.1.1 Initialization Functions [11](#initialization-functions)](\l)

[7.1.1.1 INIT: MotCurrRegVltgLimrInit1
[11](#init-motcurrregvltglimrinit1)](\l)

[7.1.1.1.1 Design Rationale [11](#design-rationale)](\l)

[7.1.1.1.2 Module Outputs [11](#module-outputs)](\l)

[7.1.1.1.3 Module Internal [11](#module-internal)](\l)

[7.1.2 PERIODIC FUNCTIONS [11](#periodic-functions)](\l)

[7.1.2.1 INIT: MotCurrRegVltgLimrPER1
[11](#init-motcurrregvltglimrper1)](\l)

[7.1.2.1.1 Design Rationale [11](#design-rationale-1)](\l)

[7.1.2.1.2 Module Outputs [11](#module-outputs-1)](\l)

[7.1.3 Interrupt Functions [11](#interrupt-functions)](\l)

[7.1.4 Server runnables [12](#server-runnables)](\l)

[7.1.4.1.1 Store Local copy of outputs into Module Outputs
[12](#store-local-copy-of-outputs-into-module-outputs)](\l)

[7.1.5 Local Function/Macro Definitions
[12](#local-functionmacro-definitions)](\l)

[7.1.5.1.1 Local function \#1 [12](#local-function-1)](\l)

[7.1.5.1.2 Local function \#2 [12](#local-function-2)](\l)

[7.1.5.1.3 Local function \#3 [12](#local-function-3)](\l)

[7.1.6 GLObAL Function/Macro Definitions
[12](#global-functionmacro-definitions)](\l)

[7.1.7 Tranisition FUNCTIONS [13](#tranisition-functions)](\l)

[8 Known Limitations With Design
[14](#known-limitations-with-design)](\l)

[9 UNIT TEST CONSIDERATION [15](#unit-test-consideration)](\l)

[10 Appendix [16](#appendix)](\l)

# Abbrevations And Acronyms

| Abbreviation | Description                |
|--------------|----------------------------|
| DFD          | Design functional diagram  |
| MDD          | Module design Document     |
| FDD          | Functional Design Document |

# References

This section lists the title & version of all the documents that are
referred for development of this document

| Sr. No. | Title                                  | Version                         |
|----------|----------------------------------------------|-----------------|
| 1       | MDD Guidelines                         | Process 4.02.01                 |
| 2       | Software Naming Conventions            | Process 4.02.01                 |
| 3       | Software Design and Coding standards   | Process 4.02.01                 |
| 4       | FDD – SF105A_MotCurrRegVltgLimr_Design | See Synergy sub project version |
|         |                                        |                                 |

# High-Level Description

*None*

# Design details of software module

## Graphical representation

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/SF105A_MotCurrRegVltgLimr_Impl/doc/mediax/media/image2.png"
style="width:2.3684in;height:4.28728in" />

## Data Flow Diagram

*Refer FDD*

## Module level DFD

*Refer FDD*

## Sub-Module level DFD

*Refer FDD*

## COMPONENT FLOW DIAGRAM

*Refer FDD*

# Variable Data Dictionary

## User defined typedef definition/declaration 

*\<This section documents any user types uniquely used for the
module.\>*

<table>
<colgroup>
<col style="width: 34%" />
<col style="width: 31%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th>Typedef Name</th>
<th>Element Name</th>
<th>User Defined Type</th>
<th><p>Legal Range</p>
<p>(min)</p></th>
<th><p>Legal Range</p>
<p>(max)</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>None</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

## Variable definition for enumerated types

| Enum Name | Element Name | Value |
|-----------|--------------|-------|
| None      |              |       |

# Constant Data Dictionary

## Program(fixed) Constants

## Embedded Constants

## Local 

| Constant Name        | Resolution             | Units | Value |
|----------------------|------------------------|-------|-------|
| MODIDXHILIM_VOLT_F32 | Single precision float | Volt  | 1     |
| MODIDXLOLIM_VOLT_F32 | Single precision float | Volt  | 0     |

##  [section]

## Global

| Constant Name |
|---------------|
|               |

## Module specific Lookup Tables Constants

*None*

# Software Module Implementation

## Sub-Module Functions 

## Initialization Functions

*MotCurrRegVltgLimrInit1*

## INIT: MotCurrRegVltgLimrInit1

## Design Rationale

*Design follows implemenetation in FDD.*

## Module Outputs

*Refer ‘MotCurrRegVltgLimrInit’ block in FDD*

## Module Internal 

None

## PERIODIC FUNCTIONS 

## INIT: MotCurrRegVltgLimrPER1

## Design Rationale

*Design follows implemenetation in FDD.*

## Module Outputs

*Design follows implemenetation in FDD.*

## Interrupt Functions

*None*

##  Server runnables

*None*

## Store Local copy of outputs into Module Outputs

*None*

## Local Function/Macro Definitions

##  Local function \#1

|                      |                                                   |         |          |               |
|-------------|--------------------------------|--------|---------|-----------|
| **Function Name**    | KpKiCtrl                                          | Type    | Min      | Max           |
| **Arguments Passed** | MotPropGain_Ohm_T_f32                             | Float32 | 0        | 2.25          |
|                      | MotIntglGain_Ohm_T_f32                            | Float32 | 0        | 3.6           |
|                      | SysSt_Cnt_T_enum                                  | Enum    | SYSST_DI | SYSST_WRMININ |
|                      | CmdErr_Ampr_T_f32                                 | Float32 | -200     | 400           |
|                      | \*MotVltgIntglCmdPrev_Volt_T_f32                  | Float32 | -1000    | 1000          |
|                      | \*MotCurrRegVltgLimrMotVltgPropCmd_Volt_T_f32     | Float32 | -26.5    | 26.5          |
|                      | \*MotCurrRegVltgLimrMotVltgIntglPreLim_Volt_T_f32 | Float32 | -26.5    | 26.5          |
|                      | MotVltgIntglLoLim_Volt_T_f32                      | Float32 | -31      | 0             |
|                      | MotVltgIntglHiLim_Volt_T_f32                      | Float32 | 0        | 31            |
|                      | \*MotVltgPropCmd_Volt_T_f32                       | Float32 | -26.5    | 26.5          |
|                      | \*MotVltgIntglCmd_Volt_T_f32                      | Float32 | 6        | 26.5          |

\* MotVltgPropCmd_Volt_T_f32 and \* MotVltgIntglCmd_Volt_T_f32 are
outputs of this function.

## Local function \#2 

|                      |                           |         |      |     |
|----------------------|---------------------------|---------|------|-----|
| **Function Name**    | ErrorCalcQax              | Type    | Min  | Max |
| **Arguments Passed** | QaxCurrCmd_Ampr_T_f32     | Float32 | -200 | 200 |
|                      | QaxRplCmd_Ampr_T_f32      | Float32 | -29  | 29  |
|                      | QaxCoggCmd_Ampr_T_f32     | Float32 | -6   | 6   |
|                      | QaxCurrModif_Ampr_T_f32   | Float32 | -200 | 200 |
|                      | \* QaxCmdFinal_Ampr_T_f32 | Float32 | -200 | 200 |
| **Returns**          | CmdErrQax_Ampr_T_f32      | Float32 | -200 | 400 |

\*QaxCmdFinal_Ampr_T_f32 is also an output of this function.

## Local function \#3 

|                      |                                          |         |       |      |
|---------------|--------------------------------|---------|---------|---------|
| **Function Name**    | LoaScaFac                                | Type    | Min   | Max  |
| **Arguments Passed** | CurrLoaMtgtnEn_Cnt_T_logl                | Boolean | FALSE | TRUE |
|                      | IvtrLoaMtgtnEn_Cnt_T_logl                | Boolean | FALSE | TRUE |
|                      | MotCtrlDualEcuMotCtrlMtgtnEna_Cnt_T_logl | Boolean | FALSE | TRUE |
|                      | \*CurrLoaScaFac_Uls_T_f32                | Float32 | 0     | 1    |
|                      | \*IvtrLoaScaFac_Uls_T_f32                | Float32 | 0     | 1    |
|                      | \*DualEcuScaFac_Uls_T_f32                | Float32 | 0     | 1    |

\*CurrLoaScaFac_Uls_T_f32, \*IvtrLoaScaFac_Uls_T_f32, and
\*DualEcuScaFac_Uls_T_f32 are outputs of this function.

## Local function \#4

|                      |                                            |         |         |         |
|---------------|--------------------------------|---------|---------|---------|
| **Function Name**    | MotCurr_Pred                               | Type    | Min     | Max     |
| **Arguments Passed** | MotInduQaxEstimdIvs_IvsHenry_T_f32         | Float32 | 2240    | 33334   |
|                      | MotREstimd_Ohm_T_f32                       | Float32 | 0.005   | 0.12565 |
|                      | CurrQax_Ampr_T_f32                         | Float32 | -200    | 200     |
|                      | MotVltgQaxPrev_Volt_T_f32                  | Float32 | -26.5   | 26.5    |
|                      | CurrDax_Ampr_T_f32                         | Float32 | -200    | 200     |
|                      | MotVltgDaxPrev_Volt_T_f32                  | Float32 | -26.5   | 26.5    |
|                      | MotBackEmfVltg_Volt_T_f32                  | Float32 | -101.25 | 101.25  |
|                      | ReacncQax_Ohm_T_f32                        | Float32 | -0.5    | 0.5     |
|                      | ReacncDax_Ohm_T_f32                        | Float32 | -0.5    | 0.5     |
|                      | MotInduDaxEstimdIvs_IvsHenry_T_f32         | Float32 | 2240    | 33334   |
|                      | MotCurrRegVltgLimrMotCurrPredEna_Cnt_T_f32 | Boolean | FALSE   | TRUE    |
|                      | MotCtrlCurrPredTi_NanoSec_T_f32            | Float32 | 0       | 125000  |
|                      | \*MotCurrQaxPred_Ampr_T_f32                | Float32 | -200    | 200     |
|                      | \*MotCurrDaxPred_Ampr_T_f32                | Float32 | -200    | 200     |

\*MotCurrQaxPred_Ampr_T_f32 and \*MotCurrDaxPred_Ampr_T_f32 are outputs
of this function.

## GLObAL Function/Macro Definitions

None

## Tranisition FUNCTIONS 

None

# Known Limitations With Design

None

# UNIT TEST CONSIDERATION

None

# Appendix

*None*

{% endraw %}