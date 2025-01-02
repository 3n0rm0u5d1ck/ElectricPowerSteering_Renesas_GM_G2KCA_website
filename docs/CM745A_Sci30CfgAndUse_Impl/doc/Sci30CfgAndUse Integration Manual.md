---
layout: default
title: Sci30CfgAndUse Integration Manual
nav_order: 1
parent: Component Implementation
---
{% raw %}
**Integration Manual**

**For**

**Sci30CfgAndUse**

**VERSION: 1**

**DATE: 01/19/17**

**Prepared By:**

**Software Group,**

**Nexteer Automotive,**

**Saginaw, MI, USA**

**Location:** The official version of this document is stored in the
Nexteer Configuration Management System.

**Revision History**

|             |                 |               |             |          |
|-------------|-----------------|---------------|-------------|----------|
| **Sl. No.** | **Description** | **Author**    | **Version** | **Date** |
| 1           | Initial version | Avinash James | 1           | 01/19/17 |

Table of Contents

[1 Abbrevations And Acronyms 4](#abbrevations-and-acronyms)

[2 References 5](#references)

[3 Dependencies 6](#dependencies)

[3.1 SWCs 6](#swcs)

[3.2 Global Functions(Non RTE) to be provided to Integration Project
6](#global-functionsnon-rte-to-be-provided-to-integration-project)

[4 Configuration REQUIREMeNTS 7](#configuration-requirements)

[4.1 Build Time Config 7](#build-time-config)

[4.2 Configuration Files to be provided by Integration Project
7](#configuration-files-to-be-provided-by-integration-project)

[4.3 Da Vinci Parameter Configuration Changes
7](#da-vinci-parameter-configuration-changes)

[4.4 DaVinci Interrupt Configuration Changes
7](#__RefHeading___Toc459966917)

[4.5 Manual Configuration Changes 7](#manual-configuration-changes)

[5 Integration DATAFLOW REQUIREMENTS
8](#integration-dataflow-requirements)

[5.1 Required Global Data Inputs 8](#required-global-data-inputs)

[5.2 Required Global Data Outputs 8](#required-global-data-outputs)

[5.3 Specific Include Path present 8](#specific-include-path-present)

[6 Runnable Scheduling 9](#runnable-scheduling)

[7 Memory Map REQUIREMENTS 10](#memory-map-requirements)

[7.1 Mapping 10](#mapping)

[7.2 Usage 10](#usage)

[7.3 NvM Blocks 10](#nvm-blocks)

[8 Compiler Settings 11](#compiler-settings)

[8.1 Preprocessor MACRO 11](#preprocessor-macro)

[8.2 Optimization Settings 11](#optimization-settings)

[9 Appendix 12](#appendix)

# Abbrevations And Acronyms

|                  |                            |
|------------------|----------------------------|
| **Abbreviation** | **Description**            |
| DFD              | Design functional diagram  |
| MDD              | Module design Document     |
| FDD              | Functional Design Document |
|                  |                            |
|                  |                            |

# References

This section lists the title & version of all the documents that are
referred for development of this document

|             |                             |                                |
|-------------|-----------------------------|--------------------------------|
| **Sr. No.** | **Title**                   | **Version**                    |
| 1           | FDD – CM475A Sci30CfgAndUse | See Synergy subproject version |
| 2           | Software Naming Conventions | Process 04.02.01               |
| 3           | Software Coding Standards   | Process 04.02.01               |
|             |                             |                                |
|             |                             |                                |

# Dependencies

## SWCs

|                    |                                      |
|--------------------|--------------------------------------|
| **Module**         | **Required Feature**                 |
| **AR350A ImcArbn** | All the IMC signal group definitions |
|                    |                                      |

Note : Referencing the external components should be avoided in most
cases. Only in unavoidable circumstance external components should be
referred. Developer should track the references.

## Global Functions(Non RTE) to be provided to Integration Project

IninSciDtsChMstReg - To be defined as a trusted function as the DTS
Channel master registers need to be configured in the supervisor mode.

# Configuration REQUIREMeNTS

## Build Time Config

|             |           |     |
|-------------|-----------|-----|
| **Modules** | **Notes** |     |
| **None**    |           |     |

## Configuration Files to be provided by Integration Project

## Da Vinci Parameter Configuration Changes

|               |           |         |
|---------------|-----------|---------|
| **Parameter** | **Notes** | **SWC** |
|               |           |         |

## DaVinci Interrupt Configuration Changes

|              |            |                         |           |
|--------------|------------|-------------------------|-----------|
| **ISR Name** | **VIM \#** | **Priority Dependency** | **Notes** |
|              |            |                         |           |

## Manual Configuration Changes

|              |           |         |
|--------------|-----------|---------|
| **Constant** | **Notes** | **SWC** |
| **None**     |           |         |

## Exclusive Areas

<table>
<colgroup>
<col style="width: 39%" />
<col style="width: 47%" />
<col style="width: 12%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Constant</strong></td>
<td><strong>Notes</strong></td>
<td><strong>SWC</strong></td>
</tr>
<tr class="even">
<td><strong>ExclsvAr1SciDrvrTxRxBuf</strong></td>
<td><p>Exclusive area needs to protect access to Transmit and Receive
buffers from asynchronous updates by server runnables and periodic
updates by tasks.</p>
<p>Integrator needs to verify if client calls to server runnables can
interrupt periodics and set up exclusive area to properly protect
access. If exclusive area is needed, at minimum it must disable OS Task
scheduling (It is assumed that all clients call occurs in OS
Tasks).</p></td>
<td></td>
</tr>
</tbody>
</table>

# Integration DATAFLOW REQUIREMENTS

## Required Global Data Inputs

None

## Required Global Data Outputs

None

## Specific Include Path present

Yes

# Runnable Scheduling 

This section specifies the required runnable scheduling.

|                         |                             |                    |
|-------------------------|-----------------------------|--------------------|
| **Init**                | **Scheduling Requirements** | **Trigger**        |
| **Sci30CfgAndUseInit1** | None                        | Once At Init (RTE) |
|                         |                             |                    |

|                        |                             |             |
|------------------------|-----------------------------|-------------|
| **Runnable**           | **Scheduling Requirements** | **Trigger** |
| **Sci30CfgAndUsePer1** | None                        | 2ms(RTE)    |
| **Sci30CfgAndUsePer2** | None                        | 2ms(RTE)    |
| **Sci30CfgAndUsePer3** | None                        | 10ms(RTE)   |
| **Sci30CfgAndUsePer4** | None                        | 100ms(RTE)  |

# Memory Map REQUIREMENTS

## Mapping

|                                                        |              |           |
|----------------------------------------|----------------|----------------|
| **Memory Section**                                     | **Contents** | **Notes** |
| **CDD_Sci30CfgAndUse_START_SEC_CODE**                  |              |           |
| **CDD_Sci30CfgAndUse_START_SEC_VAR_INIT_128**          |              |           |
| **CDD_Sci30CfgAndUse_DmaWrite_START_SEC_VAR_INIT_128** |              |           |

\* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as
specified in the AUTOSAR Memory Mapping requirements.

## Usage

|             |         |         |
|-------------|---------|---------|
| **Feature** | **RAM** | **ROM** |
|             |         |         |

Table 1: ARM Cortex R4 Memory Usage

## NvM Blocks

None

# Compiler Settings

##  Preprocessor MACRO

None

## Optimization Settings

None

# Appendix

{% endraw %}