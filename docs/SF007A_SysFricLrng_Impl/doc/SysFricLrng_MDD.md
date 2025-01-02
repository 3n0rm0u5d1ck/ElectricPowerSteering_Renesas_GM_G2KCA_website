---
layout: default
title: SysFricLrng_MDD
nav_order: 2
parent: Component Implementation
---
{% raw %}
**Module Design Document**

**For**

**SysFricLrng**

**Oct** **03, 2016**

**Prepared For:**

**Software Engineering**

**Nexteer Automotive,**

**Saginaw, MI, USA**

**Prepared By:** **Krishna Anne**

**Nexteer Automotive,**

**Saginaw, MI, USA  
<u>Change History</u>**

|                                          |                       |             |                 |
|-------------------------|--------------------|-------------|--------------|
| **Description**                          | **Author**            | **Version** | **Date**        |
| Initial Version                          | Basavaraja Ganeshappa | 1.0         | 24^th^ Mar 2016 |
| Re base lined by pulling 1.3.1           | Basavaraja Ganeshappa | 2.0         | 25^th^ Jul 2016 |
| Implementation of SF007A v2.0.0 & v2.1.0 | Krishna Anne          | 3.0         | 3^rd^ Oct 2016  |

<u>Table of Contents</u>1 Introduction 6

1.1 Purpose 6

1.2 Scope 6

2 SysFricLrng High-Level Description 7

3 Design details of software module 8

3.1 Graphical representation of SysFricLrng 9

3.2 Data Flow Diagram 11

3.2.1 Component level DFD 11

3.2.2 Function level DFD 11

4 Constant Data Dictionary 12

4.1 Program (fixed) Constants 12

4.1.1 Embedded Constants 12

5 Software Component Implementation 13

5.1 Sub-Module Functions 13

5.1.1 Init: SysFricLrngInit1 13

5.1.1.1 Design Rationale 13

5.1.1.2 Module Outputs 13

5.1.2 Per: SysFricLrngPer1 13

5.1.2.1 Design Rationale 13

5.1.2.2 Store Module Inputs to Local copies 13

5.1.2.3 (Processing of function)……… 13

5.1.2.4 Store Local copy of outputs into Module Outputs 13

5.2 Server Runnables 13

5.2.1 Server Runnable Name 13

5.2.1.1 Design Rationale 13

5.2.1.2 (Processing of function)……… 13

5.3 Server Runnables 14

5.3.1 Server Runnable Name 14

5.3.1.1 Design Rationale 14

5.3.1.2 (Processing of function)……… 14

5.3.2 Server Runnable Name 14

5.3.2.1 Design Rationale 14

5.3.2.2 (Processing of function)……… 14

5.3.3 Server Runnable Name 14

5.3.3.1 Design Rationale 14

5.3.3.2 (Processing of function)……… 14

5.3.4 Server Runnable Name 14

5.3.4.1 Design Rationale 14

5.3.4.2 (Processing of function)……… 14

5.3.5 Server Runnable Name 14

5.3.5.1 Design Rationale 15

5.3.5.2 (Processing of function)……… 15

5.4 Interrupt Functions 15

5.4.1 Interrupt Function Name 15

5.4.1.1 Design Rationale 15

5.4.1.2 (Processing of the ISR function)….. 15

5.5 Module Internal (Local) Functions 15

5.5.1 Local Function \#1 15

5.5.1.1 Design Rationale 15

5.5.1.2 Processing 15

5.5.2 Local Function \#2 16

5.5.2.1 Design Rationale 16

5.5.2.2 Processing 16

5.5.3 Local Function \#3 16

5.5.3.1 Design Rationale 16

5.5.3.2 Processing 16

5.5.4 Local Function \#4 16

5.5.4.1 Design Rationale 17

5.5.4.2 Processing 17

5.5.5 Local Function \#5 17

5.5.5.1 Design Rationale 17

5.5.5.2 Processing 17

5.5.6 Local Function \#6 17

5.5.6.1 Design Rationale 18

5.5.6.2 Processing 18

5.5.7 Local Function \#7 18

5.5.7.1 Design Rationale 18

5.5.7.2 Processing 18

5.5.8 Local Function \#8 18

5.5.8.1 Design Rationale 18

5.5.8.2 Processing 18

5.5.8.3 18

5.5.9 Local Function \#9 19

5.5.9.1 Design Rationale 19

5.5.9.2 Processing 19

5.5.10 Local Function \#10 19

5.5.10.1 Design Rationale 19

5.5.10.2 Processing 19

5.5.11 Local Function \#11 19

5.5.11.1 Design Rationale 20

5.5.11.2 Processing 20

5.5.12 Local Function \#12 20

5.5.12.1 Design Rationale 20

5.5.12.2 Processing 20

5.6 GLOBAL Function/Macro Definitions 20

6 Known Limitations with Design 21

7 UNIT TEST CONSIDERATION 22

Appendix A Abbreviations and Acronyms 23

Appendix B Glossary 24

Appendix C References 25

# Introduction

## Purpose

## Scope

# SysFricLrng High-Level Description

*Refer FDD*

# Design details of software module

*Refer FDD*

## Graphical representation of SysFricLrng

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/SF007A_SysFricLrng_Impl/doc/mediax/media/image2.png"
style="width:5.53889in;height:9.22639in" />

## Data Flow Diagram

*Refer FDD*

### Component level DFD

*Refer FDD*

### Function level DFD

*Refer FDD*

# Constant Data Dictionary

## Program (fixed) Constants

### Embedded Constants

#### Local Constants

| Constant Name                      | Resolution | Units   | Value |
|------------------------------------|------------|---------|-------|
| INDEX0_CNT_U08                     | 1          | CNT     | 0U    |
| INDEX1_CNT_U08                     | 1          | CNT     | 1U    |
| INDEX2_CNT_U08                     | 1          | CNT     | 2U    |
| INDEX3_CNT_U08                     | 1          | CNT     | 3U    |
| SYSSATNFRICESTIMDMIN_HWNWMTR_F32   | 1          | HwNwMtr | 0.0F  |
| SYSSATNFRICESTIMDMAX_HWNWMTR_F32 2 | 1          | HwNwMtr | 20.0F |
| SYSFRICESTIMDMIN_HWNWMTR_F32       | 1          | HwNwMtr | 0.0F  |
| SYSFRICESTIMDMAX_HWNWMTR_F32       | 1          | HwNwMtr | 20.0F |
| SYSFRICOFFSMIN_HWNWMTR_F32         | 1          | HwNwMtr | -5.0F |
| SYSFRICOFFSMAX_HWNWMTR_F32         | 1          | HwNwMtr | 5.0F  |

For rest of the constants, please refer Data Dictionary

# Software Component Implementation

The detailed design of the function is provided in the FDD.

## Sub-Module Functions

## Init: SysFricLrngInit1

## Design Rationale

*In MDD, filters are initialized inside the for loop using switch case
but in code filters are initialized one by one without any conditions.*

*In model, filters are initialized twice as it is not possible to use a
variable for the filter initialization in the model. This is redundancy
is not present in the code as variables are used for initializing the
filters.*

## Module Outputs

*Refer FDD*

## Per: SysFricLrngPer1

## Design Rationale

*Refer FDD*

## Store Module Inputs to Local copies

*Refer FDD*

##  (Processing of function)………

*Refer FDD*

## Store Local copy of outputs into Module Outputs

*Refer FDD*

## Server Runnables 

## Server Runnable Name

*ClrFricLrngOperMod*

## Design Rationale

*Refer FDD*

##  (Processing of function)………

*On server invocation call*

## Server Runnables 

## Server Runnable Name

*GetFricLrngData*

## Design Rationale

*Refer FDD*

##  (Processing of function)………

*On server invocation call*

## Server Runnable Name

*GetFricOffsOutpDi*

## Design Rationale

*Refer FDD*

##  (Processing of function)………

*On server invocation call*

## Server Runnable Name

*InitFricLrngTbl*

## Design Rationale

*Refer FDD*

##  (Processing of function)………

*On server invocation call*

## Server Runnable Name

*SetFricLrngDatal*

## Design Rationale

*Refer FDD*

##  (Processing of function)………

*On server invocation call*

## Server Runnable Name

*SetFricOffsOutpDi*

## Design Rationale

*Refer FDD*

##  (Processing of function)………

*On server invocation call*

## Interrupt Functions

*None*

## Interrupt Function Name

*None*

## Design Rationale

*NA*

## (Processing of the ISR function)…..

*NA*

## Module Internal (Local) Functions

## Local Function \#1

|                      |                         |         |         |        |
|----------------------|-------------------------|---------|---------|--------|
| **Function Name**    | FricLearning            | Type    | Min     | Max    |
| **Arguments Passed** | SelHwAg_HwDeg_T_f32     | Float32 | -1440.0 | 1440.0 |
|                      | SelColTq_HwNwtMtr_T_f32 | Float32 | -10     | 10     |
|                      | VehSpdIdx_Cnt_T_u16     | Uint16  | 0       | 3      |
|                      | HwVelDir_Cnt_T_u08      | Uint8   | 0       | 1      |
|                      | LrngEna_Cnt_T_Logl      | Boolean | FALSE   | TRUE   |
| **Return Value**     | NA                      | NA      | NA      | NA     |

## Design Rationale

## Processing

Refer to ‘FricLearning’ subsystem in FDD.

Following per instance data is updated.

|                                                               |
|---------------------------------------------------------------|
| \*Rte_Pim_RawAvrg() (Min:0, Max:20)                           |
| Rte_Pim_SatnAvrgFric()\[VehSpdIdx_Cnt_T_u16\] (Min:0, Max:20) |

Also writes the outputs SysFricEstimd and SysSatnFricEstimd

## Local Function \#2

|                      |                            |         |       |      |
|----------------------|----------------------------|---------|-------|------|
| **Function Name**    | RunningAndCalibrationModes | Type    | Min   | Max  |
| **Arguments Passed** | \*FricOffs_HwNwtMtr_T_f32  | Float32 | -5.0  | +5.0 |
|                      | \*LrngEna_Cnt_T_Logl       | Boolean | FALSE | TRUE |
| **Return Value**     | None                       | NA      | NA    | NA   |

## Design Rationale

## Processing

Following PIMs are updated; refer to ‘RunningAndCalibrationModes’
subsystem in the FDD. FricOffs_HwNwtMtr_T_f32 is the output of this
function

|                                                               |
|---------------------------------------------------------------|
| Rte_Pim_FricLrngData()-\>FricOffs (Min:-5, Max:5)             |
| \*Rte_Pim_RawAvrg() (Min:0, Max:20)                           |
| Rte_Pim_SatnAvrgFric()\[VehSpdIdx_Cnt_T_u16\] (Min:0, Max:20) |

Also updates the input argument, \*FricOffs_HwNwtMtr_T_f32.

## Local Function \#3

|                      |                           |         |       |       |
|----------------------|---------------------------|---------|-------|-------|
| **Function Name**    | RawAvrgCalc               | Type    | Min   | Max   |
| **Arguments Passed** | VehSpdIdx_Cnt_T_u16       | Uint16  | 0     | 5     |
|                      | DeltaIdxOffsDec_Cnt_T_u16 | Uint16  | 0     | 12    |
|                      | DeltaIdxOffsInc_Cnt_T_u16 | Uint16  | 0     | 13    |
|                      | TotalCounter_Cnt_T_u32    | Uint32  | 0     | 65535 |
|                      | LrngEna_Cnt_T_Logl        | Boolean | FALSE | TRUE  |
| **Return Value**     | NA                        | NA      | NA    | NA    |

## Design Rationale

## Processing

Refer to ‘Raw Average Calculation’ subsystem in FDD.

Following per instance data is updated.

|                                                               |
|---------------------------------------------------------------|
| \*Rte_Pim_RawAvrg() (Min:0, Max:20)                           |
| Rte_Pim_SatnAvrgFric()\[VehSpdIdx_Cnt_T_u16\] (Min:0, Max:20) |

## Local Function \#4

|                      |                         |         |       |       |
|----------------------|-------------------------|---------|-------|-------|
| **Function Name**    | PhiCalc                 | Type    | Min   | Max   |
| **Arguments Passed** | SelHwAg_HwDeg_T_f32     | Float32 | -1440 | 1440  |
|                      | Gate_Cnt_T_u16          | Uint16  | 0     | 65535 |
|                      | DeltaIdxOffs_Cnt_T_u16  | Uint16  | 0     | 10    |
|                      | SelColTq_HwNwtMtr_T_f32 | Float32 | -10   | 10    |
| **Return Value**     | NA                      | NA      | NA    | NA    |

## Design Rationale

## Processing

Refer to ‘Raw Average Calculation’ subsystem in FDD.

Following per instance data is updated.

|                                                                                                   |
|------------------------------------------------------------------------|
| Rte_Pim_FricLrngData()-\>Hys\[DeltaIdxOffs_Cnt_T_u16\]\[Gate_Cnt_T_u16 + 1U\] (Min:-127, Max:127) |
| Rte_Pim_FricLrngData()-\>Hys\[DeltaIdxOffs_Cnt_T_u16\]\[Gate_Cnt_T_u16\] (Min:-127, Max:127)      |

## Local Function \#5

|                      |                           |        |     |       |
|----------------------|---------------------------|--------|-----|-------|
| **Function Name**    | RangeCounterManager       | Type   | Min | Max   |
| **Arguments Passed** | DeltaIdxOffs_Cnt_T_u16    | Uint16 | 0   | 10    |
|                      | DeltaIdxOffsDec_Cnt_T_u16 | Uint16 | 0   | 12    |
|                      | DeltaIdxOffsInc_Cnt_T_u16 | Uint16 | 0   | 13    |
|                      | Gate_Cnt_T_u16            | Uint16 | 0   | 65535 |
| **Return Value**     | NA                        | NA     | NA  | NA    |

## Design Rationale

## Processing

Refer to ‘Range counter manager’ subsystem in FDD.

Following per instance data is updated.

|                                                         |
|---------------------------------------------------------|
| \*Rte_Pim\_ RngCntrThdExcdd() (Min:0, Max:1)            |
| Rte_Pim_FricLrngData-\>RngCntr (:,:) (Min:0, Max:65535) |

## Local Function \#6

|                      |                          |         |      |     |
|----------------------|--------------------------|---------|------|-----|
| **Function Name**    | NTCSetReset              | Type    | Min  | Max |
| **Arguments Passed** | MaxRawAvrgFric_Cnt_T_f32 | Float32 | -127 | 254 |
| **Return Value**     | NA                       | NA      | NA   | NA  |

## Design Rationale

## Processing

Refer to ‘NTC_Pass’ and ‘NTC_Fail’ subsystem in FDD

Sets or resets the NTCNR_0X0A2

## Local Function \#7

|                      |              |      |     |     |
|----------------------|--------------|------|-----|-----|
| **Function Name**    | ClearingMode | Type | Min | Max |
| **Arguments Passed** | none         | NA   | NA  | NA  |
| **Return Value**     | none         | NA   | NA  | NA  |

## Design Rationale

## Processing

Refer to ‘Clearing Mode’ subsystem in FDD.

Following per instance data is updated.

|                                     |
|-------------------------------------|
| \*Rte_Pim_FricOffs()(Min:-5, Max:5) |

## Local Function \#8

|                      |                           |      |     |     |
|----------------------|---------------------------|------|-----|-----|
| **Function Name**    | ResettingMode             | Type | Min | Max |
| **Arguments Passed** | \*FricOffs_HwNwtMtr_T_f32 | NA   | NA  | NA  |
| **Return Value**     | None                      | NA   | NA  | NA  |

## Design Rationale

## Processing

## 

Refer to ‘ResettingMode’ subsystem in FDD.

Following per instance data is updated. Also updates the input argument
‘\*FricOffs_HwNwtMtr_T_f32’.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Rte_Pim_FricLrngData()-&gt;RngCntr(;)</td>
</tr>
<tr class="even">
<td>Rte_Pim_AvrgFricLpFil<strong>X</strong>()-&gt;FilSt (X: 1 to 4)</td>
</tr>
<tr class="odd">
<td>Rte_Pim_FricLrngData()-&gt;Hys(;)</td>
</tr>
<tr class="even">
<td>Rte_Pim_FricOffs()(Min:-5, Max:5)</td>
</tr>
<tr class="odd">
<td><p>Rte_Pim_VehBasLineFric()[] (Min:-0, Max:127)</p>
<p>Rte_Pim_RawAvrgFric()[] (Min:--127, Max:254)</p>
<p>Rte_Pim_FilAvrgFric()[] (Min:--10 , Max: 10)</p>
<p>Rte_Pim_SatnAvrgFric()[](Min:--127, Max:254)</p>
<p>Rte_Pim_FricLrngData()-&gt;VehLrndFric[] (0-127)</p></td>
</tr>
</tbody>
</table>

## Local Function \#9

|                      |                       |         |       |      |
|----------------------|-----------------------|---------|-------|------|
| **Function Name**    | HwAngConstraint       | Type    | Min   | Max  |
| **Arguments Passed** | FilHwAg_HwDeg_T_f32   | Float32 | -1440 | 1440 |
|                      | \*HwAgOK_Cnt_T_Logl   | boolean | 0     | 1    |
|                      | \*SelHwAg_HwDeg_T_f32 | Float32 | -1440 | 1440 |
| **Return Value**     | NA                    | NA      | NA    | NA   |

## Design Rationale

## Processing

Refer to ‘HwAngConstraint‘ subsystem in FDD. Updates the input
arguments, \*HwAgOK_Cnt_T_Logl and \*SelHwAg_HwDeg_T_f32

## Local Function \#10

|                      |                         |         |     |     |
|----------------------|-------------------------|---------|-----|-----|
| **Function Name**    | HwVelConstraint         | Type    | Min | Max |
| **Arguments Passed** | HwVel_HwRadPerSec_T_f32 | Float32 | -42 | 42  |
|                      | HwVelOK_Cnt_T_Logl      | Boolean | 0   | 1   |
|                      | HwVelDir_Cnt_T_u08      | Uint8   | 0   | 1   |
| **Return Value**     | NA                      | NA      | NA  | NA  |

## Design Rationale

## Processing

Refer to ‘HwVelConstraint’ subsystem in FDD.

## Local Function \#11

|                      |                       |         |     |     |
|----------------------|-----------------------|---------|-----|-----|
| **Function Name**    | VehSpdConstraint      | Type    | Min | Max |
| **Arguments Passed** | VehSpd_Kph_T_f32      | Float32 | 0   | 511 |
|                      | \*VehSpdOK_Cnt_T_Logl | Boolean | 0   | 1   |
|                      | \*VehSpdIdx_Cnt_T_u16 | Uint16  | 0   | 5   |
| **Return Value**     | None                  | NA      | NA  | NA  |

## Design Rationale

*Code is optimized due to limitation with the model; hence code
completely won’t match the model. There won’t be any impact on the
functionality.*

*In the model as it is not possible to break the for loop until the loop
iterator reaches the configured constant threshold value, index
corresponding to the position in ‘SysFricLrngVehSpd’ which breaches the
conditions mentioned in ‘VehSpdIdxCalcn’ subsystem is calculated by
successively adding the index value after multiplying it with either the
condition true or false based on whether the vehicle speed value
breaches the threshold mentioned in the FDD. In code as it is possible
to exit the for loop as soon as a value in ‘VehSpdIdxCalcn’ breaches
thresholds as mentioned in FDD, no such successive addition of loop
counter is required.*

## Processing

Refer to ‘VehSpdConstraint’ subsystem in FDD.

## Local Function \#12

|                      |                           |         |     |     |
|----------------------|---------------------------|---------|-----|-----|
| **Function Name**    | ColTqconstraint           | Type    | Min | Max |
| **Arguments Passed** | FilColTq_HwNwtMtr_T_f32   | Float32 | -10 | 10  |
|                      | \*SelColTq_HwNwtMtr_T_f32 | Boolean | -10 | 10  |
| **Return Value**     | NA                        | NA      | NA  | NA  |

## Design Rationale

## Processing

Refer to ‘ColTqconstraint’ subsystem in FDD. Updates the
\*SelColTq_HwNwtMtr_T_f32.

## GLOBAL Function/Macro Definitions

NA

# Known Limitations with Design

None

# UNIT TEST CONSIDERATION

In model, one based indexing is used but in code 0 based indexing is
used.

####### Abbreviations and Acronyms

| **Abbreviation or Acronym** | **Description** |
|-----------------------------|-----------------|
|                             |                 |
|                             |                 |

####### Glossary

**Note**: Terms and definitions from the source “Nexteer Automotive”
take precedence over all other definitions of the same term. Terms and
definitions from the source “Nexteer Automotive” are formulated from
multiple sources, including the following:

-   ISO 9000

-   ISO/IEC 12207

-   ISO/IEC 15504

-   Automotive SPICE® Process Reference Model (PRM)

-   Automotive SPICE® Process Assessment Model (PAM)

-   ISO/IEC 15288

-   ISO 26262

-   IEEE Standards

-   SWEBOK

-   PMBOK

-   Existing Nexteer Automotive documentation

| **Term** | **Definition**         | **Source** |
|----------|------------------------|------------|
| MDD      | Module Design Document |            |
| DFD      | Data Flow Diagram      |            |

####### References

| **Ref. \#** | **Title**                                                                                                                                                             | **Version**                     |
|-------|-------------------------------------------------|-----------------|
| 1           | AUTOSAR Specification of Memory Mapping (Link:[AUTOSAR_SWS_MemoryMapping.pdf](http://www.autosar.org/download/R4.0/AUTOSAR_SWS_MemoryMapping.pdf))                    | Process 4.02.01                 |
| 2           | MDD Guideline                                                                                                                                                         | Process 4.02.01                 |
| 3           | [Software Naming Conventions.doc](http://misagweb01.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_fc55f/Software%20Naming%20Conventions%2003x(In%20Work).doc)   | 2.0                             |
| 4           | [Software Design and Coding Standards.doc](http://eroom1.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_1a67a9/Software%20Design%20and%20Coding%20Standards.doc) | 2.1                             |
| 5           | FDD- SF007A_SysFricLrng_Design                                                                                                                                        | See Synergy sub project version |

{% endraw %}