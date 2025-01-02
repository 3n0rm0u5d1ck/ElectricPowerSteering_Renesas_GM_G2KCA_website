---
layout: default
title: MotAg3Meas_MDD
nav_order: 2
parent: Component Implementation
---
{% raw %}
**Module Design Document**

**For**

**MotAg3Meas**

**Nov 7, 2016**

**Prepared By:**

**Shruthi Raghavan,**

**Nexteer Automotive,**

**Saginaw, MI, USA  
<u>Change History</u>**

|                 |                  |             |          |
|-----------------|------------------|-------------|----------|
| **Description** | **Author**       | **Version** | **Date** |
| Initial Version | Shruthi Raghavan | 1.0         | 7-Nov-16 |

**<u>  
</u>**

**<u>Table of Contents</u>**

[1 Introduction [4](#introduction)](#introduction)

[1.1 Purpose [4](#purpose)](#purpose)

[2 MotAg3Meas & High-Level Description
[5](#motag3meas-high-level-description)](#motag3meas-high-level-description)

[3 Design details of software module
[6](#design-details-of-software-module)](#design-details-of-software-module)

[3.1 Graphical representation of MotAg3Meas
[6](#graphical-representation-of-motag3meas)](#graphical-representation-of-motag3meas)

[3.2 Data Flow Diagram [6](#data-flow-diagram)](#data-flow-diagram)

[3.2.1 Component level DFD
[6](#component-level-dfd)](#component-level-dfd)

[3.2.2 Function level DFD [6](#function-level-dfd)](#function-level-dfd)

[4 Constant Data Dictionary
[7](#constant-data-dictionary)](#constant-data-dictionary)

[4.1 Program (fixed) Constants
[7](#program-fixed-constants)](#program-fixed-constants)

[4.1.1 Embedded Constants [7](#embedded-constants)](#embedded-constants)

[5 Software Component Implementation
[8](#software-component-implementation)](#software-component-implementation)

[5.1 Sub-Module Functions
[8](#sub-module-functions)](#sub-module-functions)

[5.1.1 Init: MotAg3MeasInit1
[8](#init-motag3measinit1)](#init-motag3measinit1)

[5.1.2 Per: None [8](#per-none)](#per-none)

[5.2 Server Runables [8](#server-runables)](#server-runables)

[5.2.1 GetMotAg3Mecl_Oper [8](#getmotag3mecl_oper)](#getmotag3mecl_oper)

[5.3 Interrupt Functions
[8](#interrupt-functions)](#interrupt-functions)

[5.3.1 Interrupt Function Name
[8](#interrupt-function-name)](#interrupt-function-name)

[5.4 Module Internal (Local) Functions
[9](#module-internal-local-functions)](#module-internal-local-functions)

[5.4.1 Local Function \#1 [9](#local-function-1)](#local-function-1)

[5.5 GLOBAL Function/Macro Definitions
[9](#global-functionmacro-definitions)](#global-functionmacro-definitions)

[5.5.1 GLOBAL Function \#1 [9](#global-function-1)](#global-function-1)

[6 Known Limitations with Design
[10](#known-limitations-with-design)](#known-limitations-with-design)

[7 UNIT TEST CONSIDERATION
[11](#unit-test-consideration)](#unit-test-consideration)

[Appendix A Abbreviations and Acronyms
[12](#abbreviations-and-acronyms)](#abbreviations-and-acronyms)

[Appendix B Glossary [13](#glossary)](#glossary)

[Appendix C References [14](#references)](#references)

# Introduction

## Purpose

Module design document for MotAg3Meas SWC.

# MotAg3Meas & High-Level Description

*Refer to design.*

# Design details of software module

## Graphical representation of MotAg3Meas

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CM510A_MotAg3Meas_Impl/doc/mediax/media/image1.png"
style="width:4.46667in;height:2.15833in" />

## Data Flow Diagram

### Component level DFD

N/A

### Function level DFD

N/A

# Constant Data Dictionary

## Program (fixed) Constants

### Embedded Constants

#### Local Constants

Refer DataDict.m file for rest of the constants.

| Constant Name               | Resolution | Units | Value |
|-----------------------------|------------|-------|-------|
| REGENCA0CTLINITVAL_CNT_U16  | 1          | Cnt   | 0x03U |
| REGENCA0IOC1INITVAL_CNT_U08 | 1          | Cnt   | 0x04U |
| REGENCA0TTINITVAL_CNT_U08   | 1          | Cnt   | 0x01U |
| REGENCA0TSINITVAL_CNT_U08   | 1          | Cnt   | 0x01U |

# Software Component Implementation

## Sub-Module Functions

## Init: MotAg3MeasInit1

#### Design Rationale

Initialization of registers according to
CM510A_MotAg3Meas_RegisterConfiguration.xlsm

#### Module Outputs

None

## Per: None

#### Design Rationale

#### Module Outputs

## Server Runables 

### GetMotAg3Mecl_Oper

#### Design Rationale

Refer to FDD

####  (Processing of function)………

> Refer to FDD

## Interrupt Functions

> None

### Interrupt Function Name

#### Design Rationale

####  (Processing of the ISR function)…..

## Module Internal (Local) Functions

None

### Local Function \#1

#### Design Rationale

#### Processing

## GLOBAL Function/Macro Definitions

None

### GLOBAL Function \#1

#### Design Rationale

#### Processing

# Known Limitations with Design

None.

# UNIT TEST CONSIDERATION

None.

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

| **Ref. \#** | **Title**                                                                                                                                                             | **Version**                      |
|-------|-------------------------------------------------|-----------------|
| 1           | AUTOSAR Specification of Memory Mapping (Link:[AUTOSAR_SWS_MemoryMapping.pdf](http://www.autosar.org/download/R4.0/AUTOSAR_SWS_MemoryMapping.pdf))                    | v1.3.0 R4.0 Rev 2                |
| 2           | MDD Guideline                                                                                                                                                         | EA4 01.00.01                     |
| 3           | EA4 Software Naming Conventions                                                                                                                                       | 01.00.00                         |
| 4           | [Software Design and Coding Standards.doc](http://eroom1.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_1a67a9/Software%20Design%20and%20Coding%20Standards.doc) | 2.1                              |
| 5           | CM510A_MotAg3Meas_Design                                                                                                                                              | Refer Synergy SubProject Version |

{% endraw %}