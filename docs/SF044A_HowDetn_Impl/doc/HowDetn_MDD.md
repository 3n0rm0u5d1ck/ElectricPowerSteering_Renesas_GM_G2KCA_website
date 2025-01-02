---
layout: default
title: HowDetn_MDD
nav_order: 2
parent: Component Implementation
---
{% raw %}
**Module Design Document**

**For**

**HowDetn**

**Jan 29, 2016**

**Prepared For:**

**Software Engineering**

**Nexteer Automotive,**

**Saginaw, MI, USA**

**Prepared By: Basavaraja Ganeshappa**

**Software Group,**

**Nexteer Automotive,**

**Saginaw, MI, USA  
<u>Change History</u>**

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 28%" />
<col style="width: 18%" />
<col style="width: 19%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Description</strong></td>
<td><strong>Author</strong></td>
<td><strong>Version</strong></td>
<td><strong>Date</strong></td>
</tr>
<tr class="even">
<td>Initial Version</td>
<td>BG</td>
<td>1</td>
<td>01/29/2016</td>
</tr>
<tr class="odd">
<td><p>Server runnables, Interrupt functions, Module Internal (Local)
Functions, GLOBAL Function/Macro Definitions - sub portions were
removed</p>
<p>Footer template updated to EA4 01.00.01</p></td>
<td>BG</td>
<td>2</td>
<td>02/15/2016</td>
</tr>
</tbody>
</table>

**<u>Table of Contents</u>**

[1 Introduction [5](#introduction)](#introduction)

[1.1 Purpose [5](#purpose)](#purpose)

[1.2 Scope [5](#scope)](#scope)

[2 HowDetn High-Level Description
[6](#howdetn-high-level-description)](#howdetn-high-level-description)

[2.1 Graphical representation of HowDetn
[6](#graphical-representation-of-howdetn)](#graphical-representation-of-howdetn)

[2.2 Data Flow Diagram [7](#data-flow-diagram)](#data-flow-diagram)

[2.2.1 Component level DFD
[7](#component-level-dfd)](#component-level-dfd)

[2.2.2 Function level DFD [7](#function-level-dfd)](#function-level-dfd)

[3 Constant Data Dictionary
[8](#constant-data-dictionary)](#constant-data-dictionary)

[3.1 Program (fixed) Constants
[8](#program-fixed-constants)](#program-fixed-constants)

[3.1.1 Embedded Constants [8](#embedded-constants)](#embedded-constants)

[4 Software Component Implementation
[9](#software-component-implementation)](#software-component-implementation)

[4.1 Sub-Module Functions
[9](#sub-module-functions)](#sub-module-functions)

[4.1.1 Init: HowDetnInit1 [9](#init-howdetninit1)](#init-howdetninit1)

[4.1.1.1 Design Rationale [9](#design-rationale)](#design-rationale)

[4.1.1.2 Module Outputs [9](#module-outputs)](#module-outputs)

[4.1.2 Per: HowDetnPer1 [9](#per-howdetnper1)](#per-howdetnper1)

[4.1.2.1 Design Rationale [9](#design-rationale-1)](#design-rationale-1)

[4.1.2.2 Store Module Inputs to Local copies
[9](#store-module-inputs-to-local-copies)](#store-module-inputs-to-local-copies)

[4.1.2.3 (Processing of function)………
[9](#processing-of-function)](#processing-of-function)

[4.1.2.4 Store Local copy of outputs into Module Outputs
[9](#store-local-copy-of-outputs-into-module-outputs)](#store-local-copy-of-outputs-into-module-outputs)

[4.2 Server Runables [9](#server-runables)](#server-runables)

[4.3 Interrupt Functions
[9](#interrupt-functions)](#interrupt-functions)

[4.4 Module Internal (Local) Functions
[9](#module-internal-local-functions)](#module-internal-local-functions)

[4.5 GLOBAL Function/Macro Definitions
[9](#global-functionmacro-definitions)](#global-functionmacro-definitions)

[5 Known Limitations with Design
[10](#known-limitations-with-design)](#known-limitations-with-design)

[6 UNIT TEST CONSIDERATION
[11](#unit-test-consideration)](#unit-test-consideration)

[Appendix A Abbreviations and Acronyms
[12](#abbreviations-and-acronyms)](#abbreviations-and-acronyms)

[Appendix B Glossary [13](#glossary)](#glossary)

[Appendix C References [14](#references)](#references)

# Introduction

## Purpose

The purpose of this document is to document the module level design for
a HowDetn software module which is the part of the software related to
Nexteer’s Electrical Steering Systems product line.

## Scope

Scope of the document is to capture the software implementation details
of HowDetn Module.

# HowDetn High-Level Description

> Determination of a continuous valued estimate that represents the
> likelihood that a driver's hands are on the steering wheel (value =1)
> or off the steering wheel (value=0). A discrete value corresponding to
> the confidence of the estimate is also specified Design details of
> software module

## Graphical representation of HowDetn

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/SF044A_HowDetn_Impl/doc/mediax/media/image1.png"
style="width:4.03472in;height:5.64375in" />

## Data Flow Diagram

Refer to FDD

### Component level DFD

Refer to FDD

### Function level DFD

Refer to FDD

# Constant Data Dictionary

## Program (fixed) Constants

### Embedded Constants

#### Local Constants

| Constant Name                   | Resolution | Units | Value |
|---------------------------------|------------|-------|-------|
| Refer SF044A_HowDetn_DataDict.m | NA         | NA    | NA    |

# Software Component Implementation

Refer FDD

## Sub-Module Functions

## Init: HowDetnInit1

## Design Rationale

*Refer FDD*

## Module Outputs

*Refer FDD*

## Per: HowDetnPer1

## Design Rationale

*Refer FDD*

## Store Module Inputs to Local copies

*Refer FDD*

##  (Processing of function)………

*Refer FDD*

## Store Local copy of outputs into Module Outputs

*Refer FDD*

## Server Runables 

*None*

## Interrupt Functions

*None*

## Module Internal (Local) Functions

*None*

## GLOBAL Function/Macro Definitions

*None*

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

| **Ref. \#** | **Title**                                                                                                                                                             | **Version**       |
|-------|-------------------------------------------------|-----------------|
| 1           | AUTOSAR Specification of Memory Mapping (Link:[AUTOSAR_SWS_MemoryMapping.pdf](http://www.autosar.org/download/R4.0/AUTOSAR_SWS_MemoryMapping.pdf))                    | v1.3.0 R4.0 Rev 2 |
| 2           | MDD Guideline                                                                                                                                                         | EA4 01.00.01      |
| 3           | [Software Naming Conventions.doc](http://misagweb01.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_fc55f/Software%20Naming%20Conventions%2003x(In%20Work).doc)   | 2.0               |
| 4           | [Software Design and Coding Standards.doc](http://eroom1.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_1a67a9/Software%20Design%20and%20Coding%20Standards.doc) | 2.1               |

{% endraw %}