---
layout: default
title: MotAgCorrln_MDD
nav_order: 3
parent: Component Implementation
---
{% raw %}
**Module Design Document**

**For**

**‘MotAgCorrln’**

**Jun 01, 2016**

**Prepared For:**

**Software Engineering**

**Nexteer Automotive,**

**Saginaw, MI, USA**

**Prepared By:**

**Nick Saxton,**

**Nexteer Automotive,**

**Saginaw, MI, USA  
<u>Change History</u>**

|                 |             |             |             |
|-----------------|-------------|-------------|-------------|
| **Description** | **Author**  | **Version** | **Date**    |
| Initial Version | Nick Saxton | 1.0         | 01-Jun-2016 |

**  
**

<u>Table of Contents</u>

[1 Introduction [5](#introduction)](#introduction)

[2 MotAgCorrln & High-Level Description
[6](#motagcorrln-high-level-description)](#motagcorrln-high-level-description)

[3 Design details of software module
[7](#design-details-of-software-module)](#design-details-of-software-module)

[3.1 Graphical representation of MotAgCorrln
[7](#graphical-representation-of-motagcorrln)](#graphical-representation-of-motagcorrln)

[3.2 Data Flow Diagram [7](#data-flow-diagram)](#data-flow-diagram)

[3.2.1 Component level DFD
[7](#component-level-dfd)](#component-level-dfd)

[3.2.2 Function level DFD [7](#function-level-dfd)](#function-level-dfd)

[4 Constant Data Dictionary
[8](#constant-data-dictionary)](#constant-data-dictionary)

[4.1 Program (fixed) Constants
[8](#program-fixed-constants)](#program-fixed-constants)

[4.1.1 Embedded Constants [8](#embedded-constants)](#embedded-constants)

[5 Software Component Implementation
[9](#software-component-implementation)](#software-component-implementation)

[5.1 Sub-Module Functions
[9](#sub-module-functions)](#sub-module-functions)

[5.1.1 Init: MotAgCorrlnInit1
[9](#init-motagcorrlninit1)](#init-motagcorrlninit1)

[5.1.1.1 Design Rationale [9](#design-rationale)](#design-rationale)

[5.1.1.2 Module Outputs [9](#module-outputs)](#module-outputs)

[5.1.2 Per: MotAgCorrlnPer1
[9](#per-motagcorrlnper1)](#per-motagcorrlnper1)

[5.1.2.1 Design Rationale [9](#design-rationale-1)](#design-rationale-1)

[5.1.2.2 Store Module Inputs to Local copies
[9](#store-module-inputs-to-local-copies)](#store-module-inputs-to-local-copies)

[5.1.2.3 (Processing of function)………
[9](#processing-of-function)](#processing-of-function)

[5.1.2.4 Store Local copy of outputs into Module Outputs
[9](#store-local-copy-of-outputs-into-module-outputs)](#store-local-copy-of-outputs-into-module-outputs)

[5.2 Server Runables [9](#server-runables)](#server-runables)

[5.3 *None*Interrupt Functions
[9](#noneinterrupt-functions)](#noneinterrupt-functions)

[5.3.1 Interrupt Function Name
[9](#interrupt-function-name)](#interrupt-function-name)

[5.3.1.1 Design Rationale [9](#design-rationale-2)](#design-rationale-2)

[5.3.1.2 (Processing of the ISR function)…..
[9](#processing-of-the-isr-function..)](#processing-of-the-isr-function..)

[5.4 Module Internal (Local) Functions
[10](#module-internal-local-functions)](#module-internal-local-functions)

[5.4.1 Local Function \#1 [10](#local-function-1)](#local-function-1)

[5.4.1.1 Design Rationale
[10](#design-rationale-3)](#design-rationale-3)

[5.4.1.2 Processing [10](#processing)](#processing)

[5.4.2 Local Function \#2 [10](#local-function-2)](#local-function-2)

[5.4.2.1 Design Rationale
[10](#design-rationale-4)](#design-rationale-4)

[5.4.2.2 Processing [10](#processing-1)](#processing-1)

[5.5 GLOBAL Function/Macro Definitions
[10](#global-functionmacro-definitions)](#global-functionmacro-definitions)

[5.5.1 GLOBAL Function \#1 [10](#global-function-1)](#global-function-1)

[5.5.1.1 Design Rationale
[10](#design-rationale-5)](#design-rationale-5)

[5.5.1.2 processing [11](#processing-2)](#processing-2)

[6 Known Limitations with Design
[12](#known-limitations-with-design)](#known-limitations-with-design)

[7 UNIT TEST CONSIDERATION
[13](#unit-test-consideration)](#unit-test-consideration)

[Appendix A Abbreviations and Acronyms
[14](#abbreviations-and-acronyms)](#abbreviations-and-acronyms)

[Appendix B Glossary [15](#glossary)](#glossary)

[Appendix C References [16](#references)](#references)

# Introduction

MDD for MotAgCorrln .

# MotAgCorrln & High-Level Description

*Refer FDD*

# Design details of software module

## Graphical representation of MotAgCorrln

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/ES249B_MotAgCorrln_Impl/doc/mediax/media/image1.PNG"
style="width:4.55272in;height:4.22976in" />

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

| Constant Name                | Resolution | Units | Value |
|------------------------------|------------|-------|-------|
| MOTAGMECLCORRLNSTMIN_CNT_U08 | None       | Cnt   | 0     |
| MOTAGMECLCORRLNSTMAX_CNT_U08 | None       | Cnt   | 3     |
| MOTAGMECLIDPTSIGMIN_CNT_U08  | None       | Cnt   | 0     |
| MOTAGMECLIDPTSIGMAX_CNT_U08  | None       | Cnt   | 2     |

# Software Component Implementation

## Sub-Module Functions

## Init: MotAgCorrlnInit1

*Refer FDD*

## Design Rationale

*Design follows implementation in FDD.*

## Module Outputs

*Refer FDD*

## Per: MotAgCorrlnPer1

*Refer FDD*

## Design Rationale

*Refer FDD*

## Store Module Inputs to Local copies

*Refer FDD*

##  (Processing of function)………

*Refer to FDD (Block ‘MotAgCorrlnPer1’)*

## Store Local copy of outputs into Module Outputs

*Refer FDD*

## Server Runables 

## *None*Interrupt Functions

*None*

## Interrupt Function Name

*None*

## Design Rationale

*None*

## (Processing of the ISR function)…..

*None*

## Module Internal (Local) Functions

## Local Function \#1

|                      |                          |                 |               |               |
|--------------|-----------------------|---------------|-----------|-----------|
| **Function Name**    | MtrAgSigAvlCheck         | Type            | Min           | Max           |
| **Arguments Passed** | SigRollg_Cnt_T_u08       | uint8           | 0             | 255           |
|                      | SigQlfr_Cnt_T_enum       | Enum (SigQlfr1) | SIGQLFR_NORES | SIGQLFR_FAILD |
|                      | LstRollg_Cnt_T_u08       | uint8           | 0             | 255           |
|                      | LstStall_Cnt_T_u08       | uint8           | 0             | 255           |
|                      | \*StallCntOutp_Cnt_T_u08 | uint8           | 0             | 255           |
| **Return Value**     | SigAvl_Cnt_T_lgc         | boolean         | FALSE         | TRUE          |

## Design Rationale

Checks Signal Availability of Motor. Implementation of 'MtrAgA
SigAvlCheck' and 'MtrAgB SigAvlCheck' blocks.

## Processing

**Note:** ‘\* StallCntOutp_Cnt_T_u08’ is an output of this function.

###  Local Function \#2

|                      |                           |         |       |       |
|----------------------|---------------------------|---------|-------|-------|
| **Function Name**    | TestOkCheck               | Type    | Min   | Max   |
| **Arguments Passed** | MotAgAMecl_MotRev_T_u0p16 | u0p16   | 0     | 65535 |
|                      | MotAgBMecl_MotRev_T_u0p16 | u0p16   | 0     | 65535 |
| **Return Value**     | TestOk_Cnt_T_logl         | boolean | FALSE | TRUE  |

## Design Rationale

Implementation of 'TestOk' check functionality. This function
corresponds to the block 'MotAgA vs MotAgB'.

## Processing

Refer FDD.

## GLOBAL Function/Macro Definitions

## GLOBAL Function \#1

None

## Design Rationale

None

## processing

None

# Known Limitations with Design

None

# UNIT TEST CONSIDERATION

None

####### Abbreviations and Acronyms

| **Abbreviation or Acronym** | **Description**            |
|-----------------------------|----------------------------|
| FDD                         | Functional Design Document |

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

| **Ref. \#** | **Title**                                                                                                                                                             | **Version**                    |
|-------|-------------------------------------------------|-----------------|
| 1           | AUTOSAR Specification of Memory Mapping (Link:[AUTOSAR_SWS_MemoryMapping.pdf](http://www.autosar.org/download/R4.0/AUTOSAR_SWS_MemoryMapping.pdf))                    | v1.3.0 R4.0 Rev 2              |
| 2           | MDD Guideline                                                                                                                                                         | EA4 01.00.02                   |
| 3           | [Software Naming Conventions.doc](http://misagweb01.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_fc55f/Software%20Naming%20Conventions%2003x(In%20Work).doc)   | EA4 01.00.02                   |
| 4           | [Software Design and Coding Standards.doc](http://eroom1.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_1a67a9/Software%20Design%20and%20Coding%20Standards.doc) | EA4 01.00.02                   |
| 5           | ES249B_MotAgCorrln_Design                                                                                                                                             | See Synergy subproject version |

{% endraw %}