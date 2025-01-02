---
layout: default
title: DualEcuIdn_MDD
nav_order: 2
parent: Component Implementation
---
{% raw %}
**Module Design Document**

**For**

**DualEcuIdn**

**June 19, 2015**

**Prepared For:**

**Software Engineering**

**Nexteer Automotive,**

**Saginaw, MI, USA**

**Prepared By:**

**SEPGroup,**

**Nexteer Automotive,**

**<u>Saginaw, MI, USAChange</u>** History

|                 |               |             |             |
|-----------------|---------------|-------------|-------------|
| **Description** | **Author**    | **Version** | **Date**    |
| Initial Version | Avinash James | 1.0         | 10-Jan-2017 |

<u>Table of Contents</u>

[**1** **Introduction 4**](#introduction)

[1.1 Purpose 4](#purpose)

[2 McuDiagc & High-Level Description
5](#component-name-high-level-description)

[3 Design details of software module
6](#design-details-of-software-module)

[3.1 Graphical representation of DualEcuIdn
6](#graphical-representation-of-dualecuidn)

[3.2 Data Flow Diagram 6](#data-flow-diagram)

[3.2.1 Component level DFD 6](#component-level-dfd)

[3.2.2 Function level DFD 6](#function-level-dfd)

[4 Constant Data Dictionary 7](#constant-data-dictionary)

[4.1 Program (fixed) Constants 7](#program-fixed-constants)

[4.1.1 Embedded Constants 7](#embedded-constants)

[5 Software Component Implementation
8](#software-component-implementation)

[5.1 Sub-Module Functions 8](#sub-module-functions)

[5.1.1 Init: DualEcuIdnInit1 8](#init-dualecuidninit1)

[5.1.1.1 Design Rationale 8](#design-rationale)

[5.1.1.2 Module Outputs 8](#module-outputs)

[5.1.2 Per: DualEcuIdnPer1 8](#per-dualecuidnper1)

[5.1.2.1 Design Rationale 8](#design-rationale-1)

[5.1.2.2 Store Module Inputs to Local copies
8](#store-module-inputs-to-local-copies)

[5.1.2.3 (Processing of function)……… 8](#processing-of-function)

[5.1.2.4 Store Local copy of outputs into Module Outputs
8](#store-local-copy-of-outputs-into-module-outputs)

[Appendix A S 10](#s)

[Appendix B Glossary 11](#glossary)

[Appendix C References 13](#references)

# Introduction

## Purpose

Module design document for Dual Ecu Identification

# \<Component Name\> & High-Level Description

Refer the Design.

# Design details of software module

## Graphical representation of DualEcuIdn

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/ES011A_DualEcuIdn_Impl/doc/mediax/media/image1.png"
style="width:3.54167in;height:2.3in" />

## Data Flow Diagram

### Component level DFD

N/A

### Function level DFD

N/A

# Constant Data Dictionary

## Program (fixed) Constants

### Embedded Constants

#### Local Constants

|                      |            |       |       |
|----------------------|------------|-------|-------|
| Constant Name        | Resolution | Units | Value |
| ECUIDNOTREAD_CNT_U08 | 1          | Cnt   | 0U    |
| Refer .m file        |            |       |       |

# Software Component Implementation

## Sub-Module Functions

The sub-module functions are grouped based on similar functionality that
needs to be executed in a given “State” of the system (refer States and
Modes). For a given module, the MDD will identify the type and number of
sub-modules required. The sub-module types are described below.

### Init: DualEcuIdnInit1

## Design Rationale

*Refer to FDD*

## Module Outputs

*Refer to FDD*

###  [section]

### Per: DualEcuIdnPer1

## Design Rationale

*None*

## Store Module Inputs to Local copies

*Refer to FDD*

## (Processing of function)………

*Refer to FDD0*

## Store Local copy of outputs into Module Outputs

*Refer to FDD*

> *Refer to FDD*

####### S

| **Abbreviation or Acronym** | **Description**           |
|-----------------------------|---------------------------|
| DFD                         | Design functional diagram |
| MDD                         | Module design Document    |

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

| **Ref. \#** | **Title**                                                                                                                                                     | **Version**                    |
|-------|-------------------------------------------------|-----------------|
| 1           | AUTOSAR Specification of Memory Mapping (Link:[AUTOSAR_SWS_MemoryMapping.pdf](http://www.autosar.org/download/R4.0/AUTOSAR_SWS_MemoryMapping.pdf))            | v1.3.0 R4.0 Rev 2              |
| 2           | MDD Guideline                                                                                                                                                 | EA4 01.00.01                   |
| 3           | [Software Naming Conventions.doc](http://misagweb01.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_fc55f/Software Naming Conventions 03x(In Work).doc)   | 1.0                            |
| 4           | [Software Design and Coding Standards.doc](http://eroom1.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_1a67a9/Software Design and Coding Standards.doc) | 2.1                            |
| 5           | FDD – ES011ADualEcuIdn                                                                                                                                        | See Synergy subproject version |

{% endraw %}