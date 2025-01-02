---
layout: default
title: HwAgSysArbn_MDD
nav_order: 3
parent: Component Implementation
---
{% raw %}
**Module Design Document**

**For**

**HwAgSysArbn**

**June 20, 2016**

**Prepared For:**

**Software Engineering**

**Nexteer Automotive,**

**Saginaw, MI, USA**

**Prepared By:**

**Spandana Balani**

**  
<u>Change History</u>**

|             |                                                    |                                |             |              |
|------|---------------------------------|-----------|----------|-------------|
| **Sl. No.** | **Description**                                    | **Author**                     | **Version** | **Date**     |
| 1           | Initial Version                                    | Sarika Natu(KPIT Technologies) | 1.0         | 07-Sept-2015 |
| 2           | SF045A_HwAgSysArbn_Design version 2 implementation | SB                             | 2.0         | 20-Jun-2016  |
|             |                                                    |                                |             |              |
|             |                                                    |                                |             |              |

|     |     |     |     |     |
|-----|-----|-----|-----|-----|
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |

**  
**

<u>Table of Contents</u>

1 HwAgSysArbn & High-Level Description 4

2 Design details of software module 5

2.1 Graphical representation of HwAgSysArbn 5

2.2 Data Flow Diagram 5

2.2.1 Component level DFD 5

2.2.2 Function level DFD 5

3 Constant Data Dictionary 6

3.1 Program (fixed) Constants 6

3.1.1 Embedded Constants 6

4 Software Component Implementation 7

4.1 Sub-Module Functions 7

4.1.1 Init: HwAgSysArbn_Init1 7

4.1.1.1 Design Rationale 7

4.1.1.2 Module Outputs 7

4.1.2 Per: HwAgSysArbn_Per1 7

4.1.2.1 Design Rationale 7

4.1.2.2 Store Module Inputs to Local copies 7

4.1.2.3 (Processing of function)……… 7

4.1.2.4 Store Local copy of outputs into Module Outputs 7

4.2 Server Runables 7

4.3 Interrupt Functions 7

4.4 Module Internal (Local) Functions 7

4.4.1 Local Function \#1 7

4.4.1.1 Design Rationale 8

4.4.1.2 Processing 8

4.5 GLOBAL Function/Macro Definitions 8

5 Known Limitations with Design 9

6 UNIT TEST CONSIDERATION 10

Appendix A References 11

# HwAgSysArbn & High-Level Description

The Handwheel angle system arbitration function accepts inputs from the
various angle sources available in the EPS system and selects the angle
source to be used for the system handwheel angle value. It also provides
for compliance compensation of the angle value and determines the angle
value and angle validity to be output on the vehicle data bus.

# Design details of software module

## Graphical representation of HwAgSysArbn

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/SF045A_HwAgSysArbn_Impl/doc/mediax/media/image2.png"
style="width:3.14167in;height:3.49167in" />

## Data Flow Diagram

See FDD.

### Component level DFD

See FDD.

### Function level DFD

See FDD.

# Constant Data Dictionary

## Program (fixed) Constants

### Embedded Constants

#### Local Constants

Refer .m file

# Software Component Implementation

## Sub-Module Functions

## Init: HwAgSysArbn_Init1

## Design Rationale

*Refer FDD*

## Module Outputs

*Refer FDD*

## Per: HwAgSysArbn_Per1

## Design Rationale

## Store Module Inputs to Local copies

*Refer FDD*

##  (Processing of function)………

*Refer FDD*

## Store Local copy of outputs into Module Outputs

*Refer FDD*

## Server Runables 

None

## Interrupt Functions

None

## Module Internal (Local) Functions

## 

|     |     |     |     |     |
|-----|-----|-----|-----|-----|
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |

## 

## 

## 

|     |     |     |     |     |
|-----|-----|-----|-----|-----|
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |

## 

## 

## 

|     |     |     |     |     |
|-----|-----|-----|-----|-----|
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |

## 

## 

## 

|     |     |     |     |     |
|-----|-----|-----|-----|-----|
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |
|     |     |     |     |     |

## 

## 

## Local Function \#1

|                   |                              |         |       |      |
|-------------------|------------------------------|---------|-------|------|
| **Function Name** | HwSigSerlComArbn             | Type    | Min   | Max  |
| 1Arguments Passed | HwAgCorrdConf_Uls_T_f32      | uint8   | 0     | 1    |
|                   | HwAgSnsrlsConf_Uls_T_f32     | uint8   | 0     | 1    |
|                   | HwAgCorrd_HwDeg_T_f32        | float32 | -1440 | 1440 |
|                   | HwAgSnsrls_HwDeg_T_f32       | float32 | -1440 | 1440 |
|                   | \*HwAgStsToSerlCom_Cnt_T_lgc | boolean | FALSE | TRUE |
| **Return Value**  | HwAgToSerlCom_HwDeg_T_f32    | float32 | -1440 | 1440 |

## Design Rationale

Note: Outputs of “HwSigSerlComArbn” function are
HwAgStsToSerlCom_Cnt_T_lgc, HwAgToSerlCom_HwDeg_T_f32

## Processing

Refer to the Handwheel signal serial communication arbitration
functionality of “HwAgSrcSeln” subsystem in the Simulink model.

## GLOBAL Function/Macro Definitions

None

# Known Limitations with Design

None

# UNIT TEST CONSIDERATION

None

####### 

|     |     |
|-----|-----|
|     |     |

####### 

-   
-   
-   
-   
-   
-   
-   
-   
-   
-   
-   

|     |     |     |
|-----|-----|-----|
|     |     |     |
|     |     |     |

####### References

| **Ref. \#** | **Title**                                                                                                                                                             | **Version**                    |
|-------|-------------------------------------------------|-----------------|
| 1           | AUTOSAR Specification of Memory Mapping (Link:[AUTOSAR_SWS_MemoryMapping.pdf](http://www.autosar.org/download/R4.0/AUTOSAR_SWS_MemoryMapping.pdf))                    | v1.3.0 R4.0 Rev 2              |
| 2           | MDD Guideline                                                                                                                                                         | Process Release 04.02.01       |
| 3           | [Software Naming Conventions.doc](http://misagweb01.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_fc55f/Software%20Naming%20Conventions%2003x(In%20Work).doc)   | Process Release 04.02.01       |
| 4           | [Software Design and Coding Standards.doc](http://eroom1.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_1a67a9/Software%20Design%20and%20Coding%20Standards.doc) | Process Release 04.02.01       |
| 5           | SF045A_HwAgSysArbn_Design                                                                                                                                             | See Synergy subproject version |

{% endraw %}