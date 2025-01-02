---
layout: default
title: GmVehPwrMod_MDD
nav_order: 2
parent: Component Implementation
---
{% raw %}
**Module Design Document**

**For**

**GmVehPwrMod**

**April 15, 2016**

**Prepared For:**

**Software Engineering**

**Nexteer Automotive,**

**Saginaw, MI, USA**

**Prepared By:**

**Nick Saxton,**

**Nexteer Automotive,**

**Saginaw, MI, USA  
<u>Change History</u>**

|                                                              |            |             |             |
|------------------|----------------|----------|----------------------------|
| **Description**                                              | **Author** | **Version** | **Date**    |
| Initial Version                                              | N. Saxton  | 1.0         | 28-Sep-2015 |
| Updated with new graphical representation and local function | N. Saxton  | 2.0         | 01-Oct-2015 |
| New graphical representation                                 | N. Saxton  | 3.0         | 12-Nov-2015 |
| Changes to local constants and functions                     | N. Saxton  | 4.0         | 15-Apr-2016 |

<u>Table of Contents</u>

[1 GmVehPwrMod High-Level Description
[4](#gmvehpwrmod-high-level-description)](#gmvehpwrmod-high-level-description)

[2 Design details of software module
[5](#design-details-of-software-module)](#design-details-of-software-module)

[2.1 Graphical representation of GmVehPwrMod
[5](#graphical-representation-of-gmvehpwrmod)](#graphical-representation-of-gmvehpwrmod)

[2.2 Data Flow Diagram [5](#data-flow-diagram)](#data-flow-diagram)

[2.2.1 Component level DFD
[5](#component-level-dfd)](#component-level-dfd)

[2.2.2 Function level DFD [5](#function-level-dfd)](#function-level-dfd)

[3 Constant Data Dictionary
[6](#constant-data-dictionary)](#constant-data-dictionary)

[3.1 Program (fixed) Constants
[6](#program-fixed-constants)](#program-fixed-constants)

[3.1.1 Embedded Constants [6](#embedded-constants)](#embedded-constants)

[4 Software Component Implementation
[7](#software-component-implementation)](#software-component-implementation)

[4.1 Sub-Module Functions
[7](#sub-module-functions)](#sub-module-functions)

[4.1.1 Per: GmVehPwrModPer1
[7](#per-gmvehpwrmodper1)](#per-gmvehpwrmodper1)

[4.1.1.1 Design Rationale [7](#design-rationale)](#design-rationale)

[4.1.1.2 Store Module Inputs to Local copies
[7](#store-module-inputs-to-local-copies)](#store-module-inputs-to-local-copies)

[4.1.1.3 (Processing of function)………
[7](#processing-of-function)](#processing-of-function)

[4.1.1.4 Store Local copy of outputs into Module Outputs
[7](#store-local-copy-of-outputs-into-module-outputs)](#store-local-copy-of-outputs-into-module-outputs)

[4.2 Server Runables [7](#server-runables)](#server-runables)

[4.3 Interrupt Functions
[7](#interrupt-functions)](#interrupt-functions)

[4.4 Module Internal (Local) Functions
[7](#module-internal-local-functions)](#module-internal-local-functions)

[4.4.1 Local Function \#1 [7](#local-function-1)](#local-function-1)

[4.4.1.1 Design Rationale [7](#design-rationale-1)](#design-rationale-1)

[4.4.1.2 Processing [7](#processing)](#processing)

[4.4.2 Local Function \#2 [8](#local-function-2)](#local-function-2)

[4.4.2.1 Design Rationale [8](#design-rationale-2)](#design-rationale-2)

[4.4.2.2 Processing [8](#processing-1)](#processing-1)

[4.5 GLOBAL Function/Macro Definitions
[8](#global-functionmacro-definitions)](#global-functionmacro-definitions)

[5 Known Limitations with Design
[9](#known-limitations-with-design)](#known-limitations-with-design)

[6 UNIT TEST CONSIDERATION
[10](#unit-test-consideration)](#unit-test-consideration)

[Appendix A Abbreviations and Acronyms
[11](#abbreviations-and-acronyms)](#abbreviations-and-acronyms)

[Appendix B Glossary [12](#glossary)](#glossary)

[Appendix C References [13](#references)](#references)

# GmVehPwrMod High-Level Description

*This GM specific function runs periodically to determine whether to
enable assist (if not previously enabled) or to disable assist based on
the inputs provided to the function.*

# Design details of software module

## Graphical representation of GmVehPwrMod

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CF017A_GMVehPwrMod_Impl/doc/mediax/media/image1.PNG"
style="width:4.22537in;height:2.92525in" />

## Data Flow Diagram

Refer FDD

### Component level DFD

### Function level DFD

# Constant Data Dictionary

## Program (fixed) Constants

### Embedded Constants

#### Local Constants

| Constant Name                     | Units | Value |
|-----------------------------------|-------|-------|
| LOOKUPTBLSIZE_CNT_U16             | CNT   | 512   |
|                                   |       |       |
| Refer .m file for other constants |       |       |

# Software Component Implementation

## Sub-Module Functions

The sub-module functions are grouped based on similar functionality that
needs to be executed in a given “State” of the system (refer States and
Modes). For a given module, the MDD will identify the type and number of
sub-modules required. The sub-module types are described below.

## Per: GmVehPwrModPer1

## Design Rationale

Refer FDD

## Store Module Inputs to Local copies

##  (Processing of function)………

## Store Local copy of outputs into Module Outputs

## Server Runables 

None

## Interrupt Functions

None

## Module Internal (Local) Functions

## Local Function \#1

|     |     |     |     |     |
|-----|-----|-----|-----|-----|
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |

|                      |                              |         |       |      |
|----------------------|------------------------------|---------|-------|------|
|  **Function Name**   | GetTblIdx                    | Type    | Min   | Max  |
| **Arguments Passed** | GetGpioMcuEna_Cnt_T_logl     | Boolean | FALSE | TRUE |
|                      | SysPwrModRun_Cnt_T_logl      | Boolean | FALSE | TRUE |
|                      | EngRunActv_Cnt_T_logl        | Boolean | FALSE | TRUE |
|                      | VehSpdAssiKeepMin_Cnt_T_logl | Boolean | FALSE | TRUE |
|                      | Msg0C9Miss_Cnt_T_logl        | Boolean | FALSE | TRUE |
|                      | VehSpdSnsrVld_Cnt_T_logl     | Boolean | FALSE | TRUE |
|                      | Msg1F1Miss_Cnt_T_logl        | Boolean | FALSE | TRUE |
|                      | BusOffHiSpd_Cnt_T_logl       | Boolean | FALSE | TRUE |
|                      | HwTq_HwNwtMtr_T_f32          | Float32 | -10   | 10   |
| **Output**           | TblIdxNr_Cnt_T_u16           | Uint16  | 0     | 511  |

*  
*

## Design Rationale

## Processing

Created to reduce static path count and cyclomatic complexity of
periodic function. Refer FDD

## Local Function \#2

|                      |                       |         |       |      |
|----------------------|-----------------------|---------|-------|------|
| **Function Name**    | GetMotTqCmdSca        | Type    | Min   | Max  |
| **Arguments Passed** | AssiEna_Cnt_T_logl    | Boolean | FALSE | TRUE |
| **Output**           | MotTqCmdSca_Cnt_T_f32 | Boolean | 0.0   | 1.0  |

## Design Rationale

Created to reduce static path count and cyclomatic complexity of
periodic function.

## Processing

Sets MotTqCmdSca to 1.0 if AssiEna is TRUE and sets it to 0.0 otherwise.

## Local Function \#3

|                      |                       |         |     |     |
|----------------------|-----------------------|---------|-----|-----|
| **Function Name**    | KeepAssiHwTqTmr       | Type    | Min | Max |
| **Arguments Passed** | HwTq_HwNwtMtr_T_f32   | Float32 | -10 | 10  |
|                      | \* TblIdxNr_Cnt_T_u16 | Uint16  | 0   | 511 |

## Design Rationale

Created to reduce static path count and cyclomatic complexity of local
function \#2.

\*TblIdxNr_Cnt_T_u16 is an output of this function.

## Processing

Refer ‘KeepAssi_HwTqTmr’ block in model.

## GLOBAL Function/Macro Definitions

None

# Known Limitations with Design

-   
-   
-   

# UNIT TEST CONSIDERATION

-   

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

| **Ref. \#** | **Title**                                                                                                                                                               | **Version**                    |
|-------|-------------------------------------------------|-----------------|
| 1           | AUTOSAR Specification of Memory Mapping (Link:[AUTOSAR_SWS_MemoryMapping.pdf](http://www.autosar.org/download/R4.0/AUTOSAR_SWS_MemoryMapping.pdf))                      | v1.3.0 R4.0 Rev 2              |
| 2           | MDD Guideline                                                                                                                                                           | EA4 01.00.00                   |
| 3           | EA4 [Software Naming Conventions.doc](http://misagweb01.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_fc55f/Software%20Naming%20Conventions%2003x(In%20Work).doc) | 01.00.00                       |
| 4           | [Software Design and Coding Standards.doc](http://eroom1.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_1a67a9/Software%20Design%20and%20Coding%20Standards.doc)   | 2.1                            |
| 5           | CF017A_GmVehPwrMod_Design                                                                                                                                               | See Synergy subproject version |

{% endraw %}