---
layout: default
title: TqOscn_MDD
nav_order: 2
parent: Component Implementation
---
{% raw %}
**Module Design Document**

**For**

**TqOscn**

**Feb 05, 2016**

**Prepared For:**

**Software Engineering**

**Nexteer Automotive,**

**Saginaw, MI, USA**

**Prepared By:**

**Krishna Kanth Anne,**

**Nexteer Automotive,**

**Saginaw, MI, USA  
<u>Change History</u>**

|                 |                    |             |             |
|-----------------|--------------------|-------------|-------------|
| **Description** | **Author**         | **Version** | **Date**    |
| Initial Version | Krishna Kanth Anne | 1.0         | 05-Feb-2016 |

**  
**

**<u>Table of Contents</u>**

[1 Introduction [3](#introduction)](#introduction)

[1.1 Purpose [3](#purpose)](#purpose)

[1.2 Scope [3](#_Toc424732604)](#_Toc424732604)

[2 \<Component Name\> & High-Level Description
[3](#tqoscn-high-level-description)](#tqoscn-high-level-description)

[3 Design details of software module
[3](#design-details-of-software-module)](#design-details-of-software-module)

[3.1 Graphical representation of \<Component Name\>
[3](#_Toc424732607)](#_Toc424732607)

[3.2 Data Flow Diagram [3](#data-flow-diagram)](#data-flow-diagram)

[3.2.1 Component level DFD
[3](#component-level-dfd)](#component-level-dfd)

[3.2.2 Function level DFD [3](#function-level-dfd)](#function-level-dfd)

[4 Constant Data Dictionary
[3](#constant-data-dictionary)](#constant-data-dictionary)

[4.1 Program (fixed) Constants
[3](#program-fixed-constants)](#program-fixed-constants)

[4.1.1 Embedded Constants [3](#embedded-constants)](#embedded-constants)

[5 Software Component Implementation
[3](#software-component-implementation)](#software-component-implementation)

[5.1 Sub-Module Functions
[3](#sub-module-functions)](#sub-module-functions)

[5.1.1 Init: \<ModuleName\>Init\<n\>
[3](#init-tqoscninit1)](#init-tqoscninit1)

[5.1.1.1 Design Rationale [3](#design-rationale)](#design-rationale)

[5.1.1.2 Module Outputs [3](#module-outputs)](#module-outputs)

[5.1.2 Per: \<ModuleName\>\_Per\<n\> [3](#none)](#none)

[5.1.2.1 Design Rationale [3](#design-rationale-1)](#design-rationale-1)

[5.1.2.2 Store Module Inputs to Local copies
[3](#store-module-inputs-to-local-copies)](#store-module-inputs-to-local-copies)

[5.1.2.3 (Processing of function)………
[3](#_Toc421011521)](#_Toc421011521)

[5.1.2.4 Store Local copy of outputs into Module Outputs
[3](#store-local-copy-of-outputs-into-module-outputs)](#store-local-copy-of-outputs-into-module-outputs)

[5.2 Server Runables [3](#server-runnables)](#server-runnables)

[5.2.1 \<Server Runable Name\> [3](#_Toc424732625)](#_Toc424732625)

[5.2.1.1 Design Rationale [3](#_Toc424732626)](#_Toc424732626)

[5.2.1.2 (Processing of function)………
[3](#_Toc424732627)](#_Toc424732627)

[5.3 Interrupt Functions
[3](#interrupt-functions)](#interrupt-functions)

[5.3.1 Interrupt Function Name [3](#_Toc424732629)](#_Toc424732629)

[5.3.1.1 Design Rationale [3](#_Toc424732630)](#_Toc424732630)

[5.3.1.2 (Processing of the ISR function)…..
[3](#_Toc424732631)](#_Toc424732631)

[5.4 Module Internal (Local) Functions
[3](#module-internal-local-functions)](#module-internal-local-functions)

[5.4.1 Local Function \#1 [3](#local-function-1)](#local-function-1)

[5.4.1.1 Design Rationale [3](#_Toc424732634)](#_Toc424732634)

[5.4.1.2 Processing [3](#_Toc424732635)](#_Toc424732635)

[5.5 GLOBAL Function/Macro Definitions
[3](#global-functionmacro-definitions)](#global-functionmacro-definitions)

[5.5.1 GLOBAL Function \#1 [3](#_Toc424732637)](#_Toc424732637)

[5.5.1.1 Design Rationale [3](#_Toc424732638)](#_Toc424732638)

[5.5.1.2 processing [3](#_Toc424732639)](#_Toc424732639)

[6 Known Limitations with Design
[3](#known-limitations-with-design)](#known-limitations-with-design)

[7 UNIT TEST CONSIDERATION
[3](#unit-test-consideration)](#unit-test-consideration)

[Appendix A Abbreviations and Acronyms
[3](#abbreviations-and-acronyms)](#abbreviations-and-acronyms)

[Appendix B Glossary [3](#glossary)](#glossary)

[Appendix C References [3](#references)](#references)

# Introduction

## Purpose

# TqOscn & High-Level Description

Please refer FDD.

# Design details of software module

## Graphical representation of TqOscn

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/SF043A_TqOscn_Impl/doc/mediax/media/image1.png"
style="width:4.31319in;height:5.66111in" />

## Data Flow Diagram

Please refer FDD

### Component level DFD

Please refer FDD

### Function level DFD

Please refer FDD

# Constant Data Dictionary

## Program (fixed) Constants

### Embedded Constants

#### Local Constants

| Constant Name        | Resolution | Units | Value |
|----------------------|------------|-------|-------|
| Please refer .m file |            |       |       |

# Software Component Implementation

## Sub-Module Functions

## Init: TqOscnInit1

## Design Rationale

None

## Module Outputs

## None

## Per: TqOscnPer1

## Design Rationale

None

## Store Module Inputs to Local copies

<span id="_Toc421011521" class="anchor"></span>None

##  (Processing of function)………

> Please refer FDD

## Store Local copy of outputs into Module Outputs

Please refer FDD

## Server Runnables 

None

## Interrupt Functions

> None

## Module Internal (Local) Functions

## Local Function \#1 

|                      |                                           |         |          |         |
|---------------|--------------------------------|---------|---------|---------|
| **Function Name**    | AmpRateLim                                | Type    | Min      | Max     |
| **Arguments Passed** | LimdAmp_MotNwtMtr_T_f32                   | Float32 | 0.0F     | 1.2F    |
|                      | HwOscnRisngRampRate_MotNwtMtrPerSec_T_f32 | Float32 | 0.1F     | 4400.0F |
|                      | HwOscnFallRampRate_MotNwtMtrPerSec_T_f32  | Float32 | -4400.0F | -0.1F   |
|                      | HwOscnEna_Cnt_T_logl                      | Boolean | FALSE    | TRUE    |
|                      | \*NonZeroAmpFlg_Cnt_T_logl                | Boolean | FALSE    | TRUE    |
| **Return Value**     | RateLimdAmp_MotNwtMtr_T_f32               | Float32 | 0.0002F  | -8.8F   |

## Local Function \#2

|                      |                          |         |        |        |
|----------------------|--------------------------|---------|--------|--------|
| **Function Name**    | ChkFlg                   | Type    | Min    | Max    |
| **Arguments Passed** | PhaAg_MatRad_T_f32       | Float32 | 0.125F | 0.628F |
| **Return Value**     | TqOscnPhaAg_MatRad_T_f32 | Float32 | 0.0F   | 0.628F |

## GLOBAL Function/Macro Definitions

> None

# Known Limitations with Design

> None

# UNIT TEST CONSIDERATION

> None.

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
| 2           | MDD Guideline                                                                                                                                                         | EA4 01.00.00                    |
| 3           | [Software Naming Conventions.doc](http://misagweb01.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_fc55f/Software%20Naming%20Conventions%2003x(In%20Work).doc)   | 1.0                             |
| 4           | [Software Design and Coding Standards.doc](http://eroom1.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_1a67a9/Software%20Design%20and%20Coding%20Standards.doc) | 2.0                             |
| 5           | FDD: SF043A\_ TqOscn_Design                                                                                                                                           | See Synergy sub project version |

{% endraw %}