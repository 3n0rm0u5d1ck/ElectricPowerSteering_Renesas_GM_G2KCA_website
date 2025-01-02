---
layout: default
title: Sci30CfgAndUse Module Design Document
nav_order: 2
parent: Component Implementation
---
{% raw %}
**Module Design Document**

**For**

**Sci30CfgAndUse**

**Jan 20, 2016**

**Prepared For:**

**Software Engineering**

**Nexteer Automotive,**

**Saginaw, MI, USA**

**Prepared By:**

**Software Group,**

**Nexteer Automotive,**

**Saginaw, MI, USA  
<u>Change History</u>**

|                 |               |             |          |
|-----------------|---------------|-------------|----------|
| **Description** | **Author**    | **Version** | **Date** |
| Initial Version | Avinash James | 1.0         | 01/20/17 |

**  
**

<u>Table of Contents</u>

[1 Introduction [5](#introduction)](#introduction)

[1.1.1 Purpose [5](#purpose)](#purpose)

[1.1.2 Scope [5](#scope)](#scope)

[2 Sci30CfgAndUse & High-Level Description
[6](#sci30cfganduse-high-level-description)](#sci30cfganduse-high-level-description)

[3 Design details of software module
[7](#design-details-of-software-module)](#design-details-of-software-module)

[3.1.1 Graphical representation of Sci30CfgAndUse
[7](#graphical-representation-of-sci30cfganduse)](#graphical-representation-of-sci30cfganduse)

[3.1.2 Data Flow Diagram [7](#data-flow-diagram)](#data-flow-diagram)

[3.1.3 Component level DFD
[7](#component-level-dfd)](#component-level-dfd)

[3.1.4 Function level DFD [7](#function-level-dfd)](#function-level-dfd)

[4 Constant Data Dictionary
[8](#constant-data-dictionary)](#constant-data-dictionary)

[4.1.1 Program (fixed) Constants
[8](#program-fixed-constants)](#program-fixed-constants)

[4.1.2 Embedded Constants [8](#embedded-constants)](#embedded-constants)

[5 Variable Data Dictionary
[9](#variable-data-dictionary)](#variable-data-dictionary)

[5.1.1 User defined typedef definition/declaration
[9](#user-defined-typedef-definitiondeclaration)](#user-defined-typedef-definitiondeclaration)

[5.1.2 Variable definition for enumerated types
[9](#variable-definition-for-enumerated-types)](#variable-definition-for-enumerated-types)

[6 Software Component Implementation
[10](#software-component-implementation)](#software-component-implementation)

[6.1.1 Sub-Module Functions
[10](#sub-module-functions)](#sub-module-functions)

[6.1.2 Init: Sci30CfgAndUseInit1
[10](#init-sci30cfganduseinit1)](#init-sci30cfganduseinit1)

[6.1.3 Design Rationale [10](#design-rationale)](#design-rationale)

[6.1.4 Module Outputs [10](#module-outputs)](#module-outputs)

[6.1.5 Per: Sci30CfgAndUsePer1
[10](#per-sci30cfganduseper1)](#per-sci30cfganduseper1)

[6.1.6 Per: Sci30CfgAndUsePer2
[10](#per-sci30cfganduseper2)](#per-sci30cfganduseper2)

[6.1.7 Per: Sci30CfgAndUsePer3
[11](#per-sci30cfganduseper3)](#per-sci30cfganduseper3)

[6.1.8 Per: Sci30CfgAndUsePer4
[11](#per-sci30cfganduseper4)](#per-sci30cfganduseper4)

[6.1.9 Server Runnables [11](#server-runnables)](#server-runnables)

[6.1.10 Interrupt Functions
[12](#interrupt-functions)](#interrupt-functions)

[6.1.11 Module Internal (Local) Function: RollOvrAdd
[12](#module-internal-local-function-rollovradd)](#module-internal-local-function-rollovradd)

[6.1.12 Module Internal (Local) Function: UpdDtsTxReg
[12](#module-internal-local-function-upddtstxreg)](#module-internal-local-function-upddtstxreg)

[6.1.13 Module Internal (Local) Function: UpdDtsRxReg
[12](#module-internal-local-function-upddtsrxreg)](#module-internal-local-function-upddtsrxreg)

[6.1.14 GLOBAL Function/Macro Definitions
[12](#global-functionmacro-definitions)](#global-functionmacro-definitions)

[7 Known Limitations with Design
[14](#known-limitations-with-design)](#known-limitations-with-design)

[8 UNIT TEST CONSIDERATION
[15](#unit-test-consideration)](#unit-test-consideration)

[Appendix A Abbreviations and Acronyms
[16](#abbreviations-and-acronyms)](#abbreviations-and-acronyms)

[Appendix B Glossary [17](#glossary)](#glossary)

[Appendix C References [18](#references)](#references)

# Introduction

## Purpose

## Scope

The following definitions are used throughout this document:

-   **<u>Shall</u>**: indicates a mandatory requirement without
    exception in compliance.

-   **<u>Should</u>**: indicates a mandatory requirement; exceptions
    allowed only with documented justification.

-   **<u>May</u>**: indicates an optional action.

# Sci30CfgAndUse & High-Level Description

*See FDD*

# Design details of software module

## Graphical representation of Sci30CfgAndUse

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CM745A_Sci30CfgAndUse_Impl/doc/mediax/media/image1.png"
style="width:2.51667in;height:1.71667in" />

## Data Flow Diagram

### Component level DFD

*See FDD*

### Function level DFD

*See FDD*

# Constant Data Dictionary

## Program (fixed) Constants

### Embedded Constants

#### Local Constants

| Constant Name                   | Resolution | Units   | Value  |
|---------------------------------|------------|---------|--------|
| **SCITXMAXBUFSIZE_CNT_U08**     | **1**      | **Cnt** | **80** |
| **IMCARBNRXDATASRCSCI_CNT_U08** | **1**      | **Cnt** | **1**  |
| **Refer .m file**               |            |         |        |

# Variable Data Dictionary

## User defined typedef definition/declaration 

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
<td>Ary1D_u8_Sci30CfgAndUseA</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Ary2D_u8_Sci30CfgAndUseA</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Ary2D_u8_Sci30CfgAndUseB</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Ary2D_u8_Sci30CfgAndUseC</td>
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
|           |              |       |

# Software Component Implementation

We have the global transmit and receive buffers declared at the file
level as static variables in different memory map sections. The global
transmit is in a memory map section aligned at 128 bit boundary in the
Sci30CfgAndUse data section as DTS has to read the data from the buffer.
The global memory map is also aligned on a 128 bit boundary but defined
in the .data_dma_128 memory map as the DTS has to write data to the
buffer

## Sub-Module Functions

## Init: Sci30CfgAndUseInit1

## Design Rationale

*Refer FDD*

## Module Outputs

*None*

## Per: Sci30CfgAndUsePer1

#### Design Rationale

*See FDD*

#### Store Module Inputs to Local copies

*Refer to FDD*

#### (Processing of function)………

*Refer to FDD*

#### Store Local copy of outputs into Module Outputs

*Refer to FDD*

#### Module Outputs

*None*

## Per: Sci30CfgAndUsePer2

#### Design Rationale

*See FDD*

#### Store Module Inputs to Local copies

*Refer to FDD*

#### (Processing of function)………

*Refer to FDD*

#### Store Local copy of outputs into Module Outputs

*Refer to FDD*

#### Module Outputs

*None*

## Per: Sci30CfgAndUsePer3

#### Design Rationale

*See FDD*

#### Store Module Inputs to Local copies

*Refer to FDD*

#### (Processing of function)………

*Refer to FDD*

#### Store Local copy of outputs into Module Outputs

*Refer to FDD*

#### Module Outputs

*None*

## Per: Sci30CfgAndUsePer4

#### Design Rationale

*See FDD*

#### Store Module Inputs to Local copies

*Refer to FDD*

#### (Processing of function)………

*Refer to FDD*

#### Store Local copy of outputs into Module Outputs

*Refer to FDD*

#### Module Outputs

*None*

## Server Runnables 

None

#### Design Rationale

#### Store Module Inputs to Local copies

####  (Processing of function)………

#### Store Local copy of outputs into Module Outputs

## Interrupt Functions

*None*

## Module Internal (Local) Function: RollOvrAdd

|                      |               |       |     |     |
|----------------------|---------------|-------|-----|-----|
| **Function Name**    | RollOvrAdd    | Type  | Min | Max |
| **Arguments Passed** | Idx_Cnt_T_u08 | Uint8 | 0   | 255 |
| **Return Value**     | None          |       |     |     |

#### Design Rationale

Function which returns the index value rolled over the max number of
bytes received

#### Processing

## Module Internal (Local) Function: UpdDtsTxReg

|                      |                     |       |     |     |
|----------------------|---------------------|-------|-----|-----|
| **Function Name**    | UpdDtsTxReg         | Type  | Min | Max |
| **Arguments Passed** | SciGlbTxCnt_Cnt_u08 | Uint8 | 0   | 255 |
| **Return Value**     | None                |       |     |     |

#### Design Rationale

#### Processing

## Module Internal (Local) Function: UpdDtsRxReg

|                      |             |      |     |     |
|----------------------|-------------|------|-----|-----|
| **Function Name**    | UpdDtsRxReg | Type | Min | Max |
| **Arguments Passed** | None        |      |     |     |
| **Return Value**     | None        |      |     |     |

#### Design Rationale

#### Processing

## GLOBAL Function/Macro Definitions

#### IninSciDtsChMstReg

|                      |                    |      |     |     |
|----------------------|--------------------|------|-----|-----|
| **Function Name**    | IninSciDtsChMstReg | Type | Min | Max |
| **Arguments Passed** | None               |      |     |     |
| **Return Value**     | None               |      |     |     |

#### Design Rationale

The DTS channel master registers can only be configured in the
supervisor mode. Hence we need to make use of a trusted function to
configure the channel master registers

#### Processing

# Known Limitations with Design

# UNIT TEST CONSIDERATION

\*Rte_Pim_SciDiagcRxMaxDataErrCntr(),\*Rte_Pim_SciDiagcOvrrunErrCntr(),\*Rte_Pim_SciDiagcParErrCntr()
and \*Rte_Pim_SciDiagcFrmErrCntr()are used as rolling counters. Hence
rollover on them is intentional.

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

| **Ref. \#** | **Title**                                                                                                                                                             | **Version**       |
|-------|-------------------------------------------------|-----------------|
| 1           | AUTOSAR Specification of Memory Mapping (Link:[AUTOSAR_SWS_MemoryMapping.pdf](http://www.autosar.org/download/R4.0/AUTOSAR_SWS_MemoryMapping.pdf))                    | v1.3.0 R4.0 Rev 2 |
| 2           | MDD Guideline                                                                                                                                                         | EA4 01.00.00      |
| 3           | [Software Naming Conventions.doc](http://misagweb01.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_fc55f/Software%20Naming%20Conventions%2003x(In%20Work).doc)   | 1.0               |
| 4           | [Software Design and Coding Standards.doc](http://eroom1.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_1a67a9/Software%20Design%20and%20Coding%20Standards.doc) | 2.0               |

{% endraw %}