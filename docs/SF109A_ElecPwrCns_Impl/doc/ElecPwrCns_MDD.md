---
layout: default
title: ElecPwrCns_MDD
nav_order: 2
parent: Component Implementation
---
{% raw %}
**Module Design Document**

**For**

**ElecPwrCns**

**May 10, 2016**

**Prepared For:**

**Software Engineering**

**Nexteer Automotive,**

**Saginaw, MI, USA**

**Prepared By:**

**Vishnu Mohan(Tata Elxsi),**

**Trivandrum, INDIA**

**<u>Change</u>** History

|                 |              |             |             |
|-----------------|--------------|-------------|-------------|
| **Description** | **Author**   | **Version** | **Date**    |
| Initial Version | Vishnu Mohan | 1.0         | 10-May-2016 |

**<u>Table of Contents</u>**

[1 Introduction 4](#introduction)

[1.1 Purpose 4](#purpose)

[2 ElecPwrCns & High-Level Description
5](#elecpwrcns-high-level-description)

[3 Design details of software module
6](#design-details-of-software-module)

[3.1 Graphical representation of ElecPwrCns
6](#graphical-representation-of-elecpwrcns)

[3.2 Data Flow Diagram 6](#data-flow-diagram)

[3.2.1 Component level DFD 6](#component-level-dfd)

[3.2.2 Function level DFD 6](#function-level-dfd)

[4 Constant Data Dictionary 7](#constant-data-dictionary)

[4.1 Program (fixed) Constants 7](#program-fixed-constants)

[4.1.1 Embedded Constants 7](#embedded-constants)

[5 Software Component Implementation
8](#software-component-implementation)

[5.1 Sub-Module Functions 8](#sub-module-functions)

[5.1.1 Per: ElecPwrCnsPer1 8](#per-elecpwrcnsper1)

[5.1.1.1 Design Rationale 8](#design-rationale)

[5.1.1.2 Store Module Inputs to Local copies
8](#store-module-inputs-to-local-copies)

[5.1.1.3 (Processing of function)……… 8](#processing-of-function)

[5.1.1.4 Store Local copy of outputs into Module Outputs
8](#store-local-copy-of-outputs-into-module-outputs)

[5.2 Server Runables 8](#server-runables)

[5.3 Interrupt Functions 8](#interrupt-functions)

[5.4 Module Internal (Local) Functions
8](#module-internal-local-functions)

[5.5 GLOBAL Function/Macro Definitions
8](#global-functionmacro-definitions)

[6 Known Limitations with Design 9](#known-limitations-with-design)

[7 UNIT TEST CONSIDERATION 10](#unit-test-consideration)

[Appendix A Abbreviations and Acronyms 11](#abbreviations-and-acronyms)

[Appendix B Glossary 12](#glossary)

[Appendix C References 13](#references)

# Introduction

## Purpose

MDD for Electrical Electric Power Consumption

# ElecPwrCns & High-Level Description

Please refer FDD

# Design details of software module

## Graphical representation of ElecPwrCns

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/SF109A_ElecPwrCns_Impl/doc/mediax/media/image1.png"
style="width:2.93681in;height:4.21944in" />

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

|                          |            |       |       |
|--------------------------|------------|-------|-------|
| Constant Name            | Resolution | Units | Value |
| Please refer the .m file |            |       |       |

# Software Component Implementation

## Sub-Module Functions

## Per: ElecPwrCnsPer1

## Design Rationale

None

## Store Module Inputs to Local copies

None

##  (Processing of function)………

Please refer FDD

## Store Local copy of outputs into Module Outputs

Please refer FDD

## Server Runables 

None

## Interrupt Functions

None

## Module Internal (Local) Functions

None

## GLOBAL Function/Macro Definitions

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

| **Ref. \#** | **Title**                                                                                                                                                     | **Version**                     |
|-------|-------------------------------------------------|-----------------|
| 1           | AUTOSAR Specification of Memory Mapping (Link:[AUTOSAR_SWS_MemoryMapping.pdf](http://www.autosar.org/download/R4.0/AUTOSAR_SWS_MemoryMapping.pdf))            | v1.3.0 R4.0 Rev 2               |
| 2           | MDD Guideline                                                                                                                                                 | EA4 01.00.00                    |
| 3           | [Software Naming Conventions.doc](http://misagweb01.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_fc55f/Software Naming Conventions 03x(In Work).doc)   | 1.0                             |
| 4           | [Software Design and Coding Standards.doc](http://eroom1.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_1a67a9/Software Design and Coding Standards.doc) | 2.1                             |
| 5           | FDD: SF109A_ElecPwrCns_Design                                                                                                                                 | See Synergy sub project version |

{% endraw %}