---
layout: default
title: TSG31CfgAndUse Integration Manual
nav_order: 2
parent: Component Implementation
---
{% raw %}
**TSG31CfgAndUse**

**Integration Manual**

**VERSION: 1.0**

**DATE: 28-Apr-2015**

**Revision History**

|             |                 |            |             |             |
|-------------|-----------------|------------|-------------|-------------|
| **Sl. No.** | **Description** | **Author** | **Version** | **Date**    |
| 1           | Initial version | K Creager  | 1.0         | 28-Apr-2015 |

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
7](#__RefHeading___Toc417976010)

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

[7.3 Non RTE NvM Blocks 10](#non-rte-nvm-blocks)

[7.4 RTE NvM Blocks 10](#rte-nvm-blocks)

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

# References

This section lists the title & version of all the documents that are
referred for development of this document

|         |                                   |                                   |
|----------|----------------------------------------------|-----------------|
| Sr. No. | Title                             | Version                           |
| \<1\>   | MDD Guidelines                    | Software Process Release 03.06.00 |
| \<2\>   | Software Naming Conventions       | Software Process Release 03.06.00 |
| \<3\>   | Design and Coding Standards       | Software Process Release 03.06.00 |
| \<4\>   | FDD: CM475A_TSG31CfgAndUse_Design | See Synergy subproject version    |

# Dependencies

## SWCs

|                     |                                          |
|---------------------|------------------------------------------|
| **Module**          | **Required Feature**                     |
| **\<Name of SWC\>** | \<Addition of global data, function\>\*. |

Note : Referencing the external components should be avoided in most
cases. Only in unavoidable circumstance external components should be
referred. Developer should track the references.

## Global Functions(Non RTE) to be provided to Integration Project

> See FDD – CM475A_TSG31CfgAndUse_DataDict.m file

# Configuration REQUIREMeNTS

## Build Time Config

|             |           |     |
|-------------|-----------|-----|
| **Modules** | **Notes** |     |
| **None**    |           |     |

## Configuration Files to be provided by Integration Project

\<Configuration file that will generated from this components that will
require Da Vinci Config generation or manual generation. Describe each
parameter \>

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

See FDD – CM475A_TSG31CfgAndUse_DataDict.m file

## Required Global Data Outputs

See FDD – CM475A_TSG31CfgAndUse_DataDict.m file

## Specific Include Path present

Yes

# Runnable Scheduling 

This section specifies the required runnable scheduling.

|                         |                             |             |
|-------------------------|-----------------------------|-------------|
| **Init**                | **Scheduling Requirements** | **Trigger** |
| **TSG31CfgAndUseInit1** | None                        | RTE/ Init   |

|                        |                             |                        |
|-------------------|---------------------------------------|---------------|
| **Runnable**           | **Scheduling Requirements** | **Trigger**            |
| **TSG31CfgAndUsePer1** | None                        | Motor control runnable |
| **TSG31CfgAndUsePer2** | None                        | RTE/2 ms               |

**.**

# Memory Map REQUIREMENTS

## Mapping

|                            |                         |           |
|----------------------------|-------------------------|-----------|
| **Memory Section**         | **Contents**            | **Notes** |
| **MotCtrl_START_SEC_CODE** | Motor Control runnables |           |
|                            |                         |           |

\* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as
specified in the AUTOSAR Memory Mapping requirements.

## Usage

|                            |         |         |
|----------------------------|---------|---------|
| **Feature**                | **RAM** | **ROM** |
| **\<Memmap usuage info\>** |         |         |

Table 1: ARM Cortex R4 Memory Usage

## Non RTE NvM Blocks

|                                           |
|-------------------------------------------|
| **Block Name**                            |
| **\<NVM block used Non RTE functions \>** |

Note : Size of the NVM block if configured in developer

##  RTE NvM Blocks

|                                          |
|------------------------------------------|
| **Block Name**                           |
| **\<NVM block used in RTE functions \>** |

Note : Size of the NVM block if configured in developer

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