---
layout: default
title: SnsrMeasStrt_MDD
nav_order: 2
parent: Component Implementation
---
{% raw %}
**Module Design Document**

**For**

**SnsrMeasStrt**

**Nov 18, 2016**

**Prepared For:**

**Software Engineering**

**Nexteer Automotive,**

**Saginaw, MI, USA**

**Prepared By:**

**Shruthi Raghavan,**

**Nexteer Automotive,**

**Saginaw, MI, USA  
<u>Change History</u>**

|                 |                  |              |          |
|-----------------|------------------|--------------|----------|
| **Description** | **Author**       | **Version**  | **Date** |
| Initial Version | Shruthi Raghavan | EA4 01.00.01 | 11/18/16 |

**  
**

**<u>Table of Contents</u>**

1 Introduction [4](#introduction)

[1.1 Purpose [4](#purpose)](#purpose)

[2 SnsrMeasStrt & High-Level Description
[5](#snsrmeasstrt-high-level-description)](#snsrmeasstrt-high-level-description)

[3 Design details of software module
[6](#design-details-of-software-module)](#design-details-of-software-module)

[3.1 Graphical representation of SnsrMeasStrt
[6](#graphical-representation-of-snsrmeasstrt)](#graphical-representation-of-snsrmeasstrt)

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

[5.1.1 Init: SnsrMeasStrt_Init1
[8](#init-snsrmeasstrt_init1)](#init-snsrmeasstrt_init1)

[5.1.1.1 Design Rationale [8](#design-rationale)](#design-rationale)

[5.1.1.2 Module Outputs [8](#module-outputs)](#module-outputs)

[5.1.2 Per: SnsrMeasStrt_Per1
[8](#per-snsrmeasstrt_per1)](#per-snsrmeasstrt_per1)

[5.1.2.1 Design Rationale [8](#design-rationale-1)](#design-rationale-1)

[5.1.2.2 Processing of function
[8](#processing-of-function)](#processing-of-function)

[5.2 Server Runnables [8](#server-runnables)](#server-runnables)

[5.3 Interrupt Functions
[9](#interrupt-functions)](#interrupt-functions)

[5.3.1 SnsrMeasStrtIrq [9](#snsrmeasstrtirq)](#snsrmeasstrtirq)

[5.3.1.1 Design Rationale [9](#design-rationale-2)](#design-rationale-2)

[5.3.1.2 Processing of the ISR function
[9](#processing-of-the-isr-function)](#processing-of-the-isr-function)

[5.4 Module Internal (Local) Functions
[9](#module-internal-local-functions)](#module-internal-local-functions)

[5.5 GLOBAL Function/Macro Definitions
[9](#global-functionmacro-definitions)](#global-functionmacro-definitions)

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

Module Design Document for CM410B SnsrMeasStrt

# SnsrMeasStrt & High-Level Description

> Torque Leg is critical factor in Feel issue. In order to minimize lag,
> it is required to synchronize trigger and time to read torque data
> should be just in time, so there will be minimum lag.

# Design details of software module

## Graphical representation of SnsrMeasStrt

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CM410B_SnsrMeasStrt_Impl/doc/mediax/media/image1.png"
style="width:2.80383in;height:1.33221in" />

## Data Flow Diagram

Refer FDD

### Component level DFD

Refer FDD

### Function level DFD

Refer FDD

# Constant Data Dictionary

## Program (fixed) Constants

### Embedded Constants

#### Local Constants

Refer to DataDict.m file for rest of the constants.

| Constant Name | Resolution | Units | Value |
|---------------|------------|-------|-------|
|               |            |       |       |

# Software Component Implementation

## Sub-Module Functions

## Init: SnsrMeasStrt_Init1

## Design Rationale

> OSTM1 Timer has choosen for timing synchronization, because it was
> close to tied with OSTM0, same clock for accuracy Purpose, but TAUJ or
> TAUD any real time timer mechanism would work. Initialize OS Timer
> registers. Refer to CM410B_SnsrMeasStrt_PeripheralCfg.xlsx in the
> design package to see the specific register configurations. Unmask the
> OSTM1 EI-level mask able interrupt according to the instructions in
> Model for which both Os.h and osekext.h are required.

## Module Outputs

> Refer FDD

## Per: SnsrMeasStrt_Per1

## Design Rationale

> OSTM0 is a free running counter for 2ms. OSTM0CNT is used to trigger
> torque measure sensor reads with a calibrated trigger delay to start
> this read (by setting a count value to OSTM1CMP for triggering its
> interval timer mode interrupt) before the periodic is called again.

##  Processing of function

> Refer to FDD

## Server Runnables

None

## Interrupt Functions

## SnsrMeasStrtIrq

## Design Rationale

> PIMs belong to the RTE and so the corresponding header file is
> included in this file for the ISR to have TqMsgTrigCnt defined in
> scope. Client calls to Hw0TqMeas & Hw1TqMeas server runnables are
> possible from ISR because they are implemented as non-RTE also in the
> respective components.

## Processing of the ISR function

> ISR calls the HwTq0MeasTrigStrt_Oper, HwTq1MeasTrigStrt_Oper server
> runnables from CM650B and CM660B respectively. Each of these in turn
> triggers the TqSENT measurement from the corresponding Handwheel
> Torque Sensor.

Only client calls to server runnables are part of this ISR. Increments a
PIM to capture how many timer triggers happen.

## Module Internal (Local) Functions

> None

## GLOBAL Function/Macro Definitions

> None

# Known Limitations with Design

**ISR needs to execute in the same application region of the Torque
Measurement Components.**

**DataDict.m** file has known issues:

1.  Context of ISR is wrong

2.  The register given as input is OSTM0CMP whereas the one need is
    OSTM0CNT.

> An anomaly has been submitted to fix this.

# UNIT TEST CONSIDERATION

Overflow for the variable **Rte_Pim_TqMsgTrigCnt** is intentional as
this is used as a rolling counter.

####### Abbreviations and Acronyms

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

| **Ref. \#** | **Title**                                                                                                                                                               | **Version**                           |
|-------|-------------------------------------------------|-----------------|
| 1           | AUTOSAR Specification of Memory Mapping (Link:[AUTOSAR_SWS_MemoryMapping.pdf](http://www.autosar.org/download/R4.0/AUTOSAR_SWS_MemoryMapping.pdf))                      | v1.3.0 R4.0 Rev 2                     |
| 2           | MDD Guideline                                                                                                                                                           | EA4 01.00.01                          |
| 3           | EA3 [Software Naming Conventions.doc](http://misagweb01.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_fc55f/Software%20Naming%20Conventions%2003x(In%20Work).doc) | 2.0                                   |
| 4           | [Software Design and Coding Standards.doc](http://eroom1.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_1a67a9/Software%20Design%20and%20Coding%20Standards.doc)   | 2.1                                   |
| 5           | FDD CM410B                                                                                                                                                              | Refer to Design Subproject in Synergy |

{% endraw %}