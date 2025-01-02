---
layout: default
title: Rtn_Module Design Document
nav_order: 4
parent: Component Implementation
---
{% raw %}
**Module Design Document**

**For**

**Return**

**June 30, 2015**

**Prepared For:**

**Software Engineering**

**Nexteer Automotive,**

**Saginaw, MI, USA**

**Prepared By:**

**Spandana Balani  
<u>Change History</u>**

|                 |            |             |             |     |
|-----------------|------------|-------------|-------------|-----|
| **Description** | **Author** | **Version** | **Date**    |     |
| Initial Version | SB         | 1           | 30-Jun-2015 |     |

**<u>Table of Contents</u>**

[1 Introduction [3](#introduction)](#introduction)

[1.1 Purpose [3](#purpose)](#purpose)

[1.2 Scope [3](#scope)](#scope)

[2 \<Component Name\> & High-Level Description
[3](#rtn-high-level-description)](#rtn-high-level-description)

[3 Design details of software module
[3](#design-details-of-software-module)](#design-details-of-software-module)

[3.1 Graphical representation of \<Component Name\>
[3](#graphical-representation-of-rtn)](#graphical-representation-of-rtn)

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

[5.1.1 Sub-Module Functions
[3](#sub-module-functions)](#sub-module-functions)

[5.1.2 Interrupt Service Routines
[3](#interrupt-service-routines)](#interrupt-service-routines)

[5.1.3 Server Runnable Functions
[3](#server-runnable-functions)](#server-runnable-functions)

[5.1.4 Module Internal (Local) Functions
[3](#module-internal-local-functions)](#module-internal-local-functions)

[5.1.5 Transition Functions
[3](#transition-functions)](#transition-functions)

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

## Scope

# Rtn High-Level Description

Refer to FDD

# Design details of software module

## Graphical representation of Rtn

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/SF002A_Rtn_Impl/doc/mediax/media/image1.png"
style="width:3.375in;height:6.68333in" />

## Data Flow Diagram

### Component level DFD

Refer to FDD

### Function level DFD

Refer to FDD

# Constant Data Dictionary

## Program (fixed) Constants

### Embedded Constants

#### Local Constants

None

# Software Component Implementation

### Sub-Module Functions

#### Initialization sub-module {\_Init()}

None

#### Periodic sub-module RtnPer1

Design Rationale - *Fault Injection client call is conditional compiled
based on “FLTINJENA” build constant.*

### Interrupt Service Routines

None

### Server Runnable Functions

None

### Module Internal (Local) Functions

None

### Transition Functions

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

| **Ref. \#** | **Title**                                                                                                                                                             | **Version**                     |
|-------|-------------------------------------------------|-----------------|
| 1           | AUTOSAR Specification of Memory Mapping (Link:[AUTOSAR_SWS_MemoryMapping.pdf](http://www.autosar.org/download/R4.0/AUTOSAR_SWS_MemoryMapping.pdf))                    | v1.3.0 R4.0 Rev 2               |
| 2           | MDD Guideline                                                                                                                                                         | EA4 01.00.00                    |
| 3           | [Software Naming Conventions.doc](http://misagweb01.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_fc55f/Software%20Naming%20Conventions%2003x(In%20Work).doc)   | 2.0                             |
| 4           | [Software Design and Coding Standards.doc](http://eroom1.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_1a67a9/Software%20Design%20and%20Coding%20Standards.doc) | 2.1                             |
| 5           | FDD – SF002A_Rtn_Design                                                                                                                                               | See Synergy Sub project version |

{% endraw %}