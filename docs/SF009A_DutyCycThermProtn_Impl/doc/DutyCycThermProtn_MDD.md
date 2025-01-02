---
layout: default
title: DutyCycThermProtn_MDD
nav_order: 3
parent: Component Implementation
---
{% raw %}
**Module Design Document**

**For**

**DutyCycThermProtn**

**Dec 14, 2016**

**Prepared By:**

**Shruthi Raghavan**

**Software Engineering**

**Nexteer Automotive,**

**Saginaw, MI, USA**

**  
<u>Change History</u>**

|                                 |                                |             |             |
|------------------------|---------------------|--------------|--------------|
| **Description**                 | **Author**                     | **Version** | **Date**    |
| Initial Version                 | Sarika Natu(KPIT Technologies) | 1.0         | 02-Oct-2015 |
| Updated to version 2.0.0 of FDD | Krishna Anne                   | 2.0         | 07-Apr-2016 |
| Fix for anomaly EA4# 7558       | Krishna Anne                   | 3.0         | 29-Sep-2016 |
| Updated to FDD v3.0.0           | Shruthi Raghavan               | 4.0         | 14-Dec-2016 |

**  
**

<u>Table of Contents</u>

1 DutyCycThermProtn & High-Level Description 5

2 Design details of software module 6

2.1 Graphical representation of DutyCycThermProtn 6

2.2 Data Flow Diagram 7

2.2.1 Component level DFD 7

2.2.2 Function level DFD 7

3 Constant Data Dictionary 8

3.1 Program (fixed) Constants 8

3.1.1 Embedded Constants 8

4 Software Component Implementation 9

4.1 Sub-Module Functions 9

4.1.1 Init: DutyCycThermProtn_Init1 9

4.1.1.1 Design Rationale 9

4.1.1.2 Module Outputs 9

4.1.2 Per: DutyCycThermProtn_Per1 9

4.1.2.1 Design Rationale 9

4.1.2.2 Store Module Inputs to Local copies 9

4.1.2.3 (Processing of function)……… 9

4.1.2.4 Store Local copy of outputs into Module Outputs 9

4.2 Server Runables 9

4.3 Interrupt Functions 9

4.4 Module Internal (Local) Functions 9

4.4.1 Local Function \#1 9

4.4.1.1 Design Rationale 9

4.4.1.2 Processing 10

4.4.2 Local Function \#2 10

4.4.2.1 Design Rationale 10

4.4.2.2 Processing 10

4.4.3 Local Function \#3 10

4.4.3.1 Design Rationale 10

4.4.3.2 Processing 10

4.4.4 Local Function \#4 10

4.4.4.1 Design Rationale 11

4.4.4.2 Processing 11

4.4.5 Local Function \#5 11

4.4.5.1 Design Rationale 11

4.4.5.2 Processing 11

4.4.6 Local Function \#6 11

4.4.6.1 Design Rationale 11

4.4.7 Local Function \#7 11

4.4.7.1 Design Rationale 12

4.4.8 Local Function \#8 12

4.4.8.1 Design Rationale 12

4.4.8.2 Processing 12

4.5 GLOBAL Function/Macro Definitions 12

5 Known Limitations with Design 13

6 UNIT TEST CONSIDERATION 14

Appendix A Abbreviations and Acronyms 15

Appendix B Glossary 16

Appendix C References 17

# DutyCycThermProtn & High-Level Description

The purpose of the Thermal Duty Cycle Protection is to limit and protect
the system from excessive use, based on motor rotational velocity and
system temperature. It also provides protection status information for
use by other functions.

# Design details of software module

## Graphical representation of DutyCycThermProtn

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/SF009A_DutyCycThermProtn_Impl/doc/mediax/media/image2.png"
style="width:5.82923in;height:7.88073in" />

## Data Flow Diagram

See FDD

### Component level DFD

See FDD

### Function level DFD

See FDD

# Constant Data Dictionary

## Program (fixed) Constants

### Embedded Constants

#### Local Constants

Refer .m file

| Constant Name            | Value |
|--------------------------|-------|
|                          |       |
| THERMLOADLIMSIZE_CNT_U08 | 8     |
| MULTFILTERSIZE_CNT_U08   | 6     |

# Software Component Implementation

## Sub-Module Functions

## Init: DutyCycThermProtn_Init1

## Design Rationale

*Refer FDD*

## Module Outputs

*Refer FDD*

## Per: DutyCycThermProtn_Per1

## Design Rationale

DutyCycThermProtn_Per1 function is divided into various functions to
reduce the cyclomatic complexity.

The subsystems ‘Multiplier’ and ‘FilterPercMax’ are clubbed into
‘MultiFilterPercMax’ local function.

## Store Module Inputs to Local copies

*Refer FDD*

## (Processing of function)………

*Refer FDD*

## Store Local copy of outputs into Module Outputs

*Refer FDD*

## Server Runables 

None

## Interrupt Functions

None

## Module Internal (Local) Functions

## Local Function \#1

|                      |                     |         |     |         |
|----------------------|---------------------|---------|-----|---------|
| **Function Name**    | FiltSVReinit        | Type    | Min | Max     |
| **Arguments Passed** | IgnTiOff_Cnt_T_u32  | uint32  | 0   | 1720000 |
|                      | VehTiVld_Cnt_T_Logl | Boolean | 0   | 1       |
| **Return Value**     | None                |         |     |         |

## Design Rationale

Name of local function matches with subsystem name from FDD

## Processing

## Local Function \#2

|                      |                                |         |     |     |
|----------------------|--------------------------------|---------|-----|-----|
| **Function Name**    | TemperatureSelection           | Type    | Min | Max |
| **Arguments Passed** | DiagcStsLimdTPrfmnc_Cnt_T_Logl | boolean | 0   | 1   |
|                      | EcuTFild_DegCgrd_T_f32         | float32 | -50 | 150 |
|                      | MotFetT_DegCgrd_T_f32          | float32 | -50 | 200 |
|                      | MotMagT_DegCgrd_T_f32          | float32 | -50 | 150 |
|                      | MotWidgT_DegCgrd_T_f32         | float32 | -50 | 300 |
|                      | \*Mult12Temp_DegCgrd_T\_ s15p0 | Sint16  | -50 | 200 |
|                      | \*Mult36Temp_DegCgrd_T_s15p0   | Sint16  | -50 | 300 |
| **Return Value**     | SlcTemp_DegCgrd_T_s15p0        | sint16  | -50 | 300 |

## Design Rationale

Name of local function matches with subsystem name from FDD

Note: The outputs of the function are Mult12Temp_DegCgrd_T_s15p0,
Mult36Temp_DegCgrd_T_s15p0 and SlcTemp_DegCgrd_T_f32.

## Processing

None

## Local Function \#3

|                      |                                  |         |     |      |
|----------------------|----------------------------------|---------|-----|------|
| **Function Name**    | TemperatureLimiting              | Type    | Min | Max  |
| **Arguments Passed** | EcuTFild_DegCgrd_T_f32           | float32 | -50 | 150  |
|                      | MotWidgT_DegCgrd_T_f32           | float32 | -50 | 300  |
| **Return Value**     | AbsTempLimitSlew_MotNwtMtr_T_f32 | float32 | 0   | 8.79 |

## Design Rationale

Name of local function matches with subsystem name from FDD

## Processing

None

## Local Function \#4

|                      |                                     |         |       |       |
|---------------|--------------------------------|---------|---------|---------|
| **Function Name**    | MultiFilterPercMax                  | Type    | Min   | Max   |
| **Arguments Passed** | Mult12Temp_DegCgrd_T_s15p0          | sint16  | -50   | 200   |
|                      | Mult36Temp_DegCgrd_T_s15p0          | sint16  | -50   | 300   |
|                      | DutyCycThermProtnDi_Cnt_T_Logl      | boolean | 0     | 1     |
|                      | MotVelCrf_MotRadPerSec_T_f32        | float32 | -1350 | 1350  |
|                      | MotCurrPeakEstimd_AmprSqd_T_f32     | float32 | 0     | 62500 |
|                      | MotCurrPeakEstimdFild_AmprSqd_T_f32 | float32 | 0     | 62500 |
|                      | \*MaxOut_Uls_T_u16p0                | uint16  | 0     | 200   |
| **Return Value**     | ThermLimSlowFilMax_Uls_T_f32        | float32 | 0     | 200   |

## Design Rationale

The subsystems ‘Multiplier’ and ‘FilterPercMax’ are clubbed into
‘MultiFilterPercMax’ local function.

Note: The outputs of the function are MaxOut_Uls_T_u16p0 and
ThermLimSlowFilMax_Uls_T_f32.

## Processing

None

## Local Function \#5

|                      |                                |         |       |      |
|----------------------|--------------------------------|---------|-------|------|
| **Function Name**    | ThermalLoadLimit               | Type    | Min   | Max  |
| **Arguments Passed** | MotVelCrf_MotRadPerSec_T_f32   | float32 | -1350 | 1350 |
|                      | SlcTemp_DegCgrd_T_s15p0        | sint16  | -50   | 300  |
|                      | MaxOut_Uls_T_u16p0             | uint16  | 0     | 200  |
| **Return Value**     | ThermalLoadLmt_MotNwtMtr_T_f32 | float32 | 0     | 8.8  |

## Design Rationale

Name of local function matches with subsystem name from FDD

## Processing

None

## Local Function \#6

|                      |                                |         |     |     |
|----------------------|--------------------------------|---------|-----|-----|
| **Function Name**    | ThermalLimitStatus             | Type    | Min | Max |
|                      |                                |         |     |     |
| **Arguments Passed** | DutyCycThermProtnDi_Cnt_T_Logl | Boolean | 0   | 1   |
|                      |                                |         |     |     |
|                      | MaxOut_Uls_T_u16p0             | uint16  | 0   | 200 |
|                      | ThermMotTqLim_MotNwtMtr_T_f32  | float32 | 0   | 8.8 |
| **Return Value**     | ThermRednFac_Uls_T_f32         | float32 | 0   | 1   |

## Design Rationale

Name of local function matches with subsystem name from FDD.
Initializing ThermRednFac_Uls_T_f32 to 0.0 helps to avoid writing
another statement in the if-conditional (optimized compared to FDD)

## Local Function \#7

|                      |                                    |         |     |      |
|---------------|--------------------------------|---------|---------|---------|
| **Function Name**    | TherrmalLimitScaling               | Type    | Min | Max  |
| **Arguments Passed** | DualEcuFltMtgtnEna_Cnt_T_logl      | Boolean | 0   | 1    |
|                      | IvtrLoaMtgtnEna_Cnt_T_logl         | Boolean | 0   | 1    |
|                      | AbsTempLimitSlew_MotNwtMtr_T_f32   | float32 | 0   | 8.79 |
|                      | DutyCycThermProtnDi_Cnt_T_Logl     | Boolean | 0   | 1    |
|                      | ThermalLoadLmt_MotNwtMtr_T_f32     | float32 | 0   | 8.8  |
|                      | \* ThermLoadDptLim_MotNwtMtr_T_f32 | Float32 | 0   | 8.8  |
|                      | \* ThermTempDptLim_MotNwtMtr_T_f32 | Float32 | 0   | 8.8  |
| **Return Value**     | ThermMotTqLim_MotNwtMtr_T_f32      | float32 | 0   | 8.8  |

## Design Rationale

Name of local function matches with subsystem name from FDD

The if-action subsystem blocks for calculation of LoadDptLim and
TempDptLim are clubbed together and optimized since the condition for
the subsystem execution was same.

## Local Function \#8

|                      |                                   |        |      |      |
|---------------|--------------------------------|---------|---------|---------|
| **Function Name**    | UseInpLowr                        | Type   | Min  | Max  |
| **Arguments Passed** | \*TableX_Cnt_T_s16                | sint16 | FULL | FULL |
|                      | \*TableY_Cnt_T_u16                | uint16 | FULL | FULL |
|                      | Size_Cnt_T_u16                    | uint16 | 1    | 20   |
|                      | Input_Cnt_T_s16                   | sint16 | FULL | FULL |
| **Return Value**     | TableY_Cnt_T_u16\[Idx_Cnt_T_u08\] | uint16 | FULL | FULL |

## Design Rationale

None.

## Processing

None

## GLOBAL Function/Macro Definitions

None

# Known Limitations with Design

None

# UNIT TEST CONSIDERATION

-   Function UseInpLowr to be tested only as called by the component;
    input and output ranges will not be reached.

-   Function UseInpLowr’s TableX must have strictly increasing elements.

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
| 1           | AUTOSAR Specification of Memory Mapping (Link:[AUTOSAR_SWS_MemoryMapping.pdf](http://www.autosar.org/download/R4.0/AUTOSAR_SWS_MemoryMapping.pdf))                    | v1.3.0 R4.0 Rev 2               |
| 2           | MDD Guideline                                                                                                                                                         | EA4 02.00.00                    |
| 3           | [Software Naming Conventions.doc](http://misagweb01.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_fc55f/Software%20Naming%20Conventions%2003x(In%20Work).doc)   | 1.0                             |
| 4           | [Software Design and Coding Standards.doc](http://eroom1.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_1a67a9/Software%20Design%20and%20Coding%20Standards.doc) | 2.1                             |
| 5           | FDD – SF009A_DutyCycThermProtn_Design                                                                                                                                 | See Synergy sub project version |

{% endraw %}