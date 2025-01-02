---
layout: default
title: SnsrMeasStrt_IntegrationManual
nav_order: 1
parent: Component Implementation
---
{% raw %}
**Integration Manual**

**For**

**SnsrMeasStrt**

**VERSION: 1.0**

**DATE: 18-NOV-2016**

**Prepared By:**

**Shruthi Raghavan**

**Nexteer Automotive,**

**Saginaw, MI, USA**

**Location:** The official version of this document is stored in the
Nexteer Configuration Management System.

**Revision History**

|             |                 |                  |             |          |
|-------------|-----------------|------------------|-------------|----------|
| **Sl. No.** | **Description** | **Author**       | **Version** | **Date** |
| 1           | Initial version | Shruthi Raghavan | 1.0         | 11/18/16 |

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
7](#__RefHeading___Toc467242760)

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

|                  |                           |
|------------------|---------------------------|
| **Abbreviation** | **Description**           |
| DFD              | Design functional diagram |
| MDD              | Module design Document    |

# References

This section lists the title & version of all the documents that are
referred for development of this document

|             |                                      |                                    |
|----------|----------------------------------------------|-----------------|
| **Sr. No.** | **Title**                            | **Version**                        |
| 1           | EA3 Software Naming Conventions      | 2.0                                |
| 2           | Software Design and Coding standards | 2.1                                |
| 3           | FDD CM410B                           | Refer Design Subproject in Synergy |

# Dependencies

## SWCs

<table>
<colgroup>
<col style="width: 30%" />
<col style="width: 69%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Module</strong></td>
<td><strong>Required Feature</strong></td>
</tr>
<tr class="even">
<td><strong>CM650B<br />
HwTq0Meas</strong></td>
<td>Server Runnable HwTq0MeasTrigStrt_Oper is called from this
function</td>
</tr>
<tr class="odd">
<td><strong>CM660B<br />
HwTq1Meas</strong></td>
<td>Server Runnable HwTq1MeasTrigStrt_Oper is called from this
function</td>
</tr>
</tbody>
</table>

## Global Functions(Non RTE) to be provided to Integration Project

None

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
| **None**      |           |         |

## DaVinci Interrupt Configuration Changes

|              |            |                         |           |
|--------------|------------|-------------------------|-----------|
| **ISR Name** | **VIM \#** | **Priority Dependency** | **Notes** |
| **None**     |            |                         |           |

## Manual Configuration Changes

|              |           |         |
|--------------|-----------|---------|
| **Constant** | **Notes** | **SWC** |
| **None**     |           |         |

# Integration DATAFLOW REQUIREMENTS

## Required Global Data Inputs

Refer FDD

## Required Global Data Outputs

Refer FDD

## Specific Include Path present

> No

# Runnable Scheduling 

This section specifies the required runnable scheduling.

|                       |                             |                |
|-----------------------|-----------------------------|----------------|
| **Init**              | **Scheduling Requirements** | **Trigger**    |
| **SnsrMeasStrtInit1** | **None**                    | **RTE (Init)** |

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 54%" />
<col style="width: 20%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Runnable</strong></td>
<td><strong>Scheduling Requirements</strong></td>
<td><strong>Trigger</strong></td>
</tr>
<tr class="even">
<td><strong>SnsrMeasStrtPer1</strong></td>
<td><strong>None(Recommended to schedule before HwTq measurement 2ms
periodic)</strong></td>
<td><strong>RTE (2 ms)</strong></td>
</tr>
<tr class="odd">
<td><strong>SnsrMeasStrtIrq</strong></td>
<td><strong>Interupt triggered</strong></td>
<td><p><strong>Interrupt</strong></p>
<p><strong>OSTM1 (interrupt channel 75)</strong></p></td>
</tr>
</tbody>
</table>

**Refer this design for interrupt priority. ISR needs to be excuted in
the same application region as HwTqMeas components.**

# Memory Map REQUIREMENTS

## Mapping

|                    |              |           |
|--------------------|--------------|-----------|
| **Memory Section** | **Contents** | **Notes** |
| **None**           |              |           |
|                    |              |           |

\* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as
specified in the AUTOSAR Memory Mapping requirements.

## Usage

|             |         |         |
|-------------|---------|---------|
| **Feature** | **RAM** | **ROM** |
| **None**    |         |         |

Table 1: ARM Cortex R4 Memory Usage

## NvM Blocks

None

# Compiler Settings

##  Preprocessor MACRO

None

## Optimization Settings

None

# Appendix

None

{% endraw %}