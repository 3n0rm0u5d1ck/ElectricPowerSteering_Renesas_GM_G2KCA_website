---
layout: default
title: CurrReasbnDiagc_MDD
nav_order: 2
parent: Component Implementation
---
{% raw %}
**Module Design Document**

**For**

**CurrReasbnDiagc**

**Dec 15, 2016**

**Prepared For:**

**Software Engineering**

**Nexteer Automotive,**

**Saginaw, MI, USA**

**Prepared By:**

**Krishna Anne**

**Nexteer Automotive,**

**Saginaw, MI, USA  
****<u>Change History</u>**

|             |                 |              |             |
|-------------|-----------------|--------------|-------------|
| **Version** | **Description** | **Author**   | **Date**    |
| 1           | Initial Version | Krishna Anne | 15-Dec-2016 |

**  
**

**<u>Table of Contents</u>**

[1 Introduction [5](#introduction)](#introduction)

[2 MotRplCoggCmd & High-Level Description
[6](#motrplcoggcmd-high-level-description)](#motrplcoggcmd-high-level-description)

[3 Design details of software module
[7](#design-details-of-software-module)](#design-details-of-software-module)

[3.1 Graphical representation of MotRplCoggCmd
[7](#graphical-representation-of-currreasbndiagc)](#graphical-representation-of-currreasbndiagc)

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

[5.1 Sub-Module Functions [9](#_Toc338170484)](#_Toc338170484)

[5.1.1 Init: MotRplCoggCmdInit1 [9](#_Toc421011514)](#_Toc421011514)

[5.1.1.1 Design Rationale [9](#design-rationale)](#design-rationale)

[5.1.1.2 Module Outputs [9](#module-outputs)](#module-outputs)

[5.1.2 Per: MotRplCoggCmdPer1
[9](#per-currreasbndiagcper2)](#per-currreasbndiagcper2)

[5.1.2.1 Design Rationale [9](#design-rationale-3)](#design-rationale-3)

[5.1.2.2 Store Module Inputs to Local copies
[9](#store-module-inputs-to-local-copies-1)](#store-module-inputs-to-local-copies-1)

[5.1.2.3 (Processing of function)………
[9](#processing-of-function-1)](#processing-of-function-1)

[5.1.2.4 Store Local copy of outputs into Module Outputs
[9](#store-local-copy-of-outputs-into-module-outputs-1)](#store-local-copy-of-outputs-into-module-outputs-1)

[5.2 Server Runables [9](#server-runables)](#server-runables)

[5.2.1 GetMotCoggCmdPrm_Oper [9](#_Toc442951602)](#_Toc442951602)

[5.2.1.1 Design Rationale [9](#_Toc442951603)](#_Toc442951603)

[5.2.1.2 Store Module Inputs to Local copies
[10](#_Toc442951604)](#_Toc442951604)

[5.2.1.3 (Processing of function)………
[10](#_Toc442951605)](#_Toc442951605)

[5.2.1.4 Store Local copy of outputs into Module Outputs
[10](#_Toc442951606)](#_Toc442951606)

[5.2.1 SetMotCoggCmdPrm_Oper [10](#_Toc442951607)](#_Toc442951607)

[5.2.1.1 Design Rationale [10](#_Toc442951608)](#_Toc442951608)

[5.2.1.2 Store Module Inputs to Local copies
[10](#_Toc442951609)](#_Toc442951609)

[5.2.1.3 (Processing of function)………
[10](#_Toc442951610)](#_Toc442951610)

[5.2.1.4 Store Local copy of outputs into Module Outputs
[10](#_Toc442951611)](#_Toc442951611)

[5.3 Module Internal (Local) Functions
[10](#_Toc442951612)](#_Toc442951612)

[5.3.1 Local Function \#1 [10](#_Toc442951613)](#_Toc442951613)

[5.3.1.1 Design Rationale [10](#_Toc442951614)](#_Toc442951614)

[5.3.1.2 Processing [10](#_Toc442951615)](#_Toc442951615)

[6 Known Limitations with Design
[11](#known-limitations-with-design)](#known-limitations-with-design)

[7 UNIT TEST CONSIDERATION
[12](#unit-test-consideration)](#unit-test-consideration)

[Appendix A Abbreviations and Acronyms
[13](#abbreviations-and-acronyms)](#abbreviations-and-acronyms)

[Appendix B Glossary [14](#glossary)](#glossary)

[Appendix C References [15](#references)](#references)

# Introduction

Please refer the Design Subproject.

# MotRplCoggCmd & High-Level Description

Please refer the Design Subproject.

# Design details of software module

## Graphical representation of CurrReasbnDiagc

Please refer the Design Subproject.

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/SF031A_CurrReasbnDiagc_Impl/doc/mediax/media/image1.png"
style="width:3.45278in;height:5.51875in" />

## Data Flow Diagram

### Component level DFD

### Function level DFD

# Constant Data Dictionary

## Program (fixed) Constants

### Embedded Constants

#### Local Constants

| Constant Name                       | Resolution                          | Units                               | Value                               |
|---------------------------------|---------------|-----------|-------------|
| Please refer the Design Subproject. | Please refer the Design Subproject. | Please refer the Design Subproject. | Please refer the Design Subproject. |

# Software Component Implementation

<span id="_Toc338170484" class="anchor"></span>Please refer the Design
Subproject

## Sub-Module Functions

<span id="_Toc421011514" class="anchor"></span>Please refer the Design
Subproject

## Init: CurrReasbnDiagcInit1

## Design Rationale

Runs at speed of MotorControl X2. Please refer the Design Subproject for
more details.

## Module Outputs

Please refer the Design Subproject

## Init: CurrReasbnDiagcInit2

## Design Rationale

Please refer the Design Subproject

## Module Outputs

Please refer the Design Subproject

###  [section]

## Per: CurrReasbnDiagcPer1

## Design Rationale

Runs at speed of MotorControl X2. Please refer the Design Subproject for
more details.

## Store Module Inputs to Local copies

Please refer the Design Subproject

##  (Processing of function)………

Please refer the Design Subproject

## Store Local copy of outputs into Module Outputs

Please refer the Design Subproject

###  [section-1]

## Per: CurrReasbnDiagcPer2

## Design Rationale

Please refer the Design Subproject

## Store Module Inputs to Local copies

Please refer the Design Subproject

##  (Processing of function)………

Please refer the Design Subproject

## Store Local copy of outputs into Module Outputs

Please refer the Design Subproject

## Server Runables 

None

# Known Limitations with Design

None

# UNIT TEST CONSIDERATION

None

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

| **Ref. \#** | **Title**                                                                                                                                                             | **Version**                         |
|-------|-------------------------------------------------|-----------------|
| 1           | AUTOSAR Specification of Memory Mapping (Link:[AUTOSAR_SWS_MemoryMapping.pdf](http://www.autosar.org/download/R4.0/AUTOSAR_SWS_MemoryMapping.pdf))                    | v1.3.0 R4.0 Rev 2                   |
| 2           | MDD Guideline                                                                                                                                                         | EA4 01.00.01                        |
| 3           | [Software Naming Conventions.doc](http://misagweb01.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_fc55f/Software%20Naming%20Conventions%2003x(In%20Work).doc)   | 1.0                                 |
| 4           | [Software Design and Coding Standards.doc](http://eroom1.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_1a67a9/Software%20Design%20and%20Coding%20Standards.doc) | 2.1                                 |
| 5           | FDD : SF031A_CurrReasbnDiagc_Design                                                                                                                                   | Please refer the Design Subproject. |

{% endraw %}