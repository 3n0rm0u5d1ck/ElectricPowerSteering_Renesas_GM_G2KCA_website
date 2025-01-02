---
layout: default
title: CM101A_ExcpnHndlg
nav_order: 1
parent: Component Design
---
{% raw %}
**Exception Handling**

**(ExcpnHndlg)**

**FDD CM101A**

[1. High Level Description 5](#high-level-description)

[2. Sub-Functions In This Document 7](#sub-functions-in-this-document)

[3. Critical Register Verification References
7](#critical-register-verification-references)

[4. Sub-functions 8](#sub-functions)

[4.1. Sub-Function: Exception Handling Configuration
8](#sub-function-exception-handling-configuration)

[4.1.1. NTCs 8](#ntcs)

[4.1.2. SAN Linkage 8](#san-linkage)

[4.1.3. Description 8](#description)

[4.1.4. Rationale 8](#rationale)

[4.1.5. Implementation 8](#implementation)

[4.1.6. Reference 10](#reference)

[4.1.7. Diagnostic Verification Method
11](#diagnostic-verification-method)

[4.2. Sub-Function: Exception Handling Routine SYSERR
12](#sub-function-exception-handling-routine-syserr)

[4.2.1. NTCs 12](#ntcs-1)

[4.2.2. SAN Linkage 12](#san-linkage-1)

[4.2.3. Description 12](#description-1)

[4.2.4. Rationale 12](#rationale-1)

[4.2.5. Implementation 12](#implementation-1)

[4.2.6. Reference 15](#reference-1)

[4.2.7. Verification Method 18](#verification-method)

[4.3. Sub-Function: Exception Handling Routine Floating Point
18](#sub-function-exception-handling-routine-floating-point)

[4.3.1. NTCs 18](#ntcs-2)

[4.3.2. SAN Linkage 18](#san-linkage-2)

[4.3.3. Description 18](#description-2)

[4.3.4. Rationale 18](#rationale-2)

[4.3.5. Implementation 18](#implementation-2)

[4.3.6. Reference 20](#reference-2)

[4.3.7. Verification Method 22](#verification-method-1)

[4.4. Sub-Function: Exception Handling Routine Misalignment
23](#sub-function-exception-handling-routine-misalignment)

[4.4.1. NTCs 23](#ntcs-3)

[4.4.2. SAN Linkage 23](#san-linkage-3)

[4.4.3. Description 23](#description-3)

[4.4.4. Rationale 23](#rationale-3)

[4.4.5. Implementation 23](#implementation-3)

[4.4.6. Reference 24](#reference-3)

[4.4.7. Verification Method 25](#verification-method-2)

[4.5. Sub-Function: Exception Handling Routine Reserved Instruction
26](#sub-function-exception-handling-routine-reserved-instruction)

[4.5.1. NTCs 26](#ntcs-4)

[4.5.2. SAN Linkage 26](#san-linkage-4)

[4.5.3. Description 26](#description-4)

[4.5.4. Rationale 26](#rationale-4)

[4.5.5. Implementation 26](#implementation-4)

[4.5.6. Verification Method 26](#verification-method-3)

[4.6. Sub-Function: Server Routine FENMI PEG
27](#sub-function-server-routine-fenmi-peg)

[4.6.1. NTCs 27](#ntcs-5)

[4.6.2. SAN Linkage 27](#san-linkage-5)

[4.6.3. Description 27](#description-5)

[4.6.4. Rationale 27](#rationale-5)

[4.6.5. Implementation 27](#implementation-5)

[4.6.6. Verification Method 27](#verification-method-4)

[4.7. Sub-Function: Server Routine FENMI SPI 2 Bit ECC Error
28](#sub-function-server-routine-fenmi-spi-2-bit-ecc-error)

[4.7.1. NTCs 28](#ntcs-6)

[4.7.2. SAN Linkage 28](#san-linkage-6)

[4.7.3. Description 28](#description-6)

[4.7.4. Rationale 28](#rationale-6)

[4.7.5. Implementation 28](#implementation-6)

[4.7.6. Reference 30](#reference-4)

[4.7.7. Verification Method 32](#verification-method-5)

[4.8. Sub-Function: Server Routine FENMI DMA Transfer Error
33](#sub-function-server-routine-fenmi-dma-transfer-error)

[4.8.1. NTCs 33](#ntcs-7)

[4.8.2. SAN Linkage 33](#san-linkage-7)

[4.8.3. Description 33](#description-7)

[4.8.4. Rationale 33](#rationale-7)

[4.8.5. Implementation 33](#implementation-7)

[4.8.6. Reference 34](#reference-5)

[4.8.7. Verification Method 34](#verification-method-6)

[4.9. Sub-Function: Server Routine FENMI DMA Access Violation Error
35](#sub-function-server-routine-fenmi-dma-access-violation-error)

[4.9.1. NTCs 35](#ntcs-8)

[4.9.2. SAN Linkage 35](#san-linkage-8)

[4.9.3. Description 35](#description-8)

[4.9.4. Rationale 35](#rationale-8)

[4.9.5. Implementation 35](#implementation-8)

[4.9.6. Reference 36](#reference-6)

[4.9.7. Verification Method 36](#verification-method-7)

[4.10. Sub-Function: Server Routine FENMI ECM Master/Checker Compare
37](#sub-function-server-routine-fenmi-ecm-masterchecker-compare)

[4.10.1. NTCs 37](#ntcs-9)

[4.10.2. SAN Linkage 37](#san-linkage-9)

[4.10.3. Description 37](#description-9)

[4.10.4. Rationale 37](#rationale-9)

[4.10.5. Implementation 37](#implementation-9)

[4.10.6. Verification Method 37](#verification-method-8)

[4.11. Sub-Function: Server Routine FENMI Watchdog
37](#sub-function-server-routine-fenmi-watchdog)

[4.11.1. NTCs 37](#ntcs-10)

[4.11.2. SAN Linkage 37](#san-linkage-10)

[4.11.3. Description 38](#description-10)

[4.11.4. Rationale 38](#rationale-10)

[4.11.5. Implementation 38](#implementation-10)

[4.11.6. Verification Method 39](#verification-method-9)

[4.12. Sub-Function: Server Routine FENMI DTS Double Bit ECC
40](#sub-function-server-routine-fenmi-dts-double-bit-ecc)

[4.12.1. NTCs 40](#ntcs-11)

[4.12.2. SAN Linkage 40](#san-linkage-11)

[4.12.3. Description 40](#description-11)

[4.12.4. Rationale 40](#rationale-11)

[4.12.5. Implementation 40](#implementation-11)

[4.12.6. Verification Method 40](#verification-method-10)

[4.13. Sub Function: Server Routine Process Unknown Exception Error
41](#sub-function-server-routine-process-unknown-exception-error)

[4.13.1. NTCs 41](#ntcs-12)

[4.13.2. SAN Linkage 41](#san-linkage-12)

[4.13.3. Description 41](#description-12)

[4.13.4. Rationale 41](#rationale-12)

[4.13.5. Implementation 41](#implementation-12)

[4.13.6. Verification Method 41](#__RefHeading___Toc440963618)

[4.14. Sub-Function: Server Routine Process Memory Protection Unit
Exception Error
42](#sub-function-server-routine-process-memory-protection-unit-exception-error)

[4.14.1. NTCs 42](#ntcs-13)

[4.14.2. SAN Linkage 42](#san-linkage-13)

[4.14.3. Description 42](#description-13)

[4.14.4. Rationale 42](#__RefHeading___Toc440963623)

[4.14.5. Implementation 42](#implementation-13)

[4.14.1. Verification Method 42](#__RefHeading___Toc440963625)

[4.15. Sub-Function: Server Routine Process Privileged Instruction
Exception Error 42](#__RefHeading___Toc440963626)

[4.15.1. NTCs 42](#__RefHeading___Toc440963627)

[4.15.2. SAN Linkage 42](#__RefHeading___Toc440963628)

[4.15.3. Description 42](#__RefHeading___Toc440963629)

[4.15.4. Rationale 43](#__RefHeading___Toc440963630)

[4.15.5. Implementation 43](#__RefHeading___Toc440963631)

[4.15.6. Verification Method 43](#__RefHeading___Toc440963632)

[4.16. Sub-Function: Server Routine Process Permanent Os Error
43](#__RefHeading___Toc440963633)

[4.16.1. NTCs 43](#__RefHeading___Toc440963634)

[4.16.2. SAN Linkage 43](#__RefHeading___Toc440963635)

[4.16.3. Description 43](#__RefHeading___Toc440963636)

[4.16.4. Rationale 43](#__RefHeading___Toc440963637)

[4.16.5. Implementation 43](#__RefHeading___Toc440963638)

[4.16.6. Verification Method 43](#__RefHeading___Toc440963639)

[4.17. Sub-Function: Server Routine Process Non Critical Os Error
43](#__RefHeading___Toc440963640)

[4.17.1. NTCs 43](#__RefHeading___Toc440963641)

[4.17.2. SAN Linkage 43](#__RefHeading___Toc440963642)

[4.17.3. Description 44](#__RefHeading___Toc440963643)

[4.17.4. Rationale 44](#__RefHeading___Toc440963644)

[4.17.5. Implementation 44](#__RefHeading___Toc440963645)

[4.17.6. Verification Method 44](#__RefHeading___Toc440963646)

[4.18. Periodic (ExcpnHndlgPer1) 44](#periodic-excpnhndlgper1)

[4.18.1. Verification Method 44](#verification-method-15)

[4.19. Sub-Function: Server Routine Shutdown Hook
45](#sub-function-server-routine-shutdown-hook)

[4.20. Sub-Function: Exception Handling Routine EIINT
45](#sub-function-exception-handling-routine-eiint)

[4.21. Sub-Function: Reset Source Determination
46](#sub-function-reset-source-determination)

[4.21.1. NTCs 46](#ntcs-17)

[4.21.2. SAN Linkage 47](#san-linkage-17)

[4.21.3. Description 47](#description-17)

[4.21.4. Rationale 47](#rationale-16)

[4.21.5. Implementation 47](#implementation-17)

[4.21.6. Verification Method 53](#verification-method-16)

[5. Special Functions 53](#special-functions)

[6. Revision Record & Change Approval
54](#revision-record-change-approval)

# High Level Description

This document describes the exception handling / reset cause
determination for microcontroller diagnostics. Note that the MCU handler
is in place to parse / identify FE and EI exception sources (of the 43
shown). The MCU will call server functions in this FDD for FE type
interrupts. EI based interrupts will call server functions directly to
the FDD.

Additionally, any pre-OS type failures that are detected are “saved”
using backup RAM until the reset cause functionality is performed. The
reset cause algorithm uses the backup RAM (modified by both Exceptions
and pre-OS start up tests) to set appropriate fault codes. For this FDD,
NTCs are only set in the reset cause function.

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CM101A_ExcpnHndlg_Design/Design/mediax/media/image1.wmf)

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CM101A_ExcpnHndlg_Design/Design/mediax/media/image2.wmf)

# Sub-Functions In This Document

Below is a linked list of all sub-functions owned by this document.

|                                                 |                                   |
|----------------------------------------------------|--------------------|
| **Sub-Function Name**                           | **Link**                          |
| Exception Handling Configuration                | 4.1                               |
| Exception Handling Routine SYSERR               | 4.2                               |
| Exception Handling Routine Floating Point       | 4.3                               |
| Exception Handling Routine Misalignment         | 4.4                               |
| Exception Handling Routine Reserved Instruction | 4.5                               |
| Server Routine FENMI PEG                        | 4.6                               |
| Server Routine FENMI SPI 2 Bit ECC              | 4.7                               |
| Server Routine FENMI DMA Transfer Error         | 4.8                               |
| Server Routine FENMI DMA Access Violation Error | 4.9                               |
| Server Routine FENMI Master Checker Compare     | 4.10                              |
| Server Routine FENMI Watchdog                   | 4.11                              |
| Server Routine FENMI DTS Double Bit ECC         | 4.12                              |
| Server Routine FENMI Unknown                    | Error: Reference source not found |
| Server Routine Protection Hook                  | Error: Reference source not found |
| Server Routine Error Hook                       | 4.14                              |
| Server Routine Shutdown Hook                    | 4.19                              |
| Exception Handling Routine EIINT                | Error: Reference source not found |
| Reset Source Determination                      | 4.21                              |

# Critical Register Verification References

This table contains the information needed for critical register
verification as configured or used in this document.

<table>
<colgroup>
<col style="width: 11%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 12%" />
<col style="width: 14%" />
<col style="width: 10%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Register</strong></td>
<td><p><strong>Register No.</strong></p>
<p><strong>(regID, selID)</strong></p></td>
<td><strong>Access Permission</strong></td>
<td><p><strong>Init / Periodic</strong></p>
<p><strong>Verification</strong></p></td>
<td><strong>Masking</strong></td>
<td><strong>Expected Value</strong></td>
<td><strong>Protn Score From Eval Sheet</strong></td>
</tr>
<tr class="even">
<td>FPCFG</td>
<td>SR10, 0</td>
<td>CU0</td>
<td>Init</td>
<td>None</td>
<td>0x0000 001C</td>
<td>0</td>
</tr>
</tbody>
</table>

# Sub-functions

## Sub-Function: Exception Handling Configuration

Return to sub-function list link: Sub-Functions In This Document

### NTCs

NA

### SAN Linkage

**SAN-49:** After reset the generation of SYSERR exception request due
to the errors shown in the Error notification Control Register (SEGCONT)
is disabled. This notification **can** be enabled by setting the related
bits accordingly.

**SAN-263:** Generation of SYSERR exception in case of uncorrectable
error (e.g. DED, Address parity) during instruction fetch cannot be
masked for instruction fetch unit in SEGCONT. However, such errors
**shall** be always handled by ECM within DTI.

**SAN-278:** Transition to the safe state **shall** take place when an
ECC 2-bit error, or an overflow error has occurred. For this purpose,
the ECM **shall** be configured accordingly.

**SAN-342:** Transition the MCU and the system to the safe state
**shall** take place when an address parity error has occurred. For this
purpose, the ECM shall be configured accordingly.

**SAN-401:** Transition to the safe state **shall** take place when
2-bits error, an error count overflow or an address error has been
detected. For this purpose, configure the appropriate response in the
ECM accordingly.

**SAN-413:** Upon detection of non-correctable bit error in the local
RAM, a system error exception request will be sent to SEG to generate a
SYSERR (FE-level) exception (if it is enabled).

### Description

This sub-function configures or identifies the exception handling
characteristics for the RH850 related to microcontroller diagnostics.

### Rationale

The Nexteer approach planned for exception handling involves two types –
those serious errors that will be handled by forcing a software reset of
the microcontroller and those that do not. This sub-function is intended
to show the list of exceptions and highlight those that will be
configured to be a system error (SYSERR) via the use of the SEGCONT
register. Floating point exceptions must also be configured.

Exception Handler assumes that the MCAL will configure the CVMREN
register to cause a reset when the CVM Fails.

### Implementation

#### Initialization (ExcpnHndlgInit1)

Register Configuration Summary

<table>
<colgroup>
<col style="width: 23%" />
<col style="width: 33%" />
<col style="width: 26%" />
<col style="width: 8%" />
<col style="width: 8%" />
</colgroup>
<tbody>
<tr class="odd">
<td rowspan="2"><strong>Register</strong></td>
<td rowspan="2"><strong>Value</strong></td>
<td rowspan="2"><strong>Comments</strong></td>
<td colspan="2"><strong>Access</strong></td>
</tr>
<tr class="even">
<td><strong>SV</strong></td>
<td><strong>UM</strong></td>
</tr>
<tr class="odd">
<td>FPCFG (Floating-point operation configuration)</td>
<td><p>FPCFG.XE.V = 1 (Validity)</p>
<p>FPCFG.XE.Z = 1 (Divide by Zero)</p>
<p>FPCFG.XE.O = 1 (Overflow)</p>
<p>FPCFG.XE.U = 0 (Underflow)</p>
<p>FPCFG.XE.I = 0 (Imprecise)</p></td>
<td>Only addresses configuring the exception bits</td>
<td>R/W</td>
<td>R/W</td>
</tr>
<tr class="even">
<td>* SYSCVMDEW (CVM Detection Enable Register)</td>
<td>SYSCVMDEW. CVMDIAGMEW = 0</td>
<td><p>Enable CVM Diagnosis</p>
<p><strong>NOTE: This is a protected register. Can only be written to
once.</strong></p></td>
<td>R/W</td>
<td>R/W</td>
</tr>
</tbody>
</table>

\*Denotes that no direct write is required as the default value meets
the requirement.

NOTE: MCU configuration has a checkbox selection for the self-test –
consider this in the future design.

// Configure floating point <u>exceptions</u> – note that other FPU
configuration is done in the FBL

FPCFG = 0x0000 001C

### Reference

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CM101A_ExcpnHndlg_Design/Design/mediax/media/image3.wmf"
style="width:5.99931in;height:7.65903in" />

FPSR (See boot loader CM110A for configuration function):

<u>Bits 31 to 24:</u> Status bits – NA for configuration – initialize to
zero

<u>Bit 23</u>: FN Flush to Nearest: recommend setting this bit to 1 –
along with the FS (Flush Subnormal) bit set to 1 and the RM bits set to
RN (round to nearest) , this setting will cause subnormal numbers to be
flushed to either zero or +/- the smallest magnitude normal number,
whichever is closer to the subnormal result – essentially rounds the
subnormal result rather than flushing to zero always. (See FS setting
for EA3 comparison)

<u>Bit 22</u>: IF: status bit – NA for configuration – initialize to
zero

<u>Bit 21</u>: PEM: recommend setting to 0 – for imprecise floating
point exceptions. This does not allow resuming execution after the
exception handler, which is ok since the expected design is to cause a
reset. Precise exceptions would allow resuming execution but causes
slower operation (different pipelining to allow for precise exceptions).

<u>Bit 20</u>: Reserved: must write a 0

<u>Bits 19 and 18</u>: RM, rounding mode, recommend setting is 00 for RN
round to nearest. This matches the setting used in EA3.

<u>Bit 17</u>: FS flush subnormal – recommend setting this bit to 1 to
enable flush subnormal. This is the default setting of this bit. The
floating point coprocessor does not have hardware processing of
subnormal numbers; therefore if FS is disabled, any subnormal operand or
result causes an exception so that software processing can occur;
recommend flush subnormal for throughput optimization. NOTE that this
differs from the EA3 setting. The EA3 processor has hardware support for
subnormal number processing and we do not flush subnormal numbers; not
flushing is the default setting for the EA3 processor.

<u>Bit 16</u>: reserved: must write a 0

<u>Bits 15 to 10:</u> Status bits – NA for configuration – initialize to
zero

<u>Bits 9 to 5</u>: Exception enable bits: recommend setting as in EA3
FDD (although no EA3 program has turned these settings on yet)

Bit 9 – V – invalid operation – set to 1 to enable exception

Bit 8 – Z – divide by zero – set to 1 to enable exception

Bit 7 – O – overflow – set to 1 to enable exception

Bit 6 – U – underflow – set to 0 to disable exception

Bit 5 – I – inexact – set to 0 to disable exception

<u>Bits 4 to 0:</u> Status bits – NA for configuration – initialize to
zero

### Diagnostic Verification Method

NA as this is a configuration sub-function

## Sub-Function: Exception Handling Routine SYSERR

Return to sub-function list link: <u>Sub-Functions In This Document</u>

### NTCs

None – NTCs are addressed in section 4.21 (Reset Source)

### SAN Linkage

**SAN-166:** If SYSERR exception is generated, a reset of the device
**shall** be issued.

**SAN-263:** Generation of SYSERR exception in case of uncorrectable
error (e.g. DED, Address parity) during instruction fetch cannot be
masked for instruction fetch unit in SEGCONT. However, such errors
**shall** be always handled by ECM within DTI.

**SAN-278:** Transition to the safe state **shall** take place when an
ECC 2-bit error, or an overflow error has occurred. For this purpose,
the ECM **shall** be configured accordingly.

**SAN-342:** Transition the MCU and the system to the safe state shall
take place when an address parity error has occurred. For this purpose,
the ECM shall be configured accordingly.

**SAN-343:** In case an address parity error has occurred, a system
error (SYSERR) exception will be generated. This exception is
terminating and a reset from the ECM or from the pin becomes necessary.

**SAN-401:** Transition to the safe state shall take place when 2-bits
error, an error count overflow or an address error has been detected.
For this purpose, configure the appropriate response in the ECM
accordingly.

**SAN-413:** Upon detection of non-correctable bit error in the local
RAM, a system error exception request will be sent to SEG to generate a
SYSERR (FE-level) exception (if it is enabled).

### Description

This sub-function handles the SYSERR exceptions (after the RBASE / EBASE
Switch - refer to start up sequence).

Note that some errors are configured to generate a SYSERR based on the
contents of the SEGCONT register (see CM110A for details). The design
stores information into back up registers, generates a software reset
and then the “Reset Source Determination” sub-function identifies the
source of the reset and identifies the NTC.

SYSERRs occurring <u>prior</u> to the RTE initialization will result in
an interrupt restarting the FBL.

### Rationale

SYSERR approach was selected over ECM as it seems to be a more direct
response in cases of serious failures. Note that the ECM error out pin
is also configured to go the safe state as another redundant disabling
mechanism; however, no EI or FE interrupts are configured as enabled.

Design assumes that if none of the SEGFLAG bits are set, then the
assumption is an instruction fetch failure.

R7F701311 has 128KB of RAM with a Base address of 0xFEB8 0000 and the
Offset starting at 0x0006 0000.

### Implementation

The SYSERR exception has an offset of 0x010.

#### Event Driven (SysErrIrq)

Registers used

<table>
<colgroup>
<col style="width: 32%" />
<col style="width: 43%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<tbody>
<tr class="odd">
<td rowspan="2"><strong>Register</strong></td>
<td rowspan="2"><strong>Use</strong></td>
<td colspan="2"><strong>Register Access</strong></td>
</tr>
<tr class="even">
<td><strong>SV</strong></td>
<td><strong>UM</strong></td>
</tr>
<tr class="odd">
<td>SEGFLAG (Error Occurrence Retention Register)</td>
<td>Contains bits to indicate the source of the system error.</td>
<td>R/W</td>
<td><p>Read</p>
<p>Only</p></td>
</tr>
<tr class="even">
<td>SEGADDR (Error Address)</td>
<td>Contains the error address information that caused the system
error.</td>
<td>R/W</td>
<td><p>Read</p>
<p>Only</p></td>
</tr>
<tr class="odd">
<td>CF1STEADR0_PE1 (Code Flash 1st Error Address Register)</td>
<td>Register provides information on address of failure – used for debug
purposes</td>
<td>R/W</td>
<td>R/W</td>
</tr>
</tbody>
</table>

*TmpData* = 0

// Determine source of error from the SEGFLAG bits and indicate in
BRAMDAT0

If (SEGVPGF = 1) Then

*TmpSrc* = McuDiagc1.MCUDIAGC_PRPHLBUSGUARD

ElseIf (SEGVCRF = 1) Then

*TmpSrc* = McuDiagc1.MCUDIAGC_INTPRPHLGUARD

ElseIf (SEGTCMF = 1) Then

// Identify bank that failed to get address information from the correct
register

> If (ECCCPU1DEDF0 = 1) Then
>
> // TmpData is the Offset Address of Local RAM ‘OR’ed with Base Addr
> (0xFEB8 0000) and Bank Addr (0x0)

*TmpData* = ((ECCCPU1LR1STEADR0_PE1 \<\< 4) \| 0xFEB8 0000)

Else If (ECCCPU1DEDF1 = 1)

> // TmpData is the Offset Address of Local RAM ‘OR’ed with Base Addr
> (0xFEB8 0000) and Bank Addr (0x4)
>
> *TmpData* = ((ECCCPU1LR1STEADR1_PE1 \<\< 4) \| 0xFEB8 0004)
>
> Else If (ECCCPU1DEDF2 = 1)
>
> // TmpData is the Offset Address of Local RAM ‘OR’ed with Base Addr
> (0xFEB8 0000) and Bank Addr (0x8)
>
> *TmpData* = ((ECCCPU1LR1STEADR2_PE1 \<\< 4) \| 0xFEB8 0008)
>
> Else
>
> // TmpData is the Offset Address of Local RAM ‘OR’ed with Base Addr
> (0xFEB8 0000) and Bank Addr (0xC)
>
> *TmpData* = ((ECCCPU1LR1STEADR3_PE1 \<\< 4) \| 0xFEB8 000C)
>
> EndIf
>
> *TmpSrc* = McuDiagc1.MCUDIAGC_LCLRAMDBLBIT

ElseIf ((SEGROMF = 1) or (SEGVCIF = 1)) Then // Both bits have code
flash ECC

If (CF1STERSTR_PE1 & 0x0000 0004 !=0) Then

> *TmpSrc* = McuDiagc1.MCUDIAGC_ADRPAR

*TmpData* = ECCFLICF1STEADR0_PE1

Else If (CF1STERSTR_PE1 & 0x0000 0002 !=0) Then

> *TmpSrc* = McuDiagc1.MCUDIAGC_CODFLSDBLBIT

*TmpData* = ECCFLICF1STEADR0_PE1

Else

> // Other VCIE cause
>
> *TmpSrc* = McuDiagc1.MCUDIAGC_VCIE

End If

Else

// Assume instruction fetch error drove SYSERR

*TmpSrc* = McuDiagc1.MCUDIAGC_INSTRFETCH

End If

NxtrSwRstFromExcpn (*TmpSrc, TmpData*)

### Reference

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CM101A_ExcpnHndlg_Design/Design/mediax/media/image4.wmf"
style="width:5.98889in;height:4.79861in" />

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CM101A_ExcpnHndlg_Design/Design/mediax/media/image5.wmf"
style="width:5.99306in;height:3.86319in" />

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CM101A_ExcpnHndlg_Design/Design/mediax/media/image6.wmf"
style="width:5.97361in;height:6.75in" />

### Verification Method

**<u>At 2ms rate:</u>**

// Invokes a double bit ECC code flash fault

If ((McuDiagcTest = McuDiagcTestTyp.CODFLSDBLBIT)

> Temp = Read from Code Flash Test Address 0x0100 A8B0 // invokes a
> double bit ECC

McuDiagcTest = McuDiagcTestTyp.NoTest

EndIf

**// Check on section 8.4.2 in SAN for address parity fault injection
options**

**// Need to find other ways to invoke a SYSERR**

## Sub-Function: Exception Handling Routine Floating Point

Return to sub-function list link: Sub-Functions In This Document

### NTCs

None – NTCs are addressed in section 4.21 (Reset Source)

### SAN Linkage

None identified

### Description

This sub-function is used to handle the exceptions configured for the
floating point unit (FPU). Based on the configurations, the handler can
identify / discriminate faults for overflow, divide by zero and invalid
operations.

### Rationale

The FPU “E bit” functionality is a function of the FPU configuration.

Page 173/174 of the software user manual (R01UH0436EJ0100 Rev.1.00)
states - "If the FS bit of the FPSR register is set to 1, an
unimplemented operation exception (E) <u>will not occur under any
circumstances</u>."

Nexteer is setting the FS bit to 1, therefore, there is no need to check
for the “E Bit” failure in the FSPR register. Should it set for some
reason, it will be swept into the “unknown” category.

### Implementation

The Floating Point exception has an offset of 0x070.

#### Event Driven (FpuErrIrq)

Registers used

|              |                                                                                     |                     |        |
|------------------------|------------------------------|---------|---------|
| **Register** | **Use**                                                                             | **Register Access** |        |
|              |                                                                                     | **SV**              | **UM** |
| FPSR         | This register is used to control and monitor the cause of floating point exceptions | R/W                 | No     |
| FPEPC        | This register stores the program counter value where the exception occurs.          | R/W                 | No     |

// Get data relating to the fault

*TmpData* = FPEPC

If (FPSR & 0x0000 4000 != 0) Then

*TmpSrc* = McuDiagc1.MCUDIAGC\_ FPUERRINVLDOPER // Invalid Operation

Else If (FPSR & 0x0000 2000 != 0)

*TmpSrc* = McuDiagc1.MCUDIAGC_FPUERRDIVBYZERO // Divide by Zero

Elseif (FPSR & 0x0000 1000 != 0)

*TmpSrc* = McuDiagc1.MCUDIAGC_FPUERROVF // Overflow

Elseif

*TmpSrc* = McuDiagc1.MCUDIAGC_FPUERRUKWN // Unknown (not expected)

EndIf

NxtrSwRstFromExcpn (*TmpSrc*, *TmpData*)

### Reference

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CM101A_ExcpnHndlg_Design/Design/mediax/media/image7.wmf"
style="width:5.99583in;height:5.78958in" />

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CM101A_ExcpnHndlg_Design/Design/mediax/media/image8.wmf"
style="width:5.63125in;height:8.27708in" />

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CM101A_ExcpnHndlg_Design/Design/mediax/media/image9.wmf"
style="width:5.99792in;height:3.3875in" />

### Verification Method

**NA**

## Sub-Function: Exception Handling Routine Misalignment

Return to sub-function list link: Sub-Functions In This Document

### NTCs

None – NTCs are addressed in section 4.21 (Reset Source)

### SAN Linkage

**SAN-148:** When a MPU violation is detected, the access is not
granted, but the related information such as access type (read, write),
data size, and instruction type are stored in the memory error
information register MEI. The memory error address register is used to
store the address when a MAE (misaligned) or MPU exception occurs. Both
registers **can** be accessed in the CPU supervisor mode only.

### Description

This sub-function handles exceptions generated by a memory misalignment
error.

### Rationale

**TBD**

### Implementation

The memory misalignment exception has an offset of 0x0C0.

#### Event Driven (AlgnErrIrq)

Registers used

<table>
<colgroup>
<col style="width: 26%" />
<col style="width: 35%" />
<col style="width: 18%" />
<col style="width: 9%" />
<col style="width: 9%" />
</colgroup>
<tbody>
<tr class="odd">
<td rowspan="2"><strong>Register</strong></td>
<td rowspan="2"><strong>Use</strong></td>
<td rowspan="2"><strong>Register No. (regID,selID)</strong></td>
<td colspan="2"><strong>Register Access</strong></td>
</tr>
<tr class="even">
<td><strong>SV</strong></td>
<td><strong>UM</strong></td>
</tr>
<tr class="odd">
<td>MEI</td>
<td>Memory error information register – used to indicate if the
misalignment was caused during read or write</td>
<td>SR8, 2</td>
<td>Yes</td>
<td><p>No</p>
<p>(via SAN)</p></td>
</tr>
<tr class="even">
<td>MEA</td>
<td><p>Memory error address register - These bits store an address when
a MAE (misaligning) or MPU violation</p>
<p>occurs.</p></td>
<td>SR6, 2</td>
<td>Yes</td>
<td><p>No</p>
<p>(via SAN)</p></td>
</tr>
</tbody>
</table>

// Determine source of error and indicate in BRAMDAT0

*TmpData* = MEA

If (MEI & 0x0000 0001 = 0x0000 00001) Then

*TmpSrc* = McuDiagc1.MCUDIAGC_ALGNWR

Else

*TmpSrc* = McuDiagc1.MCUDIAGC_ALGNREAD

End If

NxtrSwRstFromExcpn (*TmpSrc*, *TmpData*)

### Reference

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CM101A_ExcpnHndlg_Design/Design/mediax/media/image10.wmf"
style="width:5.99236in;height:7.14792in" />

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CM101A_ExcpnHndlg_Design/Design/mediax/media/image11.wmf"
style="width:5.98889in;height:2.05764in" />

### Verification Method

**NA**

## Sub-Function: Exception Handling Routine Reserved Instruction

Return to sub-function list link: Sub-Functions In This Document

### NTCs

N/A

### SAN Linkage

None

### Description

### Rationale

This is basically an exception generated by processing an illegal opcode
function.

### Implementation

The Reserved Instruction exception has an offset of 0x060.

#### Event Driven (ResdOperIrq)

Registers used

|              |         |                     |        |
|--------------|---------|---------------------|--------|
| **Register** | **Use** | **Register Access** |        |
|              |         | **SV**              | **UM** |
| None         |         |                     |        |

// Identify reset cause and reset

NxtrSwRstFromExcpn (McuDiagc1.MCUDIAGC_RESDOPER, 0)

### Verification Method

N/A

## Sub-Function: Server Routine FENMI PEG

Return to sub-function list link: Sub-Functions In This Document

### NTCs

None – NTCs are addressed in section 4.21 (Reset Source)

### SAN Linkage

**SAN-183:** For PE guard violations, a proper error handling **shall**
be performed. For this the ECM shall be configured accordingly.

### Description

This server function is called by the MCU handler and is responsible for
responding to a PEG (Processor Element Guard) error. The Nexteer design
has this configured in the ECM to be an exception of type FENMI. The
design notes the source of the error (for later use in the reset cause
function), clears the ECM status registers and issues a software reset.

### Rationale

FENMI Interrupts are used to represent serious failures within the
microcontroller or it’s peripherals that are critical to the overall
design. As a result, the Nexteer strategy is to indicate the fault type
in backup memory (data retained through a software reset) and force a
software reset where the reset type is then indicated and the fault is
set (assuming the system can operate to that point).

Note that the function FeNmiPeg is called from the MCU handler.

### Implementation

#### Event Driven (FeNmiPeg)

Registers used

|              |         |                     |        |
|--------------|---------|---------------------|--------|
| **Register** | **Use** | **Register Access** |        |
|              |         | **SV**              | **UM** |
| None         |         |                     |        |

// Identify reset cause and reset

NxtrSwRstFromExcpn(McuDiagc1.MCUDIAGC_PROCRELMGUARD, 0)

### Verification Method

NA

## Sub-Function: Server Routine FENMI SPI 2 Bit ECC Error

Return to sub-function list link: Sub-Functions In This Document

### NTCs

None – NTCs are addressed in section 4.21 (Reset Source)

### SAN Linkage

None

### Description

This server routine is called from the MCU handler and is responsible
for responding to a SPI RAM peripheral 2 Bit ECC Error. The Nexteer
design has this configured in the ECM to be an exception of type FENMI.
The design notes the source of the error (for later use in the reset
cause function), clears the ECM status registers and issues a software
reset.

### Rationale

FENMI Interrupts are used to represent serious failures within the
microcontroller or it’s peripherals that are critical to the overall
design. SPI use in the design applies to several critical functions
(motor position, gate drive and power supply control) thus the FE
designation.

Note that the function FeNmiSpiDblBit is called from the MCU handler.

### Implementation

#### Event Driven (FeNmiSpiDblBit)

Registers used

|                                                       |                                                                                                                                       |                     |        |
|------------------------|------------------------------|---------|---------|
| **Register**                                          | **Use**                                                                                                                               | **Register Access** |        |
|                                                       |                                                                                                                                       | **SV**              | **UM** |
| ECCCSIH0CTL (ECC Control / Status Register for SPI 0) | Indicates a SPI double bit error in SPI 0                                                                                             | Yes                 | Yes    |
| ECCCSIH1CTL (ECC Control / Status Register for SPI 1) | Indicates a SPI double bit error in SPI 1                                                                                             | Yes                 | Yes    |
| ECCCSIH2CTL (ECC Control / Status Register for SPI 2) | Indicates a SPI double bit error in SPI 2. Note that SPI3 is not considered and is assumed the default if 0, 1 or 2 are not detected. | Yes                 | Yes    |

*TmpData* = 0

// Identify which SPI peripheral is at fault (Data0), identify and save
address (Data1)

If (ECCCSIH0ECDEDF0 = 1) Then

*TmpData* = ECCCSIH0EAD0

*TmpSrc* = McuDiagc1.MCUDIAGC_SPIRAMDBLBIT0

Else If (ECCCSIH1ECDEDF0 = 1)

*TmpData* = ECCCSIH1EAD0

*TmpSrc* = McuDiagc1.MCUDIAGC\_ SPIRAMDBLBIT1

Else If (ECCCSIH2ECDEDF0 = 1)

*TmpData* = ECCCSIH2EAD0

*TmpSrc* = McuDiagc1.MCUDIAGC\_ SPIRAMDBLBIT2

Else

*TmpData* = ECCCSIH3EAD0

*TmpSrc* = McuDiagc1.MCUDIAGC\_ SPIRAMDBLBIT3

End If

NxtrSwRstFromExcpn(*TmpSrc*, *TmpData*)

### Reference

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CM101A_ExcpnHndlg_Design/Design/mediax/media/image12.wmf"
style="width:5.78542in;height:8.04722in" />

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CM101A_ExcpnHndlg_Design/Design/mediax/media/image13.wmf"
style="width:5.65486in;height:7.56667in" />

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CM101A_ExcpnHndlg_Design/Design/mediax/media/image14.wmf"
style="width:5.99931in;height:4.89097in" />

### Verification Method

NA

## Sub-Function: Server Routine FENMI DMA Transfer Error

Return to sub-function list link: Sub-Functions In This Document

### NTCs

None – NTCs are addressed in section 4.21 (Reset Source)

### SAN Linkage

**SAN-723:** When a data parity error is detected, a flag will be set in
P-Bus data parity status register APDPERRST_xx (xx stands for the module
name) and an internal error signal is propagated towards ECM. In this
case the MCU should move to safe state.

**SAN-724:** If a data parity error has occurred during DMA transfer, a
DMA transfer error will be notified.

### Description

This server routine is called from the MCU handler and is responsible
for responding to DMA transfer errors. The Nexteer design has this
configured in the ECM to be an exception of type FENMI. The design notes
the source of the error (for later use in the reset cause function),
clears the ECM status registers and issues a software reset.

### Rationale

N/A

### Implementation

#### Event Driven (FeNmiDmaTrf)

Registers used

|              |                                               |                     |        |
|------------------------|------------------------------|---------|---------|
| **Register** | **Use**                                       | **Register Access** |        |
|              |                                               | **SV**              | **UM** |
| DMASSDMACER  | Indicates the status of the two DMAC channels | Yes                 | Yes    |

// Indicate data for reset cause (Data0) and information on the
responsible DMA channel (Data1)

NxtrSwRstFromExcpn(McuDiagc1.MCUDIAGC_DMATRFERR, DMASSDMACER)

### Reference

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CM101A_ExcpnHndlg_Design/Design/mediax/media/image15.wmf"
style="width:5.99375in;height:5.28056in" />

### Verification Method

NA

## Sub-Function: Server Routine FENMI DMA Access Violation Error

Return to sub-function list link: Sub-Functions In This Document

### NTCs

None – NTCs are addressed in section 4.21 (Reset Source)

### SAN Linkage

**SAN-100:** When the CPU makes an illegal access to the global DMA
registers (e.g. access in user mode), then an access violation flag will
be set in the related transfer module and an internal error signal will
be propagated to the ECM to take the proper action.

### Description

This server routine is called from the MCU handler and is responsible
for responding to DMA privileged access errors. The Nexteer design has
this configured in the ECM to be an exception of type FENMI. The design
notes the source of the error (for later use in the reset cause
function), clears the ECM status registers and issues a software reset.

### Rationale

FENMI Interrupts are used to represent serious failures within the
microcontroller or it’s peripherals that are critical to the overall
design. As a result, the Nexteer strategy is to indicate the fault type
in backup memory (data retained through a software reset) and force a
software reset where the reset type is then indicated and the fault is
set (assuming the system can operate to that point).

Note that the function ExcpnHndlgFeNmiDMAREGACSPROTECNERR is called from
the MCU handler.

In future versions of this document we may want to consider using the
registers DM0CMV, DM1CMV and DTSCMV to provide more information when the
fault is triggered. Note that these registers require supervisor mode to
be accessed – note that the exceptions are already be in SV mode.
Initial design will not include them.

### Implementation

#### Event Driven (FeNmiDmaRegAcsProtnErr)

Registers used

|              |                                               |                     |        |
|------------------------|------------------------------|---------|---------|
| **Register** | **Use**                                       | **Register Access** |        |
|              |                                               | **SV**              | **UM** |
| DMASSDMACER  | Indicates the status of the two DMAC channels | Yes                 | Yes    |

// Indicate data for reset cause (Data0) and information on the
responsible DMA channel (Data1)

NxtrSwRstFromExcpn (McuDiagc1.MCUDIAGC_DMAREGACSPROTECNERR, DMASSDMACER)

### Reference

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CM101A_ExcpnHndlg_Design/Design/mediax/media/image15.wmf"
style="width:5.99375in;height:5.28056in" />

### Verification Method

NA

## Sub-Function: Server Routine FENMI ECM Master/Checker Compare

Return to sub-function list link: Sub-Functions In This Document

### NTCs

None – NTCs are addressed in section 4.21 (Reset Source)

### SAN Linkage

**SAN-656:** If there is a mismatch between ECM master and checker an
ECM compare error will be set in the ECMmESSTR0/1 register. In that
case, the safe state shall be entered.

### Description

This server routine is called from the MCU handler and is responsible
for responding errors in which the master and checker compare error. The
Nexteer design has this configured in the ECM to be an exception of type
FENMI. The design notes the source of the error (for later use in the
reset cause function), clears the ECM status registers and issues a
software reset.

### Rationale

N/A

### Implementation

#### Event Driven (FeNmiEcmMstChkrCmp)

Registers used

|              |         |                     |        |
|--------------|---------|---------------------|--------|
| **Register** | **Use** | **Register Access** |        |
|              |         | **SV**              | **UM** |
| None         |         |                     |        |

// Identify reset cause and reset

NxtrSwRstFromExcpn (McuDiagc1.MCUDIAGC_ECMMSTCHKRERR, 0)

### Verification Method

**NA**

## Sub-Function: Server Routine FENMI Watchdog 

### NTCs

None – NTCs are addressed in section 4.21 (Reset Source)

### SAN Linkage

None

### Description

This server routine is called from the MCU handler and is responsible
for responding internal watchdog failures. Note that the design is
intended to use this server function to also sort to see if the timing
failure can be further discriminated to a watchdog, program flow, alive
monitor or a deadline monitor failure It is assumed that the MCU will
provide the capability to allow Nexteer to select / direct unused
features in the design to this routine.

The Nexteer design has configured in the ECM to be an exception of type
FENMI without a Reset. The design notes the source of the error (for
later use in the reset cause function), clears the ECM status registers
and issues a software reset.

### Rationale

The SAN recommends a reset when using the ECM for watchdog failures. The
Nexteer design will defeat the reset and replace the functionality with
a software reset – this is to allow the capability to store parse the
fault into watchdog, program flow, alive monitoring and deadline
monitoring and provide more information for debug purposes. The ECM
configuration as a reset would not allow this to be done.

Note that the function FeNmiWdg is called from the MCU handler.

### Implementation

#### Event Driven (FeNmiWdg)

Registers used

|                                                                |                                                                                                                                                           |                     |        |
|------------------------|------------------------------|---------|---------|
| **Register**                                                   | **Use**                                                                                                                                                   | **Register Access** |        |
|                                                                |                                                                                                                                                           | **SV**              | **UM** |
| EntityStatusGRef (not a register, but key part of this design) | This is a structure contained within the AutoSAR module that will provide the means to discriminate different failures that result in a watchdog timeout. | NA                  | NA     |

<u>Pseudo Code</u>

*TmpSrc* = McuDiagc1.MCUDIAGC_FENMIWDG

*TmpData* = 0

For Each SupervisedEntityID

If (EntityStatusGRef🡪ProgramFlowViolationCnt != 0) Then // Program Flow

*TmpSrc* = McuDiagc1.MCUDIAGC_FENMIPROGFLOW

*TmpData* = SupervisedEntityID

End the For Loop

ElseIf (EntityStatusGRef🡪FailedSupervisionRefCycles !=0) // Alive
Monitor

*TmpSrc* = McuDiagc1.MCUDIAGC_FENMIALVMONR

*TmpData* = SupervisedEntityID

End the For Loop

ElseIf (EntityStatusGRef🡪DeadlineViolationCnt !=0) // Deadline Monitor

*TmpSrc* = McuDiagc1.MCUDIAGC_FENMIDEADLINEMONR

*TmpData* = SupervisedEntityID

End the For Loop

Else

End If

End For

// Store data for reset cause use and reset

NxtrSwRstFromExcpn (*TmpSrc*, *TmpData*)

### Verification Method

**NA**

## Sub-Function: Server Routine FENMI DTS Double Bit ECC 

Return to sub-function list link: Sub-Functions In This Document

### NTCs

None – NTCs are addressed in section 4.21 (Reset Source)

### SAN Linkage

None

### Description

This server routine is called from the MCU handler and is responsible
for responding to DTS ECC failures.

The Nexteer design has configured this in the ECM to be an exception of
type FENMI without a Reset. The design notes the source of the error
(for later use in the reset cause function), clears the ECM status
registers and issues a software reset.

### Rationale

Note that the function FeNmiDts is called from the MCU handler.

### Implementation

#### Event Driven (FeNmiDtsDblBit)

Registers used

|              |         |                     |        |
|--------------|---------|---------------------|--------|
| **Register** | **Use** | **Register Access** |        |
|              |         | **SV**              | **UM** |
| None         |         |                     |        |

<u>Pseudo Code</u>

// Identify reset cause and reset

NxtrSwRstFromExcpn (McuDiagc1.MCUDIAGC_DTSDBLBIT, 0)

### Verification Method

**NA**

## Sub Function: Server Routine Process Unknown Exception Error

### NTCs

None – NTCs are addressed in section 4.21 (Reset Source)

### SAN Linkage

None

### Description

The Process Unknown Exception Error needs to be called when the OS
detects an unknown exception.

### Rationale

### Implementation

#### Event Driven (ProcUkwnExcpnErr)

// Perform software reset from exception and pass appropriate arguments

NxtrSwRstFromExcpn(MCUDIAGC_UKWNEXCPN, McuDiagcData1_Arg)

<span id="__RefHeading___Toc440963618"
class="anchor"></span>Verification Method

**NA**

## Sub-Function: Server Routine Process Memory Protection Unit Exception Error

### NTCs

None – NTCs are addressed in section 4.21 (Reset Source)

### SAN Linkage

None

### Description

The Process Memory Protection Unit Exception Error needs to be called
when the OS detects a memory protection violation.

<span id="__RefHeading___Toc440963623" class="anchor"></span>Rationale

### Implementation

#### Event Driven (ProcMpuExcpnErr)

// Perform software reset from exception and pass appropriate arguments

NxtrSwRstFromExcpn(MCUDIAGC_MPU, McuDiagcData1_Arg)

### Verification Method

**NA**

## Sub-Function: Server Routine Process Privileged Instruction Exception Error

### NTCs

None – NTCs are addressed in section 4.21 (Reset Source)

### SAN Linkage

None

### Description

The Process Privileged Instruction Exception Error needs to be called
when the OS detects a protection violation.

### Rationale

### Implementation

#### Event Driven (ProcPrvlgdInstrExcpnErr)

// Perform software reset from exception and pass appropriate arguments

NxtrSwRstFromExcpn(MCUDIAGC_PRVLGDINSTREXCPN, McuDiagcData1_Arg)

### Verification Method

**NA**

## Sub-Function: Server Routine Process Permanent Os Error

### NTCs

None – NTCs are addressed in section 4.21 (Reset Source)

### SAN Linkage

None

### Description

The Process Permanent Os Error needs to be called when the OS detects a
fatal, permanent failure.

### Rationale

### Implementation

#### Event Driven (ProcPrmntOsErr)

// Perform software reset from exception and pass appropriate arguments

NxtrSwRstFromExcpn(MCUDIAGC_PRMNTOSERR, McuDiagcData1_Arg)

### Verification Method

**NA**

## Sub-Function: Server Routine Process Non Critical Os Error

### NTCs

None – NTCs are addressed in section 4.21 (Reset Source)

### SAN Linkage

None

### Description

The Process Non Critical Os Error needs to be called when the OS detects
a non-fatal failure.

### Rationale

### Implementation

#### Event Driven (ProcNonCritOsErr)

// Update error code variable that is polled in periodic function

ExcpnHndlgOsErrCod_C = McuDiagcData1_Arg

### Verification Method

**NA**

## Periodic (ExcpnHndlgPer1)

\*\* NOTE: variable ExcpnHndlgOsErrCod must reside in global shared
memory \*\*

If (ExcpnHndlgOsErrCod != 0x0000) then

// Set code for non-fatal OS error – Error Code is on the data
ExcpnHndlgOsErrCod

SetNtcSts(NtcNr1.NTCNR_0x031, 1, NtcSts1.NTCSTS_FAILD, 0)

End If

### Verification Method

**NA**

## Sub-Function: Server Routine Shutdown Hook 

Call EcuM_Shutdown()

## Sub-Function: Exception Handling Routine EIINT

Return to sub-function list link: Sub-Functions In This Document

It is assumed that the MCU configuration will directly provide a
client/server call to the necessary FDDs to accomplish their tasks. It
would be redundant to place them within this document only to call out
another document, so this is the chosen approach.

Please refer to other microcontroller diagnostic FDDs to see their
specific exception handler functionality.

## Sub-Function: Reset Source Determination

Return to sub-function list link: Sub-Functions In This Document

### NTCs

003.0 Code Flash ECC Single Bit (Hard Fault)

003.1 Code Flash ECC Double Bit Detection

003.2 Code Flash ECC Address Parity Fault

010.0 MBIST Startup Test Failure

013.0 Local RAM ECC Single Bit (Hard Fault)

013.1 Local RAM ECC Double Bit (Hard Fault)

016.1 DTS ECC Double Bit (Hard Fault)

017.1 CSHI0 RAM ECC Double Bit (Hard Fault)

018.1 CSHI1 RAM ECC Double Bit (Hard Fault)

019.1 CSHI2 RAM ECC Double Bit (Hard Fault)

01A.1 CSHI3 RAM ECC Double Bit (Hard Fault)

021.0 BIST Code 2-Bit ECC Failure

021.2 LBIST Startup Test Failure

021.4 BIST Not Complete

021.5 CPU Lock Step Error Forcing Startup Test Failure

021.6 DMA Lock Step Error Forcing Startup Test Failure

022.0 Lock Step Compare Fault

022.1 System VCIE Bit Error

022.2 Reserved Instruction (Illegal Op Code) Fault

022.3 Memory Misalignment - Read

022.4 Memory Misalignment - Write

022.5 Instruction Fetch Error

025.0 Data Protection Violation (MDP Exception)

025.1 Execution Protection Violation (MIP Exception)

026.0 ECM Status Bit Set Prior to ECM Init

026.2ECM Startup Master nERROR Output Control Fault

026.3 ECM Startup Checker nERROR Output Control Fault

026.7 ECM Runtime Master-Checker Compare Fault

028.1 FPU Invalid Operation (V Bit)

028.2 FPU Divide by Zero (Z Bit)

028.3 FPUOverflow (O Bit)

028.4 FPU Unknown Error

029.0 Unknown Reset Reason

029.1 Unknown ECM Reset Reason

029.4 Unknown Software Reset

029.5 Failed Backup RAM Read Write Test

029.6 FBL Pre-OS Startup Exception

029.7 Corrupt Start up / Reset Information

02A.0 Program Flow

02A.1 Deadline Monitoring

02A.2 Alive Monitoring

02C.0 Watchdog Timeout

02D.1 PEG Runtime Fault

02D.3 IPG RunTime Fault

02D.5 PBG Runtime Fault

030.0 Operating System Fatal Fault

030.1 Unhandled Exception

031.0 Operating System Non-Fatal Fault

036.0 DMA Transfer Error

036.1 DMA Register Access Protection Violation

048.0 CVM Over Voltage Startup Test Failure

048.1 CVM Under Voltage Startup Test Failure

049.0 Internal CVM Over Voltage Monitor Fault

049.1 Internal CVM Under Voltage Monitor Fault

049.7 External Over Voltage Monitor Fault

### SAN Linkage

**SAN-621:** Upon detection of under/overvoltage of the core power
supply, the signal at the CVMOUT pin changes its state to low and a
dedicated flag will be set in the CVMF register. It is also possible to
generate a reset if the software has enabled it. In that case,
transition the MCU into the safe state **shall** be entered.

**SAN-1024:** As the usage of backup registers is strongly application
dependents, the user should judge whether or not to apply the proposed
write verify check. Moreover, if the data retained in the back-up
register will be frequently used in the safety related application, then
the contain should be moved to LRAM as it is protected by ECC and thus
provide a high fault coverage.

**SAN-1094:** As the usage of backup registers is strongly application
dependents, the user should judge whether or not to apply the proposed
write verify check. Moreover, if the data retained in the back-up
register will be frequently used in the safety related application, then
the contain should be moved to LRAM as it is protected by ECC and thus
provide a high fault coverage.

**SAN-1096:** Detected failures during the execution of the test shall
be handled at application level.

### Description

This function processes information from pre-OS tests and resets to
determine the cause of anything unexpected and log the correct Nexteer
Trouble Code. Backup RAM data is used to provide this information to the
function.

### Rationale

In order to log Nexteer Trouble Code information, the Diagnostic Manager
must be initialized prior to setting or clearing NTCs.

### Implementation

#### Initialization (ExcpnHndlgInit2)

SetNtcSts(NtcNr1.NTCNR_0x003, 0, NtcSts1.NTCSTS_PASSD, 0)

SetNtcSts(NtcNr1.NTCNR_0x010, 0, NtcSts1.NTCSTS_PASSD, 0)

SetNtcSts(NtcNr1.NTCNR_0x013, 0, NtcSts1.NTCSTS_PASSD, 0)

SetNtcSts(NtcNr1.NTCNR_0x016, 0, NtcSts1.NTCSTS_PASSD, 0)

SetNtcSts(NtcNr1.NTCNR_0x017, 0, NtcSts1.NTCSTS_PASSD, 0)

SetNtcSts(NtcNr1.NTCNR_0x018, 0, NtcSts1.NTCSTS_PASSD, 0)

SetNtcSts(NtcNr1.NTCNR_0x019, 0, NtcSts1.NTCSTS_PASSD, 0)

SetNtcSts(NtcNr1.NTCNR_0x01A, 0, NtcSts1.NTCSTS_PASSD, 0)

SetNtcSts(NtcNr1.NTCNR_0x021, 0, NtcSts1.NTCSTS_PASSD, 0)

SetNtcSts(NtcNr1.NTCNR_0x022, 0, NtcSts1.NTCSTS_PASSD, 0)

SetNtcSts(NtcNr1.NTCNR_0x025, 0, NtcSts1.NTCSTS_PASSD, 0)

SetNtcSts(NtcNr1.NTCNR_0x026, 0, NtcSts1.NTCSTS_PASSD, 0)

SetNtcSts(NtcNr1.NTCNR_0x028, 0, NtcSts1.NTCSTS_PASSD, 0)

SetNtcSts(NtcNr1.NTCNR_0x029, 0, NtcSts1.NTCSTS_PASSD, 0)

SetNtcSts(NtcNr1.NTCNR_0x02A, 0, NtcSts1.NTCSTS_PASSD, 0)

SetNtcSts(NtcNr1.NTCNR_0x02C, 0, NtcSts1.NTCSTS_PASSD, 0)

SetNtcSts(NtcNr1.NTCNR_0x02D, 0, NtcSts1.NTCSTS_PASSD, 0)

SetNtcSts(NtcNr1.NTCNR_0x030, 0, NtcSts1.NTCSTS_PASSD, 0)

SetNtcSts(NtcNr1.NTCNR_0x031, 0, NtcSts1.NTCSTS_PASSD, 0)

SetNtcSts(NtcNr1.NTCNR_0x036, 0, NtcSts1.NTCSTS_PASSD, 0)

SetNtcSts(NtcNr1.NTCNR_0x048, 0, NtcSts1.NTCSTS_PASSD, 0)

SetNtcSts(NtcNr1.NTCNR_0x049, 0, NtcSts1.NTCSTS_PASSD, 0)

// Confirm state of backup data is valid

If (((BRAMDAT0 & 0xFFFF 0000) \>\> 16) XOR (BRAMDAT0 & 0x0000 FFFF)) !=
0x0000 FFFF) Then

// Set fault – BRAMDAT0 data is corrupt and cannot be trusted

SetNtcSts(NtcNr1.NTCNR_0x029, 128, NtcSts1.NTCSTS_FAILD, 0)

Else If ((BRAMDAT0 = McuDiagc1.MCUDIAGC_PWRONRST) or (BRAMDAT0 =
McuDiagc1.MCUDIAGC_FLSPROGMCMPL)) Then

// No checks needed – normal power on start up or flash programming
event

Else If ((SYSBSEQ0ST.DEBUGMODE = 1) AND (SYSBSEQ0STB. DEBUGMODEB = 0))

// No checks needed in debug mode

Else If (BRAMDAT0 = McuDiagc1.MCUDIAGC_ECMRST)

ProcEcmRst() // Reset from ECM

ElseIf (BRAMDAT0 = McuDiagc1.MCUDIAGC_PINRST)

ProcPinRst() // Reset from External Pin (Power Supply)

ElseIf (BRAMDAT0 = McuDiagc1.MCUDIAGC_COREVLTGMONRHI) // Overvoltage
internal to uC

SetNtcSts(NtcNr1.NTCNR_0x049, 1, NtcSts1.NTCSTS_FAILD, 0)

ElseIf (BRAMDAT0 = McuDiagc1.MCUDIAGC_COREVLTGMONRLO) // Low voltage
internal to uC

SetNtcSts(NtcNr1.NTCNR_0x049, 2, NtcSts1.NTCSTS_FAILD, 0)

Else

ProcStrtUpOrSwRst() // Check for start-up, non-reset faults

End If

#### FunctionCall ProcEcmRst

//Check for lock step fault in either core

// By design, lock step is the only ECM fault resulting in a reset -
confirm

If ((ECMMSSE001 = 1) or (ECMCSSE001 = 1)) Then

// Set lock step fault

SetNtcSts(NtcNr1.NTCNR_0x022, 1, NtcSts1.NTCSTS_FAILD, 0)

Else

// Set unknown ECM reset fault

SetNtcSts(NtcNr1.NTCNR_0x029, 2, NtcSts1.NTCSTS_FAILD, 0)

End If

// Clear all the bits of ECMmESSTR0

ECMESSTC0_Desired = 0xFDFF DFF3;

WrProtdRegEcm_u32 (ECMESSTC0_Desired, Address of ECMESSTC0);

// Clear all the bits of ECMmESSTR1

ECMESSTC1_Desired = 0x6000 07F7;

WrProtdRegEcm_u32 (ECMESSTC1_Desired, Address of ECMESSTC1);

#### FunctionCall ProcStrtUpOrSwRst

Switch: BRAMDAT0

// Pre-OS failures, (non-sw reset)

> Case: McuDiagc1.MCUDIAGC_MEMBISTERR
>
> SetNtcSts(NtcNr1.NTCNR_0x010, 1, NtcSts1.NTCSTS_FAILD, 0) // MBIST
> Proof
>
> Break

Case: McuDiagc1.MCUDIAGC_BIST2BITERR

SetNtcSts(NtcNr1.NTCNR_0x021, 1, NtcSts1.NTCSTS_FAILD, 0) //BIST 2 bit
ECC

Break

Case: McuDiagc1.MCUDIAGC_LOGLBISTERR

> SetNtcSts(NtcNr1.NTCNR_0x021, 4, NtcSts1.NTCSTS_FAILD, 0) //LBIST
> Proof
>
> Break

Case: McuDiagc1.MCUDIAGC_BISTNOTCMPLERR

> SetNtcSts(NtcNr1.NTCNR_0x021, 16, NtcSts1.NTCSTS_FAILD, 0) //BIST not
> complete
>
> Break
>
> Case: McuDiagc1.MCUDIAGC_CPULOCKSTEPERR
>
> SetNtcSts(NtcNr1.NTCNR_0x021, 32, NtcSts1.NTCSTS_FAILD, 0) //CPU Lock
> Step Proof
>
> Break

Case: McuDiagc1.MCUDIAGC_DMALOCKSTEPERR

> SetNtcSts(NtcNr1.NTCNR_0x021, 64, NtcSts1.NTCSTS_FAILD, 0) //DMA Lock
> Step Proof
>
> Break

Case: McuDiagc1. MCUDIAGC_ECMSTSSTRTUPFLT

> SetNtcSts(NtcNr1.NTCNR_0x026, 1, NtcSts1.NTCSTS_FAILD, 0) // ECM
> Status Prob
>
> Break
>
> Case: McuDiagc1.MCUDIAGC_MSTERROUTPCTRLFLT
>
> SetNtcSts(NtcNr1.NTCNR_0x026, 4, NtcSts1.NTCSTS_FAILD, 0) //Master
> Control Proof
>
> Break

Case: McuDiagc1.MCUDIAGC_CHKRERROUTPCTRLFLT

SetNtcSts(NtcNr1.NTCNR_0x026, 8, NtcSts1.NTCSTS_FAILD, 0) //Checker
Control Proof

Break

Case: McuDiagc1. MCUDIAGC_BACKUPRAMTSTFAILR

> SetNtcSts(NtcNr1.NTCNR_0x029, 32, NtcSts1.NTCSTS_FAILD, 0) //Back-Up
> Test Fail
>
> Break
>
> Case: McuDiagc1.MCUDIAGC_PREOSEXCPN
>
> SetNtcSts(NtcNr1.NTCNR_0x029, 64, NtcSts1.NTCSTS_FAILD, 0) //Pre-OS
> Exception
>
> Break

Case: McuDiagc1.MCUDIAGC_STRTUPCOREVLTGMONROVER

> SetNtcSts(NtcNr1.NTCNR_0x048, 1, NtcSts1.NTCSTS_FAILD, 0) //CVM OV
> Proof
>
> Break
>
> Case: McuDiagc1.MCUDIAGC_STRTUPCOREVLTGMONRUNDER
>
> SetNtcSts(NtcNr1.NTCNR_0x048, 2, NtcSts1.NTCSTS_FAILD, 0) //CVM UV
> Proof
>
> Break

Case: McuDiagc1.MCUDIAGC_RSTUKWN

SetNtcSts(NtcNr1.NTCNR_0x029, 1, NtcSts1.NTCSTS_FAILD, 0) // Unknown Rst
to FBL

Break

// Software Resets

Case: McuDiagc1.MCUDIAGC_CODFLSSNGBITHARDFLT

SetNtcSts(NtcNr1.NTCNR_0x003, 1, NtcSts1.NTCSTS_FAILD, 0)

> Break

Case: McuDiagc1.MCUDIAGC_CODFLSDBLBIT

SetNtcSts(NtcNr1.NTCNR_0x003, 2, NtcSts1.NTCSTS_FAILD, 0)

> Break

Case: McuDiagc1.MCUDIAGC_ADRPAR

> SetNtcSts(NtcNr1.NTCNR_0x003, 4, NtcSts1.NTCSTS_FAILD, 0)
>
> Break

Case: McuDiagc1. MCUDIAGC_LCLRAMECCSNGBITHARDFAILR

SetNtcSts(NtcNr1.NTCNR_0x013, 1, NtcSts1.NTCSTS_FAILD, 0)

> Break

Case: McuDiagc1.MCUDIAGC_LCLRAMDBLBIT

SetNtcSts(NtcNr1.NTCNR_0x013, 2, NtcSts1.NTCSTS_FAILD, 0)

> Break

Case: McuDiagc1.MCUDIAGC_DTSDBLBIT

SetNtcSts(NtcNr1.NTCNR_0x016, 2, NtcSts1.NTCSTS_FAILD, 0)

> Break

Case: McuDiagc1.MCUDIAGC_SPIRAMDBLBIT0

> SetNtcSts(NtcNr1.NTCNR_0x017, 2, NtcSts1.NTCSTS_FAILD, 0)
>
> Break

Case: McuDiagc1.MCUDIAGC_SPIRAMDBLBIT1

> SetNtcSts(NtcNr1.NTCNR_0x018, 2, NtcSts1.NTCSTS_FAILD, 0)
>
> Break

Case: McuDiagc1.MCUDIAGC_SPIRAMDBLBIT2

> SetNtcSts(NtcNr1.NTCNR_0x019, 2, NtcSts1.NTCSTS_FAILD, 0)
>
> Break

Case: McuDiagc1.MCUDIAGC_SPIRAMDBLBIT3

> SetNtcSts(NtcNr1.NTCNR_0x01A, 2, NtcSts1.NTCSTS_FAILD, 0)
>
> Break

Case: McuDiagc1.MCUDIAGC_VCIE

SetNtcSts(NtcNr1.NTCNR_0x022, 2, NtcSts1.NTCSTS_FAILD, 0)

> Break

Case: McuDiagc1.MCUDIAGC_RESDOPER

SetNtcSts(NtcNr1.NTCNR_0x022, 4, NtcSts1.NTCSTS_FAILD, 0)

Break

Case: McuDiagc1.MCUDIAGC_ALGNREAD

SetNtcSts(NtcNr1.NTCNR_0x022, 8, NtcSts1.NTCSTS_FAILD, 0)

Break

Case: McuDiagc1.MCUDIAGC_ALGNWR

SetNtcSts(NtcNr1.NTCNR_0x022, 16, NtcSts1.NTCSTS_FAILD, 0)

> Break

Case: McuDiagc1.MCUDIAGC_INSTRFETCH

SetNtcSts(NtcNr1.NTCNR_0x022, 32, NtcSts1.NTCSTS_FAILD, 0)

Break

Case: McuDiagc1.MCUDIAGC\_ MPU

SetNtcSts(NtcNr1.NTCNR_0x025, 1, NtcSts1.NTCSTS_FAILD, 0)

Break

Case: McuDiagc1.MCUDIAGC\_ PRVLGDINSTREXCPN

SetNtcSts(NtcNr1.NTCNR_0x025, 2, NtcSts1.NTCSTS_FAILD, 0)

Break

Case: McuDiagc1.MCUDIAGC\_ ECMMSTCHKRERR

SetNtcSts(NtcNr1.NTCNR_0x026, 128, NtcSts1.NTCSTS_FAILD, 0)

Break

Case: McuDiagc1.MCUDIAGC_FPUERRINVLDOPER

> SetNtcSts(NtcNr1.NTCNR_0x028, 2, NtcSts1.NTCSTS_FAILD, 0)
>
> Break

Case: McuDiagc1.MCUDIAGC_FPUERRDIVBYZERO

> SetNtcSts(NtcNr1.NTCNR_0x028, 4, NtcSts1.NTCSTS_FAILD, 0)
>
> Break

Case: McuDiagc1.MCUDIAGC_FPUERROVF

> SetNtcSts(NtcNr1.NTCNR_0x028, 8, NtcSts1.NTCSTS_FAILD, 0)
>
> Break

Case: McuDiagc1.MCUDIAGC_FPUERRUKWN

> SetNtcSts(NtcNr1.NTCNR_0x028, 16, NtcSts1.NTCSTS_FAILD, 0)
>
> Break

Case: McuDiagc1.MCUDIAGC_FENMIPROGFLOW

SetNtcSts(NtcNr1.NTCNR_0x02A, 1, NtcSts1.NTCSTS_FAILD, 0)

Break

Case: McuDiagc1.MCUDIAGC_FENMIDEADLINEMONR

SetNtcSts(NtcNr1.NTCNR_0x02A, 2, NtcSts1.NTCSTS_FAILD, 0)

Break

Case: McuDiagc1.MCUDIAGC_FENMIALVMONR

SetNtcSts(NtcNr1.NTCNR_0x02A, 4, NtcSts1.NTCSTS_FAILD, 0)

Break

Case: McuDiagc1.MCUDIAGC_FENMIWDG

SetNtcSts(NtcNr1.NTCNR_0x02C, 1, NtcSts1.NTCSTS_FAILD, 0)

Break

Case: McuDiagc1.MCUDIAGC_PROCRELMGUARD

SetNtcSts(NtcNr1.NTCNR_0x02D, 2, NtcSts1.NTCSTS_FAILD, 0)

Break

Case: McuDiagc1.MCUDIAGC_INTPRPHLGUARD

SetNtcSts(NtcNr1.NTCNR_0x02D, 8, NtcSts1.NTCSTS_FAILD, 0)

Break

Case: McuDiagc1.MCUDIAGC_PRPHLBUSGUARD

SetNtcSts(NtcNr1.NTCNR_0x02D, 32, NtcSts1.NTCSTS_FAILD, 0)

Break

Case: McuDiagc1.MCUDIAGC_PRMNTOSERR

SetNtcSts(NtcNr1.NTCNR_0x030, 1, NtcSts1.NTCSTS_FAILD, 0)

Break

Case: McuDiagc1.MCUDIAGC_UKWNEXCPN

SetNtcSts(NtcNr1.NTCNR_0x030, 2, NtcSts1.NTCSTS_FAILD, 0)

Break

Case: McuDiagc1.MCUDIAGC_DMATRFERR

SetNtcSts(NtcNr1.NTCNR_0x036, 1, NtcSts1.NTCSTS_FAILD, 0)

Break

Case: McuDiagc1.MCUDIAGC_DMAREGACSPROTECNERR

SetNtcSts(NtcNr1.NTCNR_0x036, 2, NtcSts1.NTCSTS_FAILD, 0)

Break

Default:

SetNtcSts(NtcNr1.NTCNR_0x029, 16, NtcSts1.NTCSTS_FAILD, 0) // unknown SW
Reset

Break

End Switch

#### FunctionCall ProcPinRst

SetNtcSts(NtcNr1.NTCNR_0x049, 128, NtcSts1.NTCSTS_FAILD, 0) // External
Pin Reset

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/CM101A_ExcpnHndlg_Design/Design/mediax/media/image16.wmf"
style="width:5.99722in;height:3.4125in" />

### Verification Method

NA

# Special Functions

For this design, some special functions are used to identify the first
failure of data and respond. Once data is changed from its known, good
states (power on reset or flash programming complete) the BRAMDAT0 will
not be updated until a valid power up process occurs or a flash program
event is requested.

Data 1 is ONLY updated by the reset cause in the case of a back-up
register corruption. This is done to not “lose” data following an NTC
event.

// SetMcuDiagcIdnData(Microcontroller Diagnostic Identification Data)

SetMcuDiagcIdnData (McuDiagcData0, McuDiagcData1)

> // Update data if different from PwrOnRst or FlsProgmCmpl – OR if
> flash prog is requested
>
> If ((McuDiagcData0 = McuDiagc1.MCUDIAGC_FLSPROGMREQ) Or
>
> (BRAMDAT0 = McuDiagc1.MCUDIAGC_PWRONRST) Or
>
> (BRAMDAT0 = McuDiagc1.MCUDIAGC_FLSPROGMCMPL)) Then
>
> BRAMDAT0 = McuDiagcData0
>
> BRAMDAT1 = McuDiagcData1
>
> End If

Done

# Revision Record & Change Approval

|         |            |                       |         |                                                       |
|------|----------|----------|-------|----------------------------------------|
| **Rev** | **Date**   | **Change Control \#** | **Drw** | **Change Description**                                |
| 1.0.0   | 10/20/2015 | EA4#1831              | MK      | Initial Release                                       |
| 1.1.0   | 11/19/2015 | EA4#2536              | SK      | Removed CVMREN Initialization. Refer Anomaly EA4#2522 |
| 1.2.0   | 01/08/16   | EA4#3186              | LWW     | Replaced Os Protection and Error Hook                 |
|         |            |                       |         |                                                       |
|         |            |                       |         |                                                       |
|         |            |                       |         |                                                       |
|         |            |                       |         |                                                       |
|         |            |                       |         |                                                       |

{% endraw %}