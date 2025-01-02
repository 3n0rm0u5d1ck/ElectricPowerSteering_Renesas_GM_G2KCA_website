---
layout: default
title: PwrUpSeq_MDD
nav_order: 2
parent: Component Implementation
---
{% raw %}
**Module Design Document**

**For**

**Power Up Sequence**

**VERSION: 3.0**

**DATE: 15-JULY-2016**

**Prepared By:**

**Software Group,**

**Nexteer Automotive,**

**Saginaw, MI, USA**

**Location:** The official version of this document is stored in the
Nexteer Configuration Management System.

**Revision History**

|             |                           |                        |             |              |
|------|----------------------|----------------------|----------|-------------|
| **Sl. No.** | **Description**           | **Author**             | **Version** | **Date**     |
| 1           | Initial Version           | Rijvi Ahmed            | 1.0         | 11-Apr-2015  |
| 2           | Updated for FDD ver 1.2.0 | Sankardu Varadapureddi | 2.0         | 13-Jan-2016  |
| 3           | Updated for FDD ver 1.4.0 | Rijvi Ahmed            | 3.0         | 15-July-2016 |

Table of Contents

[1 Abbrevations And Acronyms 5](#abbrevations-and-acronyms)

[2 References 6](#references)

[3 MDD pwrupseq & High-Level Description
7](#mdd-pwrupseq-high-level-description)

[4 Design details of software module
8](#design-details-of-software-module)

[4.1 Graphical representation of pwrupseq
8](#graphical-representation-of-pwrupseq)

[4.2 Data Flow Diagram 8](#data-flow-diagram)

[4.2.1 Module level DFD 8](#module-level-dfd)

[4.2.2 Sub-Module level DFD 8](#sub-module-level-dfd)

[4.3 COMPONENT FLOW DIAGRAM 8](#component-flow-diagram)

[5 Variable Data Dictionary 9](#variable-data-dictionary)

[5.1 User defined typedef definition/declaration
9](#user-defined-typedef-definitiondeclaration)

[5.2 Variable definition for enumerated types
9](#variable-definition-for-enumerated-types)

[6 Constant Data Dictionary 10](#constant-data-dictionary)

[6.1 Program(fixed) Constants 10](#programfixed-constants)

[6.1.1 Embedded Constants 10](#embedded-constants)

[6.1.1.1 Local 10](#local)

[6.1.1.2 Global 10](#global)

[6.1.2 Module specific Lookup Tables Constants
10](#module-specific-lookup-tables-constants)

[7 Software Module Implementation 11](#software-module-implementation)

[7.1 Sub-Module Functions 11](#sub-module-functions)

[7.2 Initialization Functions 11](#initialization-functions)

[7.2.1 PwrUpSeqInit1 11](#pwrupseqinit1)

[7.2.1.1 Design Rationale 11](#design-rationale)

[7.2.1.2 Module Outputs 11](#module-outputs)

[7.3 *None*PERIODIC FUNCTIONS 11](#noneperiodic-functions)

[7.3.1 Per: PwrUpSeqPer1 11](#per-pwrupseqper1)

[7.3.1.1 Design Rationale 11](#design-rationale-1)

[7.3.1.2 Store Module Inputs to Local copies
11](#store-module-inputs-to-local-copies)

[7.3.1.3 (Processing of function)……… 11](#processing-of-function)

[7.3.1.4 Store Local copy of outputs into Module Outputs
11](#store-local-copy-of-outputs-into-module-outputs)

[7.4 Interrupt Functions 11](#interrupt-functions)

[7.5 Serial Communication Functions 12](#serial-communication-functions)

[7.6 Local Function/Macro Definitions
12](#local-functionmacro-definitions)

[7.6.1 Local Function \#1 12](#local-function-1)

[7.6.1.1 Description 12](#description)

[7.7 GLObAL Function/Macro Definitions
12](#global-functionmacro-definitions)

[7.7.1 GLObAL Function \#1 12](#global-function-1)

[7.7.1.1 Description 12](#description-1)

[7.8 TRANSIENT FUNCTIONS 12](#transient-functions)

[8 Known Limitations With Design 13](#known-limitations-with-design)

[9 UNIT TEST CONSIDERATION 14](#unit-test-consideration)

[1 Appendix 15](#appendix)

# Abbrevations And Acronyms

|              |                                         |
|--------------|-----------------------------------------|
| Abbreviation | Description                             |
| DFD          | Design functional diagram               |
| MDD          | Module design Document                  |
|              | \<ADD more to the table if applicable\> |
|              |                                         |

# References

This section lists the title & version of all the documents that are
referred for development of this document

|         |                             |                                 |
|---------|-----------------------------|---------------------------------|
| Sr. No. | Title                       | Version                         |
| 1       | MDD Guidelines              | Process 04.02.01                |
| 2       | Software Naming Conventions | Process 04.02.01                |
| 3       | Software Coding Standards   | Process 04.02.01                |
| 4       | FDD – ES004A PwrUpSeq       | See synergy sub project version |

# MDD pwrupseq & High-Level Description

> None

# Design details of software module

## Graphical representation of pwrupseq

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/ES004A_PwrUpSeq_Impl/doc/mediax/media/image1.png"
style="width:2.58958in;height:2.03611in" />

## Data Flow Diagram

## Module level DFD

*N/A*

## Sub-Module level DFD

*N/A*

## COMPONENT FLOW DIAGRAM

*N/A*

# Variable Data Dictionary

## User defined typedef definition/declaration 

*\<This section documents any user types uniquely used for the
module.\>*

<table>
<colgroup>
<col style="width: 34%" />
<col style="width: 31%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Typedef Name</td>
<td>Element Name</td>
<td>User Defined Type</td>
<td><p>Legal Range</p>
<p>(min)</p></td>
<td><p>Legal Range</p>
<p>(max)</p></td>
</tr>
<tr class="even">
<td>N/A</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

## Variable definition for enumerated types

|           |              |       |
|-----------|--------------|-------|
| Enum Name | Element Name | Value |
|           |              |       |

# Constant Data Dictionary

## Program(fixed) Constants

## Embedded Constants

*\< All program specific constants will be defined in detail \>*

## Local

|               |            |       |       |
|---------------|------------|-------|-------|
| Constant Name | Resolution | Units | Value |
| N/A           |            |       |       |

## Global

*\<This section lists the global constants used by the module. For
details on global constants, refer to the Data Dictionary for the
application\>*

|               |
|---------------|
| Constant Name |
|               |

## Module specific Lookup Tables Constants

*\<(This is for lookup tables (arrays) with fixed values, same name as
other tables)\>*

|               |            |       |                  |
|---------------|------------|-------|------------------|
| Constant Name | Resolution | Value | Software Segment |
| N/A           |            |       |                  |

# Software Module Implementation

## Sub-Module Functions

*None*

## Initialization Functions

## PwrUpSeqInit1

## Design Rationale

*Refer FDD*

## Module Outputs

## *None*PERIODIC FUNCTIONS 

*(Note: For multiple periodic functions, insert new headers at the
“Header 2” level – subset of “7.3 Periodic Functions” and follow the
same sub-section design shown below). If none required, place the text
“None”)\>*

## Per: PwrUpSeqPer1

## Design Rationale

*None*

## Store Module Inputs to Local copies

*Refer to FDD*

## (Processing of function)………

*Refer to FDD*

## Store Local copy of outputs into Module Outputs

*Refer to FDD*

## 

## Interrupt Functions

*None*

## Serial Communication Functions

*None*

## Local Function/Macro Definitions

\<If these are numerous and defined in a separate source file then
reference the source file only.\>

## Local Function \#1

|                      |      |                               |                               |                               |
|--------------|------------------------------|----------|----------|----------|
| **Function Name**    | None | Type                          | Min                           | Max                           |
| **Arguments Passed** | None | \<Refer MDD guidelines\[1\]\> | \<Refer MDD guidelines\[1\]\> | \<Refer MDD guidelines\[1\]\> |
|                      |      |                               |                               |                               |
| **Return Value**     | None |                               |                               |                               |

## Description

N/A

## GLObAL Function/Macro Definitions

\<If these are numerous and defined in a separate source file then
reference the source file only.\>

## GLObAL Function \#1

|                      |      |                               |                               |                               |
|--------------|------------------------------|----------|----------|----------|
| **Function Name**    | None | Type                          | Min                           | Max                           |
| **Arguments Passed** | None | \<Refer MDD guidelines\[1\]\> | \<Refer MDD guidelines\[1\]\> | \<Refer MDD guidelines\[1\]\> |
|                      |      |                               |                               |                               |
| **Return Value**     | None |                               |                               |                               |

## Description

N/A

## TRANSIENT FUNCTIONS 

*None*

# Known Limitations With Design

# UNIT TEST CONSIDERATION

# Appendix

*None*

{% endraw %}