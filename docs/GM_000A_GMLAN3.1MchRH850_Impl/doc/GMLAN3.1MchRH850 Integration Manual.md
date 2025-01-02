---
layout: default
title: GMLAN3.1MchRH850 Integration Manual
nav_order: 10
parent: Component Implementation
---
{% raw %}
**Integration Manual**

**For**

**GMLAN3.1MchRH850**

**VERSION: 1**

**DATE: 02/01/17**

**Prepared By:**

**Software Group,**

**Nexteer Automotive,**

**Saginaw, MI, USA**

**Location:** The official version of this document is stored in the
Nexteer Configuration Management System.

**Revision History**

|             |                 |                |             |          |
|-------------|-----------------|----------------|-------------|----------|
| **Sl. No.** | **Description** | **Author**     | **Version** | **Date** |
| 1           | Initial version | Lucas Wendling | 1.0         | 02/01/17 |

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
7](#__RefHeading___Toc389222325)

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

[7.3 Non RTE NvM Blocks 10](#nvm-blocks)

[7.4 RTE NvM Blocks 10](#__RefHeading___Toc389222336)

[8 Compiler Settings 11](#compiler-settings)

[8.1 Preprocessor MACRO 11](#preprocessor-macro)

[8.2 Optimization Settings 11](#optimization-settings)

[9 Appendix 12](#appendix)

# Abbrevations And Acronyms

|                  |                 |
|------------------|-----------------|
| **Abbreviation** | **Description** |
|                  |                 |
|                  |                 |
|                  |                 |

# References

This section lists the title & version of all the documents that are
referred for development of this document

|             |           |             |
|-------------|-----------|-------------|
| **Sr. No.** | **Title** | **Version** |
|             |           |             |

# Dependencies

## SWCs

|                    |                                                                                                                                                                                                                                                                                                                                                                                        |
|-----------------------|-------------------------------------------------|
| **Module**         | **Required Feature**                                                                                                                                                                                                                                                                                                                                                                   |
| **VectorBswSuprt** | Integration of this version of GMLAN3.1MchRH850 requires using the 01.04.00_03.08.00 versions of files in the VectorBswSuprt component. This includes ensuring the overall project include path points to: “VectorBswSuprt\include\01.04.00_03.08.00” and the project green hills .gpj file associates the following green hills .gpj subproject file: “VStdLib_01.04.00_03.08.00.gpj” |

Note : Referencing the external components should be avoided in most
cases. Only in unavoidable circumstance external components should be
referred. Developer should track the references.

## Global Functions(Non RTE) to be provided to Integration Project

Per the CAN Driver documentation:

"If an exclusive write access to the CAN related EI level interrupt
control registers (ICn) is  
not possible or if the driver must not access registers outside the CAN
address space the  
switch C_ENABLE_OSEK_CAN_INTCTRL has to be defined via the user
configuration file.  
  
In this case the driver does not access the registers of the interrupt
controller at all and the  
application has to ensure proper initialization, disabling and restoring
of the CAN interrupt  
sources.  
The initialization of all necessary ICn has to be performed additionally
by the application  
before the call of CanInitPowerOn()if this switch is defined. All used
sources (see  
remarks in table 10-1) have to be enabled after initialization whereas
unused sources have  
to be disabled.  
  
In context of the interrupt disable/restore mechanism the driver
implements application  
call-backs that are used whenever the functions CanCanInterruptDisable()
or  
CanCanInterruptRestore() are invoked (see section 9.4 for API
definitions). The  
function OsCanCanInterruptDisable() should save the current mask status
(MK bits)  
of all used CAN interrupt sources that are linked to the given logical
channel and then set  
these bits to 1 in order to disable the sources.
OsCanCanInterruptRestore() has to  
restore the previously saved mask bits for the given logical channel.
These actions may  
differ based on the actual software configuration, but all CAN
interrupts on the  
corresponding channel have to be locked after the first call (nested
calls can occur) of  
OsCanCanInterruptDisable() and be available not until the last nested
call of  
OsCanCanInterruptRestore(). Keep in mind that the right physical channel
has to be  
chosen based on the given logical controller (to get the right ICn) and
that the receive  
FIFO and global status interrupt are used by all controllers."

It is assumed that integration of the CAN driver is done in a user-mode
application that has no direct access to the hardware interrupt
registers, and therefore the above “C_ENABLE_OSEK_CAN_INTCTRL” needs to
be defined in a user configuration file. **A user configuration file is
added in the “/tools/” folder of this component (CanDrv.cfg), and this
can be included in the Geny Can Driver User configuration file selection
to enable this interrupt feature mentioned above.** When this is done,
the following callouts need to be defined in the integration project:

OsCanCanInterruptDisable

OsCanCanInterruptRestore

These functions need to be implemented to be able to be nested calls, as
well as are required to disable all CAN related interrupts. As an
example, the OS API “SuspendOSInterrupts” and “ResumeOSInterrupts” can
be called from these functions so long as the CAN interrupts are
configured to be Category 2 ISRs in the OS (these OS APIs allow nested
calls). This may not, however, always be the most efficient
implementation as it disables all OS interrupts, not just the CAN
related OS interrupts.

# Configuration REQUIREMeNTS

Third party documentation can be referenced as needed.

## Build Time Config

|             |           |     |
|-------------|-----------|-----|
| **Modules** | **Notes** |     |
|             |           |     |

## Configuration Files to be provided by Integration Project

N/A

## Da Vinci Parameter Configuration Changes

|               |           |         |
|---------------|-----------|---------|
| **Parameter** | **Notes** | **SWC** |
|               |           |         |

## DaVinci Interrupt Configuration Changes

|              |           |
|--------------|-----------|
| **ISR Name** | **Notes** |
|              |           |

## Manual Configuration Changes

|              |           |         |
|--------------|-----------|---------|
| **Constant** | **Notes** | **SWC** |
|              |           |         |

# Integration DATAFLOW REQUIREMENTS

## Required Global Data Inputs

## Required Global Data Outputs

## Specific Include Path present

Yes

# Runnable Scheduling 

Third party documentation can be referenced as needed.

|          |                             |             |
|----------|-----------------------------|-------------|
| **Init** | **Scheduling Requirements** | **Trigger** |
|          |                             |             |

|              |                             |             |
|--------------|-----------------------------|-------------|
| **Runnable** | **Scheduling Requirements** | **Trigger** |
|              |                             |             |

**.**

# Memory Map REQUIREMENTS

## Mapping

|                    |              |           |
|--------------------|--------------|-----------|
| **Memory Section** | **Contents** | **Notes** |
|                    |              |           |
|                    |              |           |

\* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as
specified in the AUTOSAR Memory Mapping requirements.

## Usage

|             |         |         |
|-------------|---------|---------|
| **Feature** | **RAM** | **ROM** |
|             |         |         |

## NvM Blocks

# Compiler Settings

##  Preprocessor MACRO

## Optimization Settings

# Appendix

## Updates from Original Delivery

The delivery from Vector for this SIP contained an incorrect
“Gateway.pcu” file found in the “/tools/Generators/Components/”
directory. Attached is an email from Vector explaining the issue. Also,
attached are the original SIP file as well as the updated one from
Vector that needs to be used in this SIP.

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/GM_000A_GMLAN3.1MchRH850_Impl/doc/mediax/media/image1.wmf)![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/GM_000A_GMLAN3.1MchRH850_Impl/doc/mediax/media/image2.wmf)![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/GM_000A_GMLAN3.1MchRH850_Impl/doc/mediax/media/image3.wmf)

{% endraw %}