---
layout: default
title: ImcArbn_MDD
nav_order: 2
parent: Component Implementation
---
{% raw %}
**Module Design Document**

**For**

**Imc Arbitration**

**Jan 17, 2017**

**Prepared For:**

**Software Engineering**

**Nexteer Automotive,**

**Saginaw, MI, USA**

**Prepared By:**

**Software Group,**

**Nexteer Automotive,**

**<u>Saginaw, MI, USAChange</u>** History

|             |                 |                      |             |             |
|------|----------------------|----------------------|----------|-------------|
| **Sl. No.** | **Description** | **Author**           | **Version** | **Date**    |
| 1           | Initial Version | Akilan Rathakrishnan | 1.0         | 17-Jan-2017 |

<u>Table of Contents</u>

[**1** **ImcArbn High-Level Description
7**](#imcarbn-high-level-description)

[2 Design details of software module
8](#design-details-of-software-module)

[Graphical representation of ImcArbn
8](#graphical-representation-of-imcarbn)

[2.1.1 Data Flow Diagram 8](#data-flow-diagram)

[2.1.2 Component level DFD 9](#component-level-dfd)

[2.1.3 Function level DFD 9](#function-level-dfd)

[3 Variable Data Dictionary 10](#variable-data-dictionary)

[3.1 User defined typedef definition/declaration
10](#user-defined-typedef-definitiondeclaration)

[3.2 Variable definition for enumerated types
12](#variable-definition-for-enumerated-types)

[4 Constant Data Dictionary 13](#constant-data-dictionary)

[Program (fixed) Constants 13](#program-fixed-constants)

[4.1.1 Embedded Constants 13](#embedded-constants)

[4.1.1.2 Global 13](#global)

[4.1.2 Module specific Lookup Tables Constants
13](#module-specific-lookup-tables-constants)

[5 Software Module Implementation 14](#software-module-implementation)

[5.1 Sub-Module Functions 14](#sub-module-functions)

[5.1.1 Init: ImcArbnInit1 14](#init-imcarbninit1)

[5.1.1.1 Design Rationale 14](#design-rationale)

[5.1.1.2 Design Rationale 14](#design-rationale-1)

[5.1.2 PERIODIC FUNCTIONS 14](#periodic-functions)

[5.1.3 Per: ImcArbnPer1 14](#per-imcarbnper1)

[5.1.3.1 Design Rationale 14](#design-rationale-2)

[5.1.4 Per: ImcArbnPer2 14](#per-imcarbnper2)

[5.1.4.1 Design Rationale 14](#design-rationale-3)

[5.1.5 Per: ImcArbnPer3 14](#per-imcarbnper3)

[5.1.5.1 Design Rationale 14](#design-rationale-4)

[5.1.6 Per: ImcArbnPer4 14](#per-imcarbnper4)

[5.1.6.1 Design Rationale 14](#design-rationale-5)

[5.1.7 Per: ImcArbnPer5 14](#per-imcarbnper5)

[5.1.7.1 Design Rationale 14](#design-rationale-6)

[5.1.8 Per: ImcArbnPer6 14](#per-imcarbnper6)

[5.1.8.1 Design Rationale 14](#design-rationale-7)

[5.1.9 Interrupt Functions 14](#interrupt-functions)

[5.2 Server Runnable Functions 15](#server-runnable-functions)

[5.2.1 GetSigImcDataExtdSts_f32 15](#getsigimcdataextdsts_f32)

[5.2.1.1 Design Rationale 15](#design-rationale-8)

[5.2.2 GetSigImcDataExtdSts_u32 15](#getsigimcdataextdsts_u32)

[5.2.2.1 Design Rationale 15](#design-rationale-9)

[5.2.3 GetSigImcDataExtdSts_u16 15](#getsigimcdataextdsts_u16)

[5.2.3.1 Design Rationale 15](#design-rationale-10)

[5.2.4 GetSigImcDataExtdSts_s16 15](#getsigimcdataextdsts_s16)

[5.2.4.1 Design Rationale 15](#design-rationale-11)

[5.2.5 GetSigImcDataExtdSts_u08 15](#getsigimcdataextdsts_u08)

[5.2.5.1 Design Rationale 15](#design-rationale-12)

[5.2.6 GetSigImcDataExtdSts_s08 15](#getsigimcdataextdsts_s08)

[5.2.6.1 Design Rationale 15](#design-rationale-13)

[5.2.7 GetSigImcDataExtdSts_logl 15](#getsigimcdataextdsts_logl)

[5.2.7.1 Design Rationale 15](#design-rationale-14)

[5.2.8 GetSigImcData_f32 15](#getsigimcdata_f32)

[5.2.8.1 Design Rationale 15](#design-rationale-15)

[5.2.9 GetSigImcData_u32 15](#getsigimcdata_u32)

[5.2.9.1 Design Rationale 15](#design-rationale-16)

[5.2.10 GetSigImcData_s32 15](#getsigimcdata_s32)

[5.2.10.1 Design Rationale 15](#design-rationale-17)

[5.2.11 GetSigImcData_u16 16](#getsigimcdata_u16)

[5.2.11.1 Design Rationale 16](#design-rationale-18)

[5.2.12 GetSigImcData_s16 16](#getsigimcdata_s16)

[5.2.12.1 Design Rationale 16](#design-rationale-19)

[5.2.13 GetSigImcData_u08 16](#getsigimcdata_u08)

[5.2.13.1 Design Rationale 16](#design-rationale-20)

[5.2.14 GetSigImcData_s08 16](#getsigimcdata_s08)

[5.2.14.1 Design Rationale 16](#design-rationale-21)

[5.2.15 GetSigImcData_logl 16](#getsigimcdata_logl)

[5.2.15.1 Design Rationale 16](#design-rationale-22)

[5.2.16 GetTxRateGroup 16](#gettxrategroup)

[5.2.16.1 Design Rationale 16](#design-rationale-23)

[5.2.17 GetTxSigGroup 16](#gettxsiggroup)

[5.2.17.1 Design Rationale 16](#design-rationale-24)

[5.2.18 SetRxSigGroup 16](#setrxsiggroup)

[5.2.18.1 Design Rationale 16](#design-rationale-25)

[5.3 Module Internal (Local) Functions
16](#module-internal-local-functions)

[5.3.1 Local Function \#1 16](#local-function-1)

[5.3.1.1 Description 17](#description)

[5.3.2 Local Function \#2 17](#local-function-2)

[5.3.2.1 Description 17](#description-1)

[5.3.3 Local Function \#3 17](#local-function-3)

[5.3.3.1 Description 17](#description-2)

[5.3.4 Local Function \#4 17](#local-function-4)

[5.3.4.1 Description 17](#description-3)

[5.3.5 Local Function \#5 17](#local-function-5)

[5.3.5.1 Description 18](#description-4)

[5.3.6 Local Function \#6 18](#local-function-6)

[5.3.6.1 Description 18](#description-5)

[5.3.7 Local Function \#7 18](#local-function-7)

[5.3.7.1 Description 18](#description-6)

[5.3.8 Local Function \#8 18](#local-function-8)

[5.3.8.1 Description 18](#description-7)

[5.3.9 Local Function \#9 19](#local-function-9)

[5.3.9.1 Description 19](#description-8)

[5.3.10 Local Function \#10 19](#local-function-10)

[5.3.10.1 Description 19](#description-9)

[5.3.11 Local Function \#11 19](#local-function-11)

[5.3.11.1 Description 19](#description-10)

[5.3.12 Local Function \#12 19](#local-function-12)

[5.3.12.1 Description 20](#description-11)

[5.3.13 Local Function \#13 20](#local-function-13)

[5.3.13.1 Description 20](#description-12)

[5.3.14 Local Function \#14 20](#local-function-14)

[5.3.14.1 Description 20](#description-13)

[5.3.15 Local Function \#15 20](#local-function-15)

[5.3.15.1 Description 20](#description-14)

[5.3.16 Local Function \#16 20](#local-function-16)

[5.3.16.1 Description 20](#description-15)

[5.3.17 Transition Functions 20](#transition-functions)

[5.3.18 Global Function/Macro Definitions
21](#global-functionmacro-definitions)

[6 Known Limitations with Design 22](#known-limitations-with-design)

[7 UNIT TEST CONSIDERATION 23](#unit-test-consideration)

[Appendix A Abbreviations and Acronyms 24](#abbreviations-and-acronyms)

[Appendix B Glossary 25](#glossary)

[Appendix C References 26](#references)

# ImcArbn High-Level Description

The Inter-Micro Communication (IMC) Arbitration prepares data for
transmission to a complimentary ECU through two redundant communication
paths. On the receive side, the Arbitration reads data from the primary
source and determines the data validity. A validity fault on primary
source prompts the IMC Arbitration component to evaluate the same signal
from the secondary source. Faulty signals from the primary source will
be replaced with signals from the secondary source, as long as they are
valid. If both data sources are invalid the IMC Arbitration outputs the
signal status based on never received, missing and invalid conditions.

# Design details of software module

*See FDD.*

## Graphical representation of ImcArbn

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Impl/doc/mediax/media/image1.png"
style="width:4.125in;height:7.25in" />

### Data Flow Diagram

See FDD.

### Component level DFD

See FDD.

### Function level DFD

See FDD.

# Variable Data Dictionary

## User defined typedef definition/declaration 

*\<This section documents any user types uniquely used for the
module.\>*

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Impl/doc/mediax/media/image2.wmf"
style="width:6.89028in;height:9.05417in" />

## Variable definition for enumerated types

|                                    |              |       |
|------------------------------------|--------------|-------|
| Enum Name                          | Element Name | Value |
| See AR350A_ImcArbn_DataDict.m file |              |       |

# Constant Data Dictionary

## Program (fixed) Constants

### Embedded Constants

#### Local Constants

|                                    |            |       |       |
|------------------------------------|------------|-------|-------|
| Constant Name                      | Resolution | Units | Value |
| See AR350A_ImcArbn_DataDict.m file |            |       |       |

## Global

\<This section lists the global constants used by the module. For
details on global constants, refer to the Data Dictionary for the
application\>

|                                    |
|------------------------------------|
| Constant Name                      |
| See AR350A_ImcArbn_DataDict.m file |

## Module specific Lookup Tables Constants

*\<(This is for lookup tables (arrays) with fixed values, same name as
other tables)*\>

|                               |              |              |                  |
|----------------------------|---------------|-------------|-----------------|
| Constant Name                 | type         | Value        | Software Segment |
| SIGGROUPCONFIG_REC            | SigGroupRec1 | Configurable | ImcArbn_CONST    |
| \<SIGGROUPNAME\>\_REC         | SigPrmRec1   | Configurable | ImcArbn_CONST    |
| RATEGROUPOFFS_CNT_U08         | Uint8        | Configurable | ImcArbn_CONST    |
| NRSIGGROUPINRATEGROUP_CNT_U08 | Uint8        | Configurable | ImcArbn_CONST    |
| MISSSIGGROUPTIOUT_CNT_U08     | Uint8        | Configurable | ImcArbn_CONST    |

Note: \<SIGGROUPNAME\>\_REC – Placeholder \<SIGGROUPNAME\> will be
replaced based on respective Signal Group names from the configuration.
Also note, this component will have as many number of
\<SIGGROUPNAME\>\_REC constants as number of Signal Groups.

# Software Module Implementation

## Sub-Module Functions

None

## Init: ImcArbnInit1 

## Design Rationale

*Design follows implementation in FDD.*

## Design Rationale

*Refer FDD*

## PERIODIC FUNCTIONS 

## Per: ImcArbnPer1

## Design Rationale

*Refer FDD*

## Per: ImcArbnPer2

## Design Rationale

*Refer FDD*

## Per: ImcArbnPer3

## Design Rationale

*Refer FDD*

## Per: ImcArbnPer4

## Design Rationale

*Refer FDD*

## Per: ImcArbnPer5

## Design Rationale

*Refer FDD*

## Per: ImcArbnPer6

## Design Rationale

*Refer FDD*

## Interrupt Functions

*None*

## Server Runnable Functions

## GetSigImcDataExtdSts_f32

## Design Rationale

*Refer FDD*

## GetSigImcDataExtdSts_u32

## Design Rationale

*Refer FDD*

## GetSigImcDataExtdSts_u16

## Design Rationale

*Refer FDD*

## GetSigImcDataExtdSts_s16

## Design Rationale

*Refer FDD*

## GetSigImcDataExtdSts_u08

## Design Rationale

*Refer FDD*

## GetSigImcDataExtdSts_s08

## Design Rationale

*Refer FDD*

## GetSigImcDataExtdSts_logl

## Design Rationale

*Refer FDD*

## GetSigImcData_f32

## Design Rationale

*Refer FDD*

## GetSigImcData_u32

## Design Rationale

*Refer FDD*

## GetSigImcData_s32

## Design Rationale

*Refer FDD*

## GetSigImcData_u16

## Design Rationale

*Refer FDD*

## GetSigImcData_s16

## Design Rationale

*Refer FDD*

## GetSigImcData_u08

## Design Rationale

*Refer FDD*

## GetSigImcData_s08

## Design Rationale

*Refer FDD*

## GetSigImcData_logl

## Design Rationale

*Refer FDD*

## GetTxRateGroup

## Design Rationale

*Refer FDD*

## GetTxSigGroup

## Design Rationale

*Refer FDD*

## SetRxSigGroup

## Design Rationale

*Refer FDD*

## Module Internal (Local) Functions

## Local Function \#1

|                      |                     |       |     |     |
|----------------------|---------------------|-------|-----|-----|
| **Function Name**    | ImcArbnTx           | Type  | Min | Max |
| **Arguments Passed** | RateGroup_Cnt_T_u08 | Uint8 | 0   | 2   |
| **Return Value**     | void                | N/A   | N/A | N/A |

## Description

This function implements “ImcArbnTx” function in the FDD.

## Local Function \#2

|                      |                            |                |            |            |
|--------------|-----------------------------|-----------|----------|----------|
| **Function Name**    | ImcArbnRx                  | Type           | Min        | Max        |
| **Arguments Passed** | FrmFltCntr_Ary2D_u8        | Ary2D_u8_2_2\* | 0x00000001 | 0xFFFFFFFF |
|                      | RateGroup_Cnt_T_u08        | uint8          | 0          | 2          |
|                      | IniTiOutChkCmpl_Cnt_T_logl | Boolean        | 0          | 1          |
| **Return Value**     | None                       | N/A            | N/A        | N/A        |

## Description

This function implements “ImcArbnRx” function in the FDD.

## Local Function \#3

|                      |                               |                   |     |     |
|-------------|-----------------------------|-------------|---------|---------|
| **Function Name**    | NoDataHndlg                   | Type              | Min | Max |
| **Arguments Passed** | RxSigExtdSts1_Cnt_T_enum      | ImcArbnRxExtdSts1 | 0   | 6   |
|                      | RxDataSrc_Cnt_T_enum          | ImcArbnRxDataSrc1 | 0   | 2   |
|                      | RateGroup_Cnt_T_u08           | uint8             | 0   | 2   |
|                      | SigGroup_Cnt_T_u08            | uint8             | 0   | 255 |
|                      | PrimSrcNoDataRxd_Cnt_T_logl   | boolean           | 0   | 1   |
|                      | SecdrySrcNoDataRxd_Cnt_T_logl | boolean           | 0   | 1   |
| **Return Value**     | None                          | N/A               | N/A | N/A |

## Description

This function implements “NoDataHndlg” function in the FDD.

## Local Function \#4

|                      |                            |         |     |     |
|----------------------|----------------------------|---------|-----|-----|
| **Function Name**    | OvrdSigStsDurgStrtUp       | Type    | Min | Max |
| **Arguments Passed** | SigGroup_Cnt_T_u08         | uint8   | 0   | 255 |
|                      | IniTiOutChkCmpl_Cnt_T_logl | Boolean | 0   | 1   |
| **Return Value**     | None                       | N/A     | N/A | N/A |

## Description

This function implements “OvrdSigStsDurgStrtUp” function in the FDD.

## Local Function \#5

|                      |                            |                   |     |     |
|-------------|-----------------------------|------------|---------|---------|
| **Function Name**    | EvlSigGroupNeverRxdMissSts | Type              | Min | Max |
| **Arguments Passed** | RateGroup_Cnt_T_u08        | uint8             | 0   | 2   |
|                      | SigGroup_Cnt_T_u08         | uint8             | 0   | 255 |
| **Return Value**     | RxSigExtdSts1_Cnt_T_enum   | ImcArbnRxExtdSts1 | 0   | 6   |

## Description

This function implements “OvrdSigStsDurgStrtUp” function in the FDD.

## Local Function \#6

|                      |                                |                        |            |            |
|-------------|---------------------------|---------------|----------|----------|
| **Function Name**    | RxFrmVldChk                    | Type                   | Min        | Max        |
| **Arguments Passed** | DataBuf_Cnt_T_u08              | uint8\*                | 0x00000001 | 0xFFFFFFFF |
|                      | FrmFltCntr_Cnt_T_u08           | Ary1D_u8_2\*           | 0x00000001 | 0xFFFFFFFF |
|                      | SigGroupDataSrc_Cnt_T_enum     | ImcArbnRxDataSrc1      | 0          | 2          |
|                      | RateGroup_Cnt_T_u08            | uint8                  | 0          | 2          |
|                      | SigGroup_Cnt_T_u08             | Uint8                  | 0          | 255        |
|                      | PrimSrcOnlySigGroup_Cnt_T_logl | Boolean                | 0          | 1          |
|                      | IniTiOutChkCmpl_Cnt_T_logl     | Boolean                | 0          | 1          |
| **Return Value**     | FrmSts_Cnt_T_enum              | ImcArbnRxRollgCntrSts1 | 0          | 2          |

## Description

This function implements “RxFrmVldChk” function in the FDD.

## Local Function \#7

|                      |                            |                   |     |     |
|-------------|---------------------------|---------------|----------|----------|
| **Function Name**    | ImcChResyncHndlg           | Type              | Min | Max |
| **Arguments Passed** | SigGroupDataSrc_Cnt_T_enum | ImcArbnRxDataSrc1 | 0   | 2   |
|                      | SigGroup_Cnt_T_u08         | Uint8             | 0   | 255 |
|                      | PrsntRollgCntr_Cnt_T_u08   | Uint8             | 0   | 31  |
| **Return Value**     | Void                       | NA                | NA  | NA  |

## Description

This function implements “ImcChResyncHndlg” function in the FDD.

## Local Function \#8

|                      |                            |                        |     |     |
|-------------|---------------------------|---------------|----------|----------|
| **Function Name**    | VldtRollgCntr              | Type                   | Min | Max |
| **Arguments Passed** | SigGroupDataSrc_Cnt_T_enum | ImcArbnRxDataSrc1      | 0   | 2   |
|                      | RateGroup_Cnt_T_u08        | Uint8                  | 0   | 2   |
|                      | SigGroup_Cnt_T_u08         | Uint8                  | 0   | 255 |
|                      | PrsntRollgCntr_Cnt_T_u08   | Uint8                  | 0   | 31  |
| **Return Value**     | RollgCntrSts_Cnt_T_enum    | ImcArbnRxRollgCntrSts1 | 0   | 2   |

## Description

This function implements “VldtRollgCntr” function in the FDD.

## Local Function \#9

|                      |                            |                        |     |     |
|-------------|---------------------------|---------------|----------|----------|
| **Function Name**    | VldtRollgCntrAlg           | Type                   | Min | Max |
| **Arguments Passed** | SigGroupDataSrc_Cnt_T_enum | ImcArbnRxDataSrc1      | 0   | 2   |
|                      | RateGroup_Cnt_T_u08        | Uint8                  | 0   | 2   |
|                      | SigGroup_Cnt_T_u08         | Uint8                  | 0   | 255 |
|                      | PrsntRollgCntr_Cnt_T_u08   | Uint8                  | 0   | 31  |
| **Return Value**     | RollgCntrSts_Cnt_T_enum    | ImcArbnRxRollgCntrSts1 | 0   | 2   |

## Description

This function implements “VldtRollgCntrAlg” function in the FDD.

## Local Function \#10

|                      |                           |         |     |     |
|----------------------|---------------------------|---------|-----|-----|
| **Function Name**    | RollgCntrSeqChk           | Type    | Min | Max |
| **Arguments Passed** | PrsntRollgCntr_Cnt_T_u08  | Uint8   | 0   | 31  |
|                      | AntcptdRollCntr_Cnt_T_u08 | Uint8   | 0   | 31  |
|                      | UpprDriftLim_Cnt_T_u08    | Uint8   | 0   | 255 |
|                      | LwrDriftLim_Cnt_T_u08     | Uint8   | 0   | 255 |
| **Return Value**     | RollgCntrVld_Cnt_T_logl   | boolean | 0   | 1   |

## Description

This function implements “RollgCntrSeqChk” function in the FDD.

## Local Function \#11

|                      |                   |                      |            |            |
|-------------|---------------------------|---------------|----------|----------|
| **Function Name**    | CreatSigGroupData | Type                 | Min        | Max        |
| **Arguments Passed** | SigGroup_T_rec    | SigGroupRec1 const\* | 0x00000001 | 0xFFFFFFFF |
| **Return Value**     | RetData_Uls_T_u32 | uint32               | 0          | 4294967295 |

## Description

This function implements “CreatSigGroupData” function in the FDD.

## Local Function \#12

|                      |                          |                      |            |            |
|-------------|---------------------------|---------------|----------|----------|
| **Function Name**    | DecodSigGroupData        | Type                 | Min        | Max        |
| **Arguments Passed** | SigGroup_T_rec           | SigGroupRec1 const\* | 0x00000001 | 0xFFFFFFFF |
|                      | SigGroupRxData_Uls_T_u32 | uint32               | 0          | 4294967295 |
|                      | RxSigExtdSts1_Cnt_T_enum | ImcArbnRxExtdSts1    | 0          | 6          |
|                      | RxDataSrc_Cnt_T_enum     | ImcArbnRxDataSrc1    | 0          | 2          |
| **Return Value**     | void                     |                      |            |            |

## Description

This function implements “DecodSigGroupData” function in the FDD.

## Local Function \#13

|                      |                    |        |     |            |
|----------------------|--------------------|--------|-----|------------|
| **Function Name**    | GetBitMask         | Type   | Min | Max        |
| **Arguments Passed** | NrOfBits_Cnt_T_u08 | Uint8  | 0   | 31         |
| **Return Value**     | BitMask_Cnt_T_u32  | uint32 | 0   | 4294967295 |

## Description

This function implements “GetBitMask” function in the FDD.

## Local Function \#14

|                      |                          |                   |     |     |
|-------------|---------------------------|---------------|----------|----------|
| **Function Name**    | GetImcSigSts             | Type              | Min | Max |
| **Arguments Passed** | RxSigExtdSts1_Cnt_T_enum | ImcArbnRxExtdSts1 | 0   | 6   |
| **Return Value**     | RetSts_Cnt_T_enum        | ImcArbnRxSts1     | 0   | 2   |

## Description

This function implements “GetImcSigSts” function in the FDD.

## Local Function \#15

|                      |                      |       |     |     |
|----------------------|----------------------|-------|-----|-----|
| **Function Name**    | GetImcFltParamByte   | Type  | Min | Max |
| **Arguments Passed** | void                 |       |     |     |
| **Return Value**     | FltBitMask_Cnt_T_u08 | Uint8 | 0   | 15  |

## Description

This function implements “GetImcFltParamByte” function in the FDD.

## Local Function \#16

|                      |                    |         |     |     |
|----------------------|--------------------|---------|-----|-----|
| **Function Name**    | NoDataRxd          | Type    | Min | Max |
| **Arguments Passed** | StrtByte_Cnt_T_u08 | Uint8   | 0   | 255 |
|                      | EndByte_Cnt_T_u08  | Uint8   | 0   | 255 |
| **Return Value**     | RetVal_Cnt_T_logl  | boolean | 0   | 1   |

## Description

This function implements “NoDataRxd” function in the FDD.

## Transition Functions

None.

## Global Function/Macro Definitions

Refer FDD

# Known Limitations with Design

> None

# UNIT TEST CONSIDERATION

1.  Number of Signals / Signal Groups / Rate Groups that can be
    supported by Imc Tx/Rx is configurable. Even though underlying data
    type of configuration information might have wider range, only
    values that are generated out of configuration will be supported by
    the component. If complete range need to be supported, then make
    configuration, and generate the cfg files accordingly. Also, none of
    the configuration values shall be hand-modified to cover legal range
    of underlying parameter.

####### Abbreviations and Acronyms

| **Abbreviation or Acronym** | **Description**            |
|-----------------------------|----------------------------|
| DFD                         | Design functional diagram  |
| MDD                         | Module design Document     |
| FDD                         | Functional Design Document |

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

| **Ref. \#** | **Title**                                                                                                                                                     | **Version**                    |
|-------|-------------------------------------------------|-----------------|
| 1           | AUTOSAR Specification of Memory Mapping (Link:[AUTOSAR_SWS_MemoryMapping.pdf](http://www.autosar.org/download/R4.0/AUTOSAR_SWS_MemoryMapping.pdf))            | v1.3.0 R4.0 Rev 2              |
| 2           | MDD Guideline                                                                                                                                                 | EA4 01.00.00                   |
| 3           | [Software Naming Conventions.doc](http://misagweb01.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_fc55f/Software Naming Conventions 03x(In Work).doc)   | 1.0                            |
| 4           | [Software Design and Coding Standards.doc](http://eroom1.nexteer.com/eRoomReq/Files/erooms8/NextGeneration/0_1a67a9/Software Design and Coding Standards.doc) | 2.1                            |
| 5           | FDD: AR350A_ImcArbn_Design                                                                                                                                    | See Synergy subproject version |

{% endraw %}