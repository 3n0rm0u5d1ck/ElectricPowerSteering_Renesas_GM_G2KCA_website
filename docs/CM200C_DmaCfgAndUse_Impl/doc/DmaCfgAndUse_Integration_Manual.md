---
layout: default
title: DmaCfgAndUse_Integration_Manual
nav_order: 2
parent: Component Implementation
---
{% raw %}
**Integration Manual**

**For**

**DmaCfgAndUse**

**VERSION:** **2.0**

**DATE:** **10-Dec-2016**

**Prepared By:**

**Avinash James**

**Location:** The official version of this document is stored in the
Nexteer Configuration Management System.

**Revision History**

|                                                  |               |             |             |
|---------------------|---------------------|---------|----------------------|
| **Description**                                  | **Author**    | **Version** | **Date**    |
| Initial version                                  | Avinash James | 1.0         | 08-Nov-2016 |
| Corrected the micro diag error injection defines | Avinash James | 2.0         | 10-Dec-2016 |

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
7](#__RefHeading___Toc466377987)

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

|                  |                                         |
|------------------|-----------------------------------------|
| **Abbreviation** | **Description**                         |
| DFD              | Design functional diagram               |
| MDD              | Module design Document                  |
|                  | \<ADD more to the table if applicable\> |
|                  |                                         |
|                  |                                         |

# References

This section lists the title & version of all the documents that are
referred for development of this document

|             |                                 |                                                                          |
|----------|----------------------------------------------|-----------------|
| **Sr. No.** | **Title**                       | **Version**                                                              |
| \<1\>       | \<MDD Guidelines\>              | Software Engineering Process 04.00.00                                    |
| \<2\>       | \<Software Naming Conventions\> | Software Engineering Process 04.00.00 and working EA4 naming conventions |
| \<3\>       | \<Coding standards\>            | Software Engineering Process 04.00.00                                    |
| \<4\>       | \<FDD \>                        | See Synergy subproject version                                           |
|             | \<Add if more available\>       |                                                                          |

# Dependencies

## SWCs

|                      |                                                                                                                                            |
|-----------------------|-------------------------------------------------|
| **Module**           | **Required Feature**                                                                                                                       |
| **MotCtrlMgr**       | Generated struct type declarations for the Motor Control loop / RTE interface data; macros for access of Motor Control loop data           |
| **GuardCfgAndDiagc** | PEG and PBG settings to allow DMA transfers; CM200C_DmaCfgAndUse_Impl_1.0.0 or newer requires CM107A_GuardCfgAndDiagc_Impl_1.0.0 or newer. |

Note : Referencing the external components should be avoided in most
cases. Only in unavoidable circumstance external components should be
referred. Developer should track the references.

## Global Functions(Non RTE) to be provided to Integration Project

void DmaRegInin (void) - needs to be a trusted function

void InjDmaErr(void) - Inject DAM errors needed for error injection
build

void InjMotCtrlTo2MilliSecTrfErr (void) - Inject NTC 2B Errors needed
for error injection build

# Configuration REQUIREMeNTS

## Build Time Config

<table style="width:100%;">
<colgroup>
<col style="width: 36%" />
<col style="width: 53%" />
<col style="width: 9%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Modules</strong></td>
<td><strong>Notes</strong></td>
<td></td>
</tr>
<tr class="even">
<td><strong>MCUDIAGCERRINJ</strong></td>
<td><p>STD_OFF for other builds</p>
<p>STD_ON for uDiag test builds</p></td>
<td></td>
</tr>
</tbody>
</table>

## Configuration Files to be provided by Integration Project

None

## Da Vinci Parameter Configuration Changes

|                                             |           |         |
|---------------------------------------------|-----------|---------|
| **Parameter**                               | **Notes** | **SWC** |
| **\<Configurator Changes for parameters\>** |           |         |

## DaVinci Interrupt Configuration Changes

|                                             |            |                         |           |
|-------------|--------|---------------------------|-------------------------|
| **ISR Name**                                | **VIM \#** | **Priority Dependency** | **Notes** |
| **\<Configurator Changes for Interrupts\>** |            |                         |           |

## Manual Configuration Changes

|                                          |           |         |
|------------------------------------------|-----------|---------|
| **Constant**                             | **Notes** | **SWC** |
| **\<Additional configuration changes\>** |           |         |

# Integration DATAFLOW REQUIREMENTS

## Required Global Data Inputs

See DataDict.m file

## Required Global Data Outputs

See DataDict.m file

## Specific Include Path present

Yes

# Runnable Scheduling 

This section specifies the required runnable scheduling.

|                       |                             |             |
|-----------------------|-----------------------------|-------------|
| **Init**              | **Scheduling Requirements** | **Trigger** |
| **DmaCfgAndUseInit1** | None                        | RTE Init    |

|                                          |                                                                                                                            |                                                                        |
|----------------------------|--------------|------------------------------|
| **Runnable**                             | **Scheduling Requirements**                                                                                                | **Trigger**                                                            |
| **DmaCfgAndUsePer1**                     | Per FDD:” - Execution order of "DmaCfgAndUsePer1" shall schedule start of forward path (as soon as possible start of 2ms)” | RTE 2 ms                                                               |
| **DmaWaitForMotCtrlTo2MilliSecTrf_Oper** | N/A                                                                                                                        | On invocation of DmaWaitForMotCtrlTo2MilliSecTrf.Oper                  |
| **DmaEna2MilliSecToMotCtrlTrf_Oper**     | N/A                                                                                                                        | On invocation of DmaEna2MilliSecToMotCtrlTrf.Oper                      |
| **InjDmaErr**                            | N/A                                                                                                                        | On invocation of InjDmaErr only when **MCUDIAGCERRINJ is STD_ON**      |
| **InjMcuDiagcErr**                       | N/A                                                                                                                        | On invocation of InjMcuDiagcErr only when **MCUDIAGCERRINJ is STD_ON** |

# Memory Map REQUIREMENTS

## Mapping

|                                     |              |           |
|-------------------------------------|--------------|-----------|
| **Memory Section**                  | **Contents** | **Notes** |
| **CDD_DmaCfgAndUse_START_SEC_CODE** |              |           |
|                                     |              |           |

\* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as
specified in the AUTOSAR Memory Mapping requirements.

## Usage

|                            |         |         |
|----------------------------|---------|---------|
| **Feature**                | **RAM** | **ROM** |
| **\<Memmap usuage info\>** |         |         |

Table 1: ARM Cortex R4 Memory Usage

## NvM Blocks

None

# Compiler Settings

##  Preprocessor MACRO

\<Define all the preprocessor Macros needed and conditions when
needed\>.

## Optimization Settings

\<Define Optimization levels that are needed and conditions when
needed\>.

# Appendix

*\<This section is for appendix\>*

{% endraw %}