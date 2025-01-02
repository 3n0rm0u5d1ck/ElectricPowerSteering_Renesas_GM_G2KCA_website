---
layout: default
title: ImcArbn_IntegrationManual
nav_order: 1
parent: Component Implementation
---
{% raw %}
**Integration Manual**

**For**

**Imc Arbitration**

**VERSION: 1.0**

**DATE: 02-Feb-2017**

**Prepared By:**

**Software Group,**

**Nexteer Automotive,**

**Saginaw, MI, USA**

**Revision History**

|             |                                                                                    |                      |             |             |
|-----|--------------------|--------------------|---------|--------------------|
| **Sl. No.** | **Description**                                                                    | **Author**           | **Version** | **Date**    |
| 1           | Initial version                                                                    | Akilan Rathakrishnan | 1.0         | 17-Jan-2017 |
| 2           | Added note about potential compilation issue in case of no signal group configured | Akilan Rathakrishnan | 2.0         | 02-Feb-2017 |

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
7](#da-vinci-developer-notes)

[4.4 DaVinci Interrupt Configuration Changes
7](#davinci-interrupt-configuration-changes)

[4.5 Manual Configuration Changes 8](#manual-configuration-changes)

[5 Integration DATAFLOW REQUIREMENTS
9](#integration-dataflow-requirements)

[5.1 Required Global Data Inputs 9](#required-global-data-inputs)

[5.2 Required Global Data Outputs 9](#required-global-data-outputs)

[5.3 Specific Include Path present 9](#specific-include-path-present)

[6 Runnable Scheduling 10](#runnable-scheduling)

[7 Memory Map REQUIREMENTS 12](#memory-map-requirements)

[7.1 Mapping 12](#mapping)

[7.2 Usage 12](#usage)

[7.3 Non RTE NvM Blocks 12](#non-rte-nvm-blocks)

[7.4 RTE NvM Blocks 12](#rte-nvm-blocks)

[8 Compiler Settings 13](#compiler-settings)

[8.1 Preprocessor MACRO 13](#preprocessor-macro)

[8.2 Optimization Settings 13](#optimization-settings)

[9 Appendix 14](#appendix)

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

|             |                                   |                                  |
|----------|----------------------------------------------|-----------------|
| **Sr. No.** | **Title**                         | **Version**                      |
| \<1\>       | \<FDD - \<AR350A_ImcArbn_Design\> | Refer Synergy subproject version |
|             |                                   |                                  |
|             |                                   |                                  |
|             |                                   |                                  |
|             |                                   |                                  |

# Dependencies

## SWCs

|            |                      |
|------------|----------------------|
| **Module** | **Required Feature** |
| **None**   | N/A                  |

Note : Referencing the external components should be avoided in most
cases. Only in unavoidable circumstance external components should be
referred. Developer should track the references.

## Global Functions(Non RTE) to be provided to Integration Project

None

# Configuration REQUIREMeNTS

## Build Time Config

|             |           |     |
|-------------|-----------|-----|
| **Modules** | **Notes** |     |
| **None**    |           |     |

## Configuration Files to be provided by Integration Project

ImcArbn_Private_Cfg.c

ImcArbn_Private_Cfg.h

ImcArbn\_ Cfg.h

Note 1: Include “ImcArbn_Private_Cfg.h” in the “Rte_UserTypes.h” file as
user defined typedefs are generated in this file.

Note 2: Configuration files “ImcArbn_Private_Cfg.c”,
“ImcArbn_Private_Cfg.h” and “ImcArbn\_ Cfg.h”

shall be regenerated whenever there is a change in text template files
*ImcArbn_Private_Cfg.c.tt,* *ImcArbn_Private_Cfg.h.tt and
ImcArbn_Cfg.c.tt.*

Note 3: If there is no IMC Signal Group / IMC Signals are configured,
configuration scripts of this component will end-up in generating
zero-size array typedefs, which will cause compilation issues. It is a
design limitation and underlying assumption is that if no Signal Group
configured, then the component shall be removed from the project
altogether.

## Da Vinci DEVELOPER NOTES

Davinci Developer project for this component is just base. Integrator
need to import the developer project into the integration project and
add all required IMC Signals in order to access the signal using S/R
Ports. Also, for every of the signal, based on the Rate Group provided
by higher level Architectural and Requirement documents, port access
shall be provided to corresponding Transmit periodics (ImcArbnPer1= 2ms,
ImcArbnPer2= 10ms and ImcArbnPer3= 100ms). All IMC Signals RTE reads
shall be direct reads.

## Da Vinci Parameter Configuration Changes

Following configurations shall be made in DaVinci configurator for the
component. Configuration data for this component shall be provided by
higher level Architectural and Requirement documents.

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Impl/doc/mediax/media/image1.wmf"
style="width:6.29306in;height:1.225in" />

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Impl/doc/mediax/media/image2.wmf"
style="width:6.29306in;height:0.79792in" />

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Impl/doc/mediax/media/image3.wmf"
style="width:6.29306in;height:1.74722in" />

## DaVinci Interrupt Configuration Changes

|              |            |                         |           |
|--------------|------------|-------------------------|-----------|
| **ISR Name** | **VIM \#** | **Priority Dependency** | **Notes** |
| **N/A**      |            |                         |           |

## Manual Configuration Changes

|              |           |         |
|--------------|-----------|---------|
| **Constant** | **Notes** | **SWC** |
| **N/A**      |           |         |

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
<td><strong>ExclsvAr1DrvrTxRxBuf</strong></td>
<td><p>Exclusive area needs to protect access to Transmit and Receive
buffers from asynchronous updates by server runnables and periodic
updates by tasks.</p>
<p>Integrator needs to verify if client calls to server runnables can
inteerupt periodics and set up exclusive area to properly protect
access. If exclusive area is needed, at minimum it must disable OS Task
scheduling (It is assumed that all clients call occurs in OS
Tasks).</p></td>
<td></td>
</tr>
<tr class="odd">
<td><strong>ExclsvAr2SigDataBuf</strong></td>
<td><p>Exclusive area needs to protect access to Signal data buffers
from asynchronous read by server runnables and periodic updates by
tasks.</p>
<p>Integrator needs to verify if client calls to server runnables can
inteerupt periodics and set up exclusive area to properly protect
access. If exclusive area is needed, at minimum it must disable OS Task
scheduling (It is assumed that all clients call occurs in OS
Tasks).</p></td>
<td></td>
</tr>
</tbody>
</table>

# Integration DATAFLOW REQUIREMENTS

## Required Global Data Inputs

Refer AR350A_ImcArbn_DataDict.m file

## Required Global Data Outputs

Refer AR350A_ImcArbn_DataDict.m file

## Specific Include Path present

Yes

# Runnable Scheduling 

This section specifies the required runnable scheduling.

|                  |                             |             |
|------------------|-----------------------------|-------------|
| **Init**         | **Scheduling Requirements** | **Trigger** |
| **ImcArbnInit1** | Invoked by RTE during Init  | RTE         |

|                                    |                                    |                |
|--------------------------|----------------------------|-------------------|
| **Runnable**                       | **Scheduling Requirements**        | **Trigger**    |
| **ImcArbnPer1**                    | Refer Notes listed below the table | RTE 2ms Task   |
| **ImcArbnPer2**                    | Refer Notes listed below the table | RTE 10ms Taks  |
| **ImcArbnPer3**                    | Refer Notes listed below the table | RTE 100ms Task |
| **ImcArbnPer4**                    | Refer Notes listed below the table | RTE 2ms Task   |
| **ImcArbnPer5**                    | Refer Notes listed below the table | RTE 10ms Task  |
| **ImcArbnPer6**                    | Refer Notes listed below the table | RTE 100ms Task |
| **GetSigImcDataExtdSts_f32_Oper**  | Server Runnable                    | Client call    |
| **GetSigImcDataExtdSts_u32_Oper**  | Server Runnable                    | Client call    |
| **GetSigImcDataExtdSts_s32_Oper**  | Server Runnable                    | Client call    |
| **GetSigImcDataExtdSts_u16_Oper**  | Server Runnable                    | Client call    |
| **GetSigImcDataExtdSts_s16_Oper**  | Server Runnable                    | Client call    |
| **GetSigImcDataExtdSts_u08_Oper**  | Server Runnable                    | Client call    |
| **GetSigImcDataExtdSts_s08_Oper**  | Server Runnable                    | Client call    |
| **GetSigImcDataExtdSts_logl_Oper** | Server Runnable                    | Client call    |
| **GetSigImcData_f32_Oper**         | Server Runnable                    | Client call    |
| **GetSigImcData_u32_Oper**         | Server Runnable                    | Client call    |
| **GetSigImcData_s32_Oper**         | Server Runnable                    | Client call    |
| **GetSigImcData_u16_Oper**         | Server Runnable                    | Client call    |
| **GetSigImcData_s16_Oper**         | Server Runnable                    | Client call    |
| **GetSigImcData_u08_Oper**         | Server Runnable                    | Client call    |
| **GetSigImcData_s08_Oper**         | Server Runnable                    | Client call    |
| **GetSigImcData_logl_Oper**        | Server Runnable                    | Client call    |
| **GetTxRateGroup_Oper**            | Server Runnable                    | Client call    |
| **GetTxSigGroup_Oper**             | Server Runnable                    | Client call    |
| **SetRxSigGroup_Oper**             | Server Runnable                    | Client call    |

Notes:

1.  ImcArbnPer1, ImcArbnPer2 and ImcArbnPer3 periodic functions shall be
    called prior to calling respective primary and secondary signal
    source transmit layer functions.

2.  ImcArbnPer4, ImcArbnPer5 and ImcArbnPer6 periodic functions shall be
    called after calling respective primary and secondary signal source
    receive layer functions.

3.  ImcArbn Receive periodic functions (ImcArbnPer4, ImcArbnPer5 and
    ImcArbnPer6) shall run prior to the ImcArbn Transmit periodics
    (ImcArbnPer1, ImcArbnPer2 and ImcArbnPer3) functions.

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

## Non RTE NvM Blocks

|                |
|----------------|
| **Block Name** |
| **None**       |

Note : Size of the NVM block if configured in developer

##  RTE NvM Blocks

|                |
|----------------|
| **Block Name** |
| **None**       |

Note : Size of the NVM block if configured in developer

# Compiler Settings

##  Preprocessor MACRO

None

## Optimization Settings

None

# Appendix

*\<This section is for appendix\>*

{% endraw %}