---
layout: default
title: AR350A_ImcArbn_FDD
nav_order: 1
parent: Component Design
---
{% raw %}
**Inter-Micro Communication Arbitration**

**FDD \#AR350A**

.

1\. High Level Description 4

2\. Function I/O 5

2.1. Input Description 5

2.2. Output Description 5

2.3. Sub-Function Data Flow 6

2.3.1. Imc Arbitration Transmit side data flow 6

2.3.2. Imc Arbitration Receive side data flow 6

2.3.3. Rolling Counter Handling 7

3\. Design Rationale and Assumptions 14

4\. Sub-Functions 15

4.1. Sub-Function: ImcArbnInit1 15

4.1.1. Hardware Related Design 15

4.1.2. Software Related Design 15

4.2. Sub-Function: ImcArbnTx 16

4.2.1. Hardware Related Design 16

4.2.2. Software Related Design 16

4.3. Sub-Function: ImcArbnPer1 19

4.3.1. Hardware Related Design 19

4.3.2. Software Related Design 19

4.4. Sub-Function: ImcArbnPer2 19

4.4.1. Hardware Related Design 19

4.4.2. Software Related Design 20

4.5. Sub-Function: ImcArbnPer3 20

4.5.1. Hardware Related Design 20

4.5.2. Software Related Design 20

4.6. Sub-Function: ImcArbnRx 21

4.6.1. Hardware Related Design 21

4.6.2. Software Related Design 21

4.7. Sub-Function: ImcArbnPer4 25

4.7.1. Hardware Related Design 25

4.7.2. Software Related Design 25

4.8. Sub-Function: ImcArbnPer5 26

4.8.1. Hardware Related Design 26

4.8.2. Software Related Design 26

4.9. Sub-Function: ImcArbnPer6 27

4.9.1. Hardware Related Design 27

4.9.2. Software Related Design 27

4.10. Sub-Function: SetRxSigGroup 29

4.10.1. Hardware Related Design 29

4.10.2. Software Related Design 29

4.11. Sub-Function: GetTxSigGroup 31

4.11.1. Hardware Related Design 31

4.11.2. Software Related Design 31

4.12. Sub-Function: GetTxRateGroup 33

4.12.1. Hardware Related Design 33

4.12.2. Software Related Design 33

4.13. Sub-Function: GetSigImcDataExtdSts\_\<DATA_TYPE\> 35

4.13.1. Hardware Related Design 35

4.13.2. Software Related Design 35

4.14. Sub-Function: GetSigImcData\_\<DATA_TYPE\> 37

4.14.1. Hardware Related Design 37

4.14.2. Software Related Design 37

4.15. Sub-Function: RxFrmVldChk 38

4.15.1. Hardware Related Design 38

4.15.2. Software Related Design 38

4.16. Sub-Function: ImcChResyncHndlg 42

4.16.1. Hardware Related Design 42

4.16.2. Software Related Design 42

4.17. Sub-Function: CreatSigGroupData 43

4.17.1. Hardware Related Design 43

4.17.2. Software Related Design 43

4.18. Sub-Function: DecodSigGroupData 44

4.18.1. Hardware Related Design 44

4.18.2. Software Related Design 44

4.19. Sub-Function: GetBitMask 46

4.19.1. Hardware Related Design 46

4.19.2. Software Related Design 46

4.20. Sub-Function: GetImcFltParamByte 47

4.20.1. Hardware Related Design 47

4.20.2. Software Related Design 47

4.21. Sub-Function: VldtRollgCntr 49

4.21.1. Hardware Related Design 49

4.21.2. Software Related Design 49

4.22. Sub-Function: VldtRollgCntrAlg 51

4.22.1. Hardware Related Design 51

4.22.2. Software Related Design 51

4.23. Sub-Function: RollgCntrSeqChk 54

4.23.1. Hardware Related Design 54

4.23.2. Software Related Design 54

4.24. Sub-Function: NoDataHndlg 55

4.24.1. Hardware Related Design 55

4.24.2. Software Related Design 55

4.25. Sub-Function: EvlSigGroupNeverRxdMissSts 57

4.25.1. Hardware Related Design 57

4.25.2. Software Related Design 57

4.26. Sub-Function: OvrdSigStsDurgStrtUp 59

4.26.1. Hardware Related Design 59

4.26.2. Software Related Design 59

4.27. Sub-Function: GetImcSigSts 60

4.27.1. Hardware Related Design 60

4.27.2. Software Related Design 60

4.28. Sub-Function: NoDataRxd 62

4.28.1. Hardware Related Design 62

4.28.2. Software Related Design 62

5\. Timing / Execution Constraints 63

5.1. Rationale / Comments 63

5.2. Rates and State Execution 63

6\. Serial Communications Interfaces 63

7\. Additional Information 63

7.1. Imc Arbitration – Configuration 63

7.1.1. Hardware Related Design 63

7.1.2. Software Related Design 63

7.2. Imc Signal Mapping for Receiving FDDs 69

7.2.1. Hardware Related Design 69

7.2.2. Software Related Design 69

7.3. Enumerations - Signal Status, Extended Signal Status and Signal
Source 69

7.3.1. Hardware Related Design 69

7.3.2. Software Related Design 69

8\. Revision Record & Change Approval 70

# High Level Description

The Inter-Micro Communication (IMC) Arbitration prepares data for
transmission to a complimentary ECU through two redundant communication
paths. On the receive side, the Arbitration reads data from the primary
source and determines the data validity. A validity fault on primary
source prompts the IMC Arbitration component to evaluate the same signal
from the secondary source. Faulty signals from the primary source will
be replaced with signals from the secondary source, as long as they are
valid. If both data sources are invalid the IMC Arbitration outputs the
signal status based on never received, missing and invalid conditions.

#  Function I/O

## Input Description

Inputs for this component are provided by IMC signal configurations that
are defined based on program requirements. Refer Section 5.23 for more
details.

| Input Name                | Description                                                                                                                                                                                                  |
|-----------------------|-------------------------------------------------|
| *\<Signal1\>…\<Signal#\>* | All RTE signals coming from any periodic that are required to be read by IMC Arbitration scheduled runnables. The list of signals can change from program to program based on program dataflow requirements. |

## Output Description

Refer Data Dictionary for details.

##  Sub-Function Data Flow

### Imc Arbitration Transmit side data flow

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image1.emf)

### Imc Arbitration Receive side data flow

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image2.emf)

###  Rolling Counter Handling

**General Description:**

Rolling counters are used to ascertain sequence of every Signal Group
reception via IMC channels.

Rolling counters are embedded in the start byte with length of 5 bits in
every frame on both channels. This sequence is generated for each Rate
Group separately with range of 0 to 31. Roll over will happen once the
Rolling counter reaches 31.

All Signal Groups defined under a Rate Group will have same value of
Rolling Counter in a given cycle of transmission.

On the receiving side Rolling counter evaluation poses following
challenges:

1.  Underlying protocols of Primary and Secondary sources have different
    data handling methods and hence, at any instant, the data received
    from any of these channels will be different.

2.  Underlying protocols of Primary and Secondary sources have different
    handling in Software which in turn impacts reception hence, at any
    instant, the data processed will be different.

3.  Corruption in the channel level causes loss in messages and hence
    loss in synchronization.

Rolling counter algorithm addresses all these challenges and determines
a robust approach to handle these.

**Rolling Counter Algorithm description:**

The following are addressed by this algorithm:

1.  Validation of the data sequence of Signal Group based on Rolling
    counter from Primary and Secondary sources

2.  Data Sequence validation from IMC channels which are of same or
    different characteristics.

3.  Resynchronization of the Rolling counter check during data
    corruption in the channels.

4.  Resynchronization of the Rolling counter check when the Rolling
    counter reference changes ( Roll-over cases)

5.  Indicates if a Rolling counter fault needs to be reported.

Further details are indicated in the following generic flowchart.

Variables used in the flowchart are,

1.  DataValid: This is a flag which indicates if valid Data is received
    from the Communication channel.

2.  GoodDataSource:This indicates which Communication channel ( Primary
    or Secondary) has Valid data

3.  MessageSkipCounter: This is a counter which indicates the number of
    missed messages in the form of No data or invalid data.

4.  RollCounterError: Indicates if a rolling counter fault need to be
    reported

5.  CounterThreshold:This is a value related to the typical amount of
    latency in data transmission in the communication channel.

6.  ChannelSwitchDelay:This is a value related to the dynamics of the
    redundant communication channels. This indicates the typical delay
    in a message reception between the communication channels at any
    instant.

7.  PreviousRolling Counter:This is the value of the rolling counter of
    the previously stored valid message.

8.  RollCounterResyncCounterPrimary: This is a counter which indicates
    the number of times data is missed because of only Rolling Counter
    issue on primary channel.

9.  RollCounterResyncCounterSecondary: This is a counter which indicates
    the number of times data is missed because of only Rolling Counter
    issue on Secondary channel.

10. ResyncThreshold: This is the number of consecutive Rolling counter
    issues after which it could be assumed that either of the MCUs have
    lot synchronization of rolling counter, and hence a resync has to
    happen.

11. RollCounterPrimaryResync – Previous rolling counter value received
    during resync period on Primary channel

12. RollCounterSecondaryResync – Previous rolling counter value received
    during resync period on Secondary channel

13. PrimaryResyncActive – Indicates whether Resync is active on Primary
    channel

14. SecondaryResyncActive – Indicates whether Resync is active on
    Secondary channel.

In short, the Rolling counter algorithm behaves as follows,

1.  Data is considered valid in the following cases,

    1.  For consecutive messages from same Comm. channel, if the new
        Rolling counter falls within the range

> (ExpectedRollCntrValue – LowerLimit) \<= CurrentRolling Counter \<=
> (ExpectedRollCntrValue + CounterThreshold)
>
> Where ExpectedRollCntrValue = PreviousRolling Counter +
> MessageSkipCounter + 1,
>
> LowerLimit = CounterThreshold if it is lesser than MessageSkipCounter
> else, LowerLimit = MessageSkipCounter

1.  For consecutive messages from different Comm. channel, if the new RL
    falls within a range specified by

> (ExpectedRollCntrValue – LowerLimit) \<= CurrentRolling Counter \<=
> (ExpectedRollCntrValue + (CounterThreshold + ChannelSwitchDelay))
>
> Where ExpectedRollCntrValue = PreviousRolling Counter +
> MessageSkipCounter + 1,
>
> LowerLimit = CounterThreshold + ChannelSwitchDelay if it is lesser
> than MessageSkipCounter else, LowerLimit = MessageSkipCounter

1.  Rolling Counter error will not be set in the following cases,

    1.  For consecutive messages from same Comm. channel, if the new
        Rolling counter falls within the range

> (ExpectedRollCntrValue – CounterThreshold) \<= CurrentRolling Counter
> \<= (ExpectedRollCntrValue + CounterThreshold)
>
> Where ExpectedRollCntrValue = PreviousRolling Counter +
> MessageSkipCounter + 1

1.  For consecutive messages from different Comm. channel, if the new RL
    falls within a range specified by

> (ExpectedRollCntrValue – (CounterThreshold + ChannelSwitchDelay)) \<=
> CurrentRolling Counter \<= (ExpectedRollCntrValue +
> (CounterThreshold + ChannelSwitchDelay))
>
> Where ExpectedRollCntrValue = PreviousRolling Counter +
> MessageSkipCounter + 1

1.  On every skip of message (includes missing, CRC error and No data)
    MessageSkipCounter is incremented. The next rolling counter is
    expected to have a value bigger than the previous rolling counter
    value by this counter amount. Any active resynchronization will be
    cleared as next rolling counter value will not be just next to
    currently stored value.

2.  If consecutive ResyncThreshold amount of rolling counter issues
    occur (cases when old or invalid CurrentRollingCounter detected) in
    a channel, then it is assumed that either of the MCUs have lot
    synchronization of rolling counter on the particular channel, and
    hence a resynchronization is triggered.

3.  Following pseudo code explains resynchronization logic on Primary
    channel. Same is applicable for Secondary channel as well. This
    logic will start run when old or invalid CurrentRollingCounter
    detected in a channel. Note that at any point of time, Resync will
    be active for only one channel.

> If((Channel == Primary) && (SecondaryResyncActive == FALSE)) /\*
> Secondary Resync not active \*/
>
> {
>
> If(RollCounterPrimaryResync == 0xFF) /\* First time Rolling counter
> fault detected \*/
>
> {
>
> RollCounterResyncCounterPrimary ++ /\* Update Resync counter \*/
>
> RollCounterPrimaryResync = CurrentRollingCounter /\* Update current
> rolling counter \*/
>
> PrimaryResyncActive = TRUE /\*Activate primary resync \*/
>
> }
>
> Else
>
> {
>
> If(CurrentRollingCounter == (RollCounterPrimaryResync+1) /\* Check new
> rolling counter is just next to current previous rolling counter \*/
>
> {
>
> RollCounterResyncCounterPrimary ++ /\* Good to proceed resync.
> Increment Resync counter to reach threshold. \*/
>
> RollCounterPrimaryResync = CurrentRollingCounter /\* Update Rolling
> counter \*/
>
> }
>
> Else /\* Rolling counter is not next value. Abort Resync. Try again
> \*/
>
> {
>
> RollCounterResyncCounterPrimary = 0
>
> RollCounterPrimaryResync = 0xFF
>
> PrimaryResyncActive = FALSE
>
> }
>
> }
>
> }

When RollCounterResyncCounterPrimary reaches ResyncThreshold, Rolling
counter and data will be declared as valid.

1.  For rolling counter evaluation within the same Comm. Channel, a
    latency value of CounterThreshold is used. For rolling counter
    evaluation within different Comm. Channel, an additional latency
    value of ChannelSwitchDelay is used.

Following flow-charts indicates overall rolling counter handling.

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image3.emf)

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image4.emf)

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image5.emf)

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image6.emf)

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image7.emf)

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image8.emf)

Rolling counter algorithm spreads across following functions:

1.  ImcArbnInit1 – Initialization of Signal Group Resync Rolling counter
    buffer and Signal Group data source buffer

2.  ImcArbnRx – Resync and Skip counter handling during no data
    situation.

3.  RxFrmVldChk - Resync and Skip counter handling

4.  VldtRollgCntr – Validate rolling counter

5.  VldtRollgCntrAlg – Rolling counter algorithm implementation

6.  RollgCntrSeqChk – Valid Rolling counter interval checking

7.  NoDataHndlg – Rolling counter handling when No data received on both
    channels

8.  ImcChResyncHndlg – Resync logic

# Design Rationale and Assumptions

1.  Imc Arbitration Receive function designed based on the assumption
    that first byte and last byte in a valid Signal Group is always a
    non-zero value.

2.  Signal Group data received by IMC Arbitration component considered
    as valid if CRC and rolling counters found to be good. This means,
    IMC Arbitration component is not designed to evaluate quality of
    individual signals packed in a Signal Group. The signal status
    provided by this component is just mere expression of quality of
    reception. It is assumed that evaluation of quality of Signal would
    be carried-out by respective sending/receiving components.

3.  Imc Arbitration component doesn’t use fault threshold tracking
    mechanism implemented by Diagnostics Manager due to the fact that
    this component is currently assigned with one NTC (NTC 0x3F) for
    logging all frame faults and these faults are detected across three
    Rx periodics (ImcArbnPer4, ImcArbnPer5 and ImcArbnPer6). Diag
    Manager offers tracking mechanism only for a single periodic. This
    component keeps track of faulty frames using PIM variables and
    logs/clears the NTC in 100ms Rx periodic (ImcArbnPer6).

4.  Imc Arbitration component doesn’t care about availability of data
    bandwidth to transmit /receive all configured Signal Groups. It
    allows the user to configure up to 255 Signal Groups. Assumption is
    that optimal use of IMC channels would be ensured during system
    design.

5.  Imc Arbitration component doesn’t care about channel type of primary
    source or secondary source. This component should work independent
    of type of channel as long as the frame format of a Signal Group
    followed.

6.  Imc Arbitration Tx functionality provides interfaces to get transmit
    data for individual Signal Group or all signal groups configured
    under given Rate Group. It is up to the primary and secondary source
    Tx layers to decide how they would like to get the Tx data from IMC
    Arbitration component, considering all relevant requirements.

7.  It is mandatory to transmit all Signal Groups on primary source
    channel. Transmission of particular Signal Group on secondary source
    channel is optional and that need to be specified during
    configuration.

8.  Tx / Rx processing for particular Rate Group will happen only if it
    has minimum one Signal Group. Otherwise, evaluation of Tx / Rx
    processing of said Rate Group will be skipped.

9.  This component provides Signal status definition in two versions:
    basic and extended. While basic signal status indicates No Data,
    Valid and Invalid cases, extended signal status provides status of
    startup, Signal Group never received, Signal Group missing, Signal
    Group availability on only one channel or on both channels.
    Following table indicates relation between these two status:

<img
src="ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image9.png"
style="width:6in;height:1.5109in" />

1.  Signal Status IMCARBNRXEXTDSTS_STRTG / IMCARBNRXSTS_NODATA returned
    to IMC Signal users until initial start-up time completion even if
    integrity of received signal data found to be good. This is to
    ensure that the availability of properly calculated values in RTE by
    the components which are transmitting signals via IMC.

2.  Data consistency across the component is ensured by exclusive area
    access. Following are the places where exclusive area access
    provided:

    1.  Reading from / Writing into Tx Buffer

    2.  Reading from / Writing into Rx buffer

    3.  Writing to Received signal data buffer, Status buffer and Signal
        source buffers.

3.  This component provides two server runnables to copy data buffer
    during transmission: one for Rate Group level (provides all Signal
    Groups configured under given Rate Group) and another for Signal
    Group level (provides all Signals configured under given Signal
    Group). It is up to the respective channel drivers to decide which
    one to be invoked depending on buffer handling scheme.

4.  Primary and Secondary source receive data buffers are defined with
    same size even though, transmission of Signal Groups on Secondary
    source is optional. It is done to avoid complex logics in buffer
    handling. For e.g if SignalGroupA is configured to be PrimaryOnly,
    then there is no need to allocate buffer space in the Secondary
    source buffer for SignalGroupA. But, the design allocates buffer
    SignalGroupA as well in the Secondary source buffer to keep common
    buffer definition and access logic.

5.  The server runnables defined in this component designed based on the
    assumption that it will be invoked only from the tasks which runs at
    the rate of 2ms or greater than that.

# Sub-Functions

## Sub-Function: ImcArbnInit1

### Hardware Related Design

None

### Software Related Design

| **ImcArbnInit1**                         |                                                                                                             |
|-------------------|-----------------------------------------------------|
| **Function scope**                       | Global, Init function                                                                                       |
| **Description**                          | Initialized Signal Group and Signal related buffers. Gets start time of the component and saves it in a PIM |
| **Parameters**                           | None                                                                                                        |
| **Return value**                         | None                                                                                                        |
| **Affected static and global variables** | Reads / Writes to following variables in functions                                                          |
|                                          | *SigGroupNeverRxd*                                                                                          |
|                                          | *PrimSrcRollgCntrResync*                                                                                    |
|                                          | *SecdrySrcRollgCntrResync*                                                                                  |
|                                          | *RxdSigDataExtdSts*                                                                                         |
|                                          | *RxdSigDataSrc*                                                                                             |
|                                          | *SigGroupDataSrc*                                                                                           |
| **Affected inter-runnable variable**     | None                                                                                                        |
| **Exclusive area access**                | None                                                                                                        |
| **Configuration access**                 | Accesses following configuration data                                                                       |
|                                          | *IMCARBN_TOTALNROFSIG_CNT_U16*                                                                              |
|                                          | *IMCARBN_TOTALNROFSIGGROUP_CNT_U08*                                                                         |
| **Calibration data access**              | None                                                                                                        |
| **Called local functions**               | None                                                                                                        |
| **External Interface call**              | None                                                                                                        |
| **Called by**                            | Called by following functions                                                                               |
|                                          | *Init Task*                                                                                                 |

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image10.emf)

## Sub-Function: ImcArbnTx

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 74%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>ImcArbnTx</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>Local</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>1) This function collects signal data for all Signal Groups
configured in the ImcArbn_SigGroupConfig_Rec for given Rate Group and
packs each signal to the specified start bit in each Signal Group as
defined in the configuration.<br />
2) A Pattern Identification flag, Rolling Counter, Signal Group ID, CRC,
Compliment Pattern ID and Compliment Rolling Counter are added for each
Signal Group.<br />
3) The resulting signal group is put into a transmit data buffer for for
the GetTxSigGroup or GetTxRateGroup client calls to access.</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Parameters</strong></td>
<td>Requires following parameters</td>
</tr>
<tr class="even">
<td><em>RateGroup -</em> Rate Group Id provided by IMC Arbitration
Configuration<br />
Type: uint8<br />
Range:<br />
IMCARBN_RATEGROUPID2MILLISEC_CNT_U08 (0U)<br />
IMCARBN_RATEGROUPID10MILLISEC_CNT_U08 (1U)<br />
IMCARBN_RATEGROUPID100MILLISEC_CNT_U08 (2U)<br />
All other values are invalid</td>
</tr>
<tr class="odd">
<td><strong>Return value</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td rowspan="3"><strong>Affected static and global
variables</strong></td>
<td>Writes to following variables</td>
</tr>
<tr class="odd">
<td><em>TxBuf</em></td>
</tr>
<tr class="even">
<td><em>RollgCntr</em></td>
</tr>
<tr class="odd">
<td><strong>Affected inter-runnable variable</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Exclusive area access</strong></td>
<td>Needed to update Transmit data buffer</td>
</tr>
<tr class="odd">
<td rowspan="4"><strong>Configuration access</strong></td>
<td>Accesses following configuration data</td>
</tr>
<tr class="even">
<td><em>SIGGROUPCONFIG_REC</em></td>
</tr>
<tr class="odd">
<td><em>RATEGROUPOFFS_CNT_U08</em></td>
</tr>
<tr class="even">
<td><em>NRSIGGROUPINRATEGROUP_CNT_U08</em></td>
</tr>
<tr class="odd">
<td><strong>Calibration data access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Called local functions</strong></td>
<td>Calls following local function</td>
</tr>
<tr class="odd">
<td><em>CreatSigGroupData</em></td>
</tr>
<tr class="even">
<td rowspan="2"><strong>External Interface call</strong></td>
<td>Calls following external function in the sub-functions</td>
</tr>
<tr class="odd">
<td><em>Crc_CalculateCRC8</em></td>
</tr>
<tr class="even">
<td rowspan="4"><strong>Called by</strong></td>
<td>Called by following functions only when atleast one Signal Group is
configured for particular Rate Group<br />
e.g if no Signal Group configured for 100ms Rate Group then this
function will not get called from ImcArbnPer3</td>
</tr>
<tr class="odd">
<td><em>ImcArbrPer1</em></td>
</tr>
<tr class="even">
<td><em>ImcArbrPer2</em></td>
</tr>
<tr class="odd">
<td><em>ImcArbrPer3</em></td>
</tr>
</tbody>
</table>

## Sub-Function: ImcArbnPer1

### Hardware Related Design

None

### Software Related Design

| **ImcArbrPer1**                          |                                                                                                                                                          |
|-------------------|-----------------------------------------------------|
| **Function scope**                       | 2ms Periodic, Global                                                                                                                                     |
| **Description**                          | Frames transmit data for all Signal Groups configured under 2ms Rate Group and stores in the Transmit data buffer.                                       |
| **Parameters**                           | None                                                                                                                                                     |
| **Return value**                         | None                                                                                                                                                     |
| **Affected static and global variables** | Writes to following variables                                                                                                                            |
|                                          | *TxBuf*                                                                                                                                                  |
|                                          | *RollgCntr*                                                                                                                                              |
| **Affected inter-runnable variable**     | None                                                                                                                                                     |
| **Exclusive area access**                | Needed to update Transmit data buffer                                                                                                                    |
| **Configuration access**                 | Accesses following configuration data                                                                                                                    |
|                                          | *SIGGROUPCONFIG_REC*                                                                                                                                     |
|                                          | *RATEGROUPOFFS_CNT_U08*                                                                                                                                  |
|                                          | *NRSIGGROUPINRATEGROUP_CNT_U08*                                                                                                                          |
| **Calibration data access**              | None                                                                                                                                                     |
| **Called local functions**               | Calls following function only when number of Signal Groups configured under the 2ms Rate Group is NOT zero (IMCARBN_NROF2MILLISECRATEGROUP_CNT_U08 != 0) |
|                                          | *ImcArbnTx*                                                                                                                                              |
| **External Interface call**              | Calls following external function                                                                                                                        |
|                                          | *Crc_CalculateCRC8*                                                                                                                                      |
| **Called by**                            | 2ms Task                                                                                                                                                 |

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image13.emf)

## Sub-Function: ImcArbnPer2

### Hardware Related Design

None

### Software Related Design

| **ImcArbrPer2**                          |                                                                                                                                                            |
|-------------------|-----------------------------------------------------|
| **Function scope**                       | 10ms Periodic, Global                                                                                                                                      |
| **Description**                          | Frames transmit data for all Signal Groups configured under 10ms Rate Group and stores in the Transmit data buffer.                                        |
| **Parameters**                           | None                                                                                                                                                       |
| **Return value**                         | None                                                                                                                                                       |
| **Affected static and global variables** | Writes to following variables                                                                                                                              |
|                                          | *TxBuf*                                                                                                                                                    |
|                                          | *RollgCntr*                                                                                                                                                |
| **Affected inter-runnable variable**     | None                                                                                                                                                       |
| **Exclusive area access**                | Needed to update Transmit data buffer                                                                                                                      |
| **Configuration access**                 | Accesses following configuration data                                                                                                                      |
|                                          | *SIGGROUPCONFIG_REC*                                                                                                                                       |
|                                          | *RATEGROUPOFFS_CNT_U08*                                                                                                                                    |
|                                          | *NRSIGGROUPINRATEGROUP_CNT_U08*                                                                                                                            |
| **Calibration data access**              | None                                                                                                                                                       |
| **Called local functions**               | Calls following function only when number of Signal Groups configured under the 10ms Rate Group is NOT zero (IMCARBN_NROF10MILLISECRATEGROUP_CNT_U08 != 0) |
|                                          | *ImcArbnTx*                                                                                                                                                |
| **External Interface call**              | Calls following external function in the sub-functions                                                                                                     |
|                                          | *Crc_CalculateCRC8*                                                                                                                                        |
| **Called by**                            | 10ms Task                                                                                                                                                  |

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image14.emf)

## Sub-Function: ImcArbnPer3

### Hardware Related Design

None

### Software Related Design

| **ImcArbrPer3**                          |                                                                                                                                                              |
|-------------------|-----------------------------------------------------|
| **Function scope**                       | 100ms Periodic, Global                                                                                                                                       |
| **Description**                          | Frames transmit data for all Signal Groups configured under 100ms Rate Group and stores in the Transmit data buffer.                                         |
| **Parameters**                           | None                                                                                                                                                         |
| **Return value**                         | None                                                                                                                                                         |
| **Affected static and global variables** | Writes to following variables                                                                                                                                |
|                                          | *TxBuf*                                                                                                                                                      |
|                                          | *RollgCntr*                                                                                                                                                  |
| **Affected inter-runnable variable**     | None                                                                                                                                                         |
| **Exclusive area access**                | Needed to update Transmit data buffer                                                                                                                        |
| **Configuration access**                 | Accesses following configuration data                                                                                                                        |
|                                          | *SIGGROUPCONFIG_REC*                                                                                                                                         |
|                                          | *RATEGROUPOFFS_CNT_U08*                                                                                                                                      |
|                                          | *NRSIGGROUPINRATEGROUP_CNT_U08*                                                                                                                              |
| **Calibration data access**              | None                                                                                                                                                         |
| **Called local functions**               | Calls following function only when number of Signal Groups configured under the 100ms Rate Group is NOT zero (IMCARBN_NROF100MILLISECRATEGROUP_CNT_U08 != 0) |
|                                          | *ImcArbnTx*                                                                                                                                                  |
| **External Interface call**              | Calls following external function in the sub-functions                                                                                                       |
|                                          | *Crc_CalculateCRC8*                                                                                                                                          |
| **Called by**                            | 100ms Task                                                                                                                                                   |

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image15.emf)

## Sub-Function: ImcArbnRx

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 23%" />
<col style="width: 76%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>ImcArbnRx</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>Local</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>1) This sub-function receives signal groups from two Imc Channels:
Primary Source and Secondary Source. It first validates the data from
the primary source and if there is any fault found with the Signal Group
data, it will switch to the secondary source for that signal.<br />
2) If the Signal Group data has been sourced from primary source, it
checks availability of the Signal Group data received via secondary
source. If the signal group is available in secondary source buffer,
then it sets respective signals defined under signal group to
IMCARBNRXEXTDSTS_DATAVLDWITHBACKUP. Otherwise it sets the Signal status
to IMCARBNRXEXTDSTS_DATAVLDWITHNOBACKUP.<br />
3) If the signal group data received on primary source found to be
invalid, then it switches to secondary source data buffer and evaluates
it. If valid, the signal status is set to
IMCARBNRXEXTDSTS_DATAVLDWITHNOBACKUP. Otherwise set to
IMCARBNRXEXTDSTS_DATAINVLD.<br />
4) If the Signal Group is not received in any of the channels, then it
evaluates missing and never received conditions and sets signal status
to any of the following depends on the conditions:
IMCARBNRXEXTDSTS_NEVERRXD, IMCARBNRXEXTDSTS_MISS,
IMCARBNRXEXTDSTS_PREVDATA<br />
5) If initial start-up timer is not complete, then signal status is set
to IMCARBNRXEXTDSTS_STRTG irrespective of above evaluations.<br />
6) There are a total of two Rx buffers are defined as input to this
function: one for primary source, another one for secondary
source.<br />
7) There are three buffers (Signal Data, Signal Status, Signal Source)
defined to serve signal data requests from the components which uses
signals received via IMC Arbitration component. This function puts
processed values into these buffers.<br />
8) PIM variables are used to track frame faults and log NTC based on
threshold.<br />
9) Following validation steps are carried out to declare received Signal
Group data as valid / invalid:<br />
a)No Data Received check<br />
b)CRC Check<br />
c) Rolling counter check</td>
</tr>
<tr class="odd">
<td rowspan="4"><strong>Parameters</strong></td>
<td>Requires following parameters</td>
</tr>
<tr class="even">
<td><em>FrmFltCntr -</em> Pointer to the frame fault counters for the
given Rate Group where frame faults to be accounted.<br />
Type: Ary2D_u8_2_2*<br />
Valid Range: 0x00000001 to 0xFFFFFFFF</td>
</tr>
<tr class="odd">
<td><em>RateGroup -</em> Rate Group Id provided by IMC Arbitration
Configuration<br />
Type: uint8<br />
Range:<br />
IMCARBN_RATEGROUPID2MILLISEC_CNT_U08 (0U)<br />
IMCARBN_RATEGROUPID10MILLISEC_CNT_U08 (1U)<br />
IMCARBN_RATEGROUPID100MILLISEC_CNT_U08 (2U)<br />
All other values are invalid</td>
</tr>
<tr class="even">
<td>IniTiOutChkCmpl - Initial time-out completion status<br />
Type: boolean<br />
TRUE – Time-out completed<br />
FALSE – Time-out not completed</td>
</tr>
<tr class="odd">
<td><strong>Return value</strong></td>
<td>void</td>
</tr>
<tr class="even">
<td rowspan="20"><strong>Affected static and global
variables</strong></td>
<td>Read and Write to following variables in sub-functions</td>
</tr>
<tr class="odd">
<td><em>SigGroupMissCntr</em></td>
</tr>
<tr class="even">
<td><em>SigGroupNeverRxd</em></td>
</tr>
<tr class="odd">
<td><em>RxdSigData</em></td>
</tr>
<tr class="even">
<td><em>RxdSigDataExtdSts</em></td>
</tr>
<tr class="odd">
<td><em>PrevRollgCntrRxd</em></td>
</tr>
<tr class="even">
<td><em>PrimSrcRxBuf</em></td>
</tr>
<tr class="odd">
<td><em>SecdrySrcRxBuf</em></td>
</tr>
<tr class="even">
<td><em>RxdSigDataSrc</em></td>
</tr>
<tr class="odd">
<td><em>SigGroupSkipCntr</em></td>
</tr>
<tr class="even">
<td><em>PrimSrcResyncCntr</em></td>
</tr>
<tr class="odd">
<td><em>SecdrySrcResyncCntr</em></td>
</tr>
<tr class="even">
<td><em>ResyncOnPrimActv</em></td>
</tr>
<tr class="odd">
<td><em>ResyncOnSecdryActv</em></td>
</tr>
<tr class="even">
<td><em>SigGroupDataSrc</em></td>
</tr>
<tr class="odd">
<td><em>PrimSrcRollgCntrResync</em></td>
</tr>
<tr class="even">
<td><em>SecdrySrcRollgCntrResync</em></td>
</tr>
<tr class="odd">
<td><em>FrmFltCntr2MilliSec</em></td>
</tr>
<tr class="even">
<td><em>FrmFltCntr10MilliSec</em></td>
</tr>
<tr class="odd">
<td><em>FrmFltCntr100MilliSec</em></td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Affected inter-runnable variable</strong></td>
<td>Reads following interunnable variable</td>
</tr>
<tr class="odd">
<td><em>IniTiOutChkCmpl</em></td>
</tr>
<tr class="even">
<td><strong>Exclusive area access</strong></td>
<td>Needed to read received Signal Group data buffers and to write Imc
Signal data, Signal Status and Signal source buffers.</td>
</tr>
<tr class="odd">
<td rowspan="5"><strong>Configuration access</strong></td>
<td>Accesses following configuration data in the sub-functions call</td>
</tr>
<tr class="even">
<td><em>SIGGROUPCONFIG_REC</em></td>
</tr>
<tr class="odd">
<td><em>RATEGROUPOFFS_CNT_U08</em></td>
</tr>
<tr class="even">
<td><em>NRSIGGROUPINRATEGROUP_CNT_U08</em></td>
</tr>
<tr class="odd">
<td><em>MISSSIGGROUPTIOUT_CNT_U08</em></td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Calibration data access</strong></td>
<td>Accesses following calibration value in the sub-functions call</td>
</tr>
<tr class="odd">
<td><em>ImcArbnFrmFltThd</em></td>
</tr>
<tr class="even">
<td rowspan="6"><strong>Called local functions</strong></td>
<td>Calls following local function</td>
</tr>
<tr class="odd">
<td><em>RxFrmVldChk</em></td>
</tr>
<tr class="even">
<td><em>DecodSigGroupData</em></td>
</tr>
<tr class="odd">
<td><em>NoDataHndlg</em></td>
</tr>
<tr class="even">
<td><em>OvrdSigStsDurgStrtUp</em></td>
</tr>
<tr class="odd">
<td><em>NoDataRxd</em></td>
</tr>
<tr class="even">
<td rowspan="2"><strong>External Interface call</strong></td>
<td>Calls following external function</td>
</tr>
<tr class="odd">
<td><em>Crc_CalculateCRC8</em></td>
</tr>
<tr class="even">
<td rowspan="4"><strong>Called by</strong></td>
<td>Called by following functions only when atleast one Signal Group is
configured for particular Rate Group<br />
e.g if no Signal Group configured for 100ms Rate Group then this
function will not get called from ImcArbnPer6.</td>
</tr>
<tr class="odd">
<td><em>ImcArbrPer4</em></td>
</tr>
<tr class="even">
<td><em>ImcArbrPer5</em></td>
</tr>
<tr class="odd">
<td><em>ImcArbrPer6</em></td>
</tr>
</tbody>
</table>

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image16.emf)

## Sub-Function: ImcArbnPer4

### Hardware Related Design

None

### Software Related Design

| **ImcArbrPer4**                          |                                                                                                                                                                                                      |
|-------------------|-----------------------------------------------------|
| **Function scope**                       | 2ms Periodic, Global                                                                                                                                                                                 |
| **Description**                          | Processes received Signal Group data via IMC Channels for all Signal Groups configured under 2ms Rate Group and stores validated Signal data, Signal Status and Signal source in respective buffers. |
| **Parameters**                           | None                                                                                                                                                                                                 |
| **Return value**                         | None                                                                                                                                                                                                 |
| **Affected static and global variables** | Read and Write to following variables in sub-functions                                                                                                                                               |
|                                          | *SigGroupMissCntr*                                                                                                                                                                                   |
|                                          | *SigGroupNeverRxd*                                                                                                                                                                                   |
|                                          | *RxdSigData*                                                                                                                                                                                         |
|                                          | *RxdSigDataExtdSts*                                                                                                                                                                                  |
|                                          | *PrevRollgCntrRxd*                                                                                                                                                                                   |
|                                          | *PrimSrcRxBuf*                                                                                                                                                                                       |
|                                          | *SecdrySrcRxBuf*                                                                                                                                                                                     |
|                                          | *FrmFltCntr2MilliSec*                                                                                                                                                                                |
|                                          | *RxdSigDataSrc*                                                                                                                                                                                      |
|                                          | *SigGroupSkipCntr*                                                                                                                                                                                   |
|                                          | *PrimSrcResyncCntr*                                                                                                                                                                                  |
|                                          | *SecdrySrcResyncCntr*                                                                                                                                                                                |
|                                          | *ResyncOnPrimActv*                                                                                                                                                                                   |
|                                          | *ResyncOnSecdryActv*                                                                                                                                                                                 |
|                                          | *SigGroupDataSrc*                                                                                                                                                                                    |
|                                          | *PrimSrcRollgCntrResync*                                                                                                                                                                             |
|                                          | *SecdrySrcRollgCntrResync*                                                                                                                                                                           |
| **Affected inter-runnable variable**     | Reads following inter-runnable variable                                                                                                                                                              |
|                                          | *IniTiOutChkCmpl*                                                                                                                                                                                    |
| **Exclusive area access**                | Needed to read received Signal Group data buffers and write to Imc Signal data, Signal Status and Signal source buffers                                                                              |
| **Configuration access**                 | Accesses following configuration data in the sub-functions call                                                                                                                                      |
|                                          | *SIGGROUPCONFIG_REC*                                                                                                                                                                                 |
|                                          | *RATEGROUPOFFS_CNT_U08*                                                                                                                                                                              |
|                                          | *NRSIGGROUPINRATEGROUP_CNT_U08*                                                                                                                                                                      |
|                                          | *MISSSIGGROUPTIOUT_CNT_U08*                                                                                                                                                                          |
| **Calibration data access**              | Accesses following calibration value in the sub-functions call                                                                                                                                       |
|                                          | *ImcArbnFrmFltThd*                                                                                                                                                                                   |
| **Called local functions**               | Calls following function only when number of Signal Groups configured under the 2ms Rate Group is NOT zero (IMCARBN_NROF2MILLISECRATEGROUP_CNT_U08 != 0)                                             |
|                                          | *ImcArbnRx*                                                                                                                                                                                          |
| **External Interface call**              | Calls following external function                                                                                                                                                                    |
|                                          | *Crc_CalculateCRC8*                                                                                                                                                                                  |
| **Called by**                            | 2ms Task                                                                                                                                                                                             |

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image17.emf)

## Sub-Function: ImcArbnPer5

### Hardware Related Design

None

### Software Related Design

| **ImcArbrPer5**                          |                                                                                                                                                                                                       |
|-------------------|-----------------------------------------------------|
| **Function scope**                       | 10ms Periodic, Global                                                                                                                                                                                 |
| **Description**                          | Processes received Signal Group data via IMC Channels for all Signal Groups configured under 10ms Rate Group and stores validated Signal data, Signal Status and Signal source in respective buffers. |
| **Parameters**                           | None                                                                                                                                                                                                  |
| **Return value**                         | None                                                                                                                                                                                                  |
| **Affected static and global variables** | Read and Write to following variables in sub-functions                                                                                                                                                |
|                                          | *SigGroupMissCntr*                                                                                                                                                                                    |
|                                          | *SigGroupNeverRxd*                                                                                                                                                                                    |
|                                          | *RxdSigData*                                                                                                                                                                                          |
|                                          | *RxdSigDataExtdSts*                                                                                                                                                                                   |
|                                          | *PrevRollgCntrRxd*                                                                                                                                                                                    |
|                                          | *PrimSrcRxBuf*                                                                                                                                                                                        |
|                                          | *SecdrySrcRxBuf*                                                                                                                                                                                      |
|                                          | *FrmFltCntr10MilliSec*                                                                                                                                                                                |
|                                          | *RxdSigDataSrc*                                                                                                                                                                                       |
|                                          | *SigGroupSkipCntr*                                                                                                                                                                                    |
|                                          | *PrimSrcResyncCntr*                                                                                                                                                                                   |
|                                          | *SecdrySrcResyncCntr*                                                                                                                                                                                 |
|                                          | *ResyncOnPrimActv*                                                                                                                                                                                    |
|                                          | *ResyncOnSecdryActv*                                                                                                                                                                                  |
|                                          | *SigGroupDataSrc*                                                                                                                                                                                     |
|                                          | *PrimSrcRollgCntrResync*                                                                                                                                                                              |
|                                          | *SecdrySrcRollgCntrResync*                                                                                                                                                                            |
| **Affected inter-runnable variable**     | Reads following inter-runnable variable                                                                                                                                                               |
|                                          | *IniTiOutChkCmpl*                                                                                                                                                                                     |
| **Exclusive area access**                | Needed to read received Signal Group data buffers and write to Imc Signal data, Signal Status and Signal source buffers                                                                               |
| **Configuration access**                 | Accesses following configuration data in the sub-functions call                                                                                                                                       |
|                                          | *SIGGROUPCONFIG_REC*                                                                                                                                                                                  |
|                                          | *RATEGROUPOFFS_CNT_U08*                                                                                                                                                                               |
|                                          | *NRSIGGROUPINRATEGROUP_CNT_U08*                                                                                                                                                                       |
|                                          | *MISSSIGGROUPTIOUT_CNT_U08*                                                                                                                                                                           |
| **Calibration data access**              | Accesses following calibration value in the sub-functions call                                                                                                                                        |
|                                          | *ImcArbnFrmFltThd*                                                                                                                                                                                    |
| **Called local functions**               | Calls following function only when number of Signal Groups configured under the 10ms Rate Group is NOT zero (IMCARBN_NROF10MILLISECRATEGROUP_CNT_U08 != 0)                                            |
|                                          | *ImcArbnRx*                                                                                                                                                                                           |
| **External Interface call**              | Calls following external function                                                                                                                                                                     |
|                                          | *Crc_CalculateCRC8*                                                                                                                                                                                   |
| **Called by**                            | 10ms Task                                                                                                                                                                                             |

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image18.emf)

## Sub-Function: ImcArbnPer6

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 74%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>ImcArbrPer6</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>100ms Periodic, Global</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>1. Evaluates initial start-up time out and sets IniTiOutChkCmpl flag
once start-up exceeded ECU initialization timeout
ImcArbnEcuIninTiOutThd. IniTiOutChkCmpl would be used across all Rx
periodics to set signal status IMCARBNRXEXTDSTS_STRTG.<br />
2. Processes received Signal Group data via IMC Channels for all Signal
Groups configured under 100ms Rate Group and stores validated Signal
data, Signal Status and Signal source in respective buffers.<br />
3. Logs NTCNR_0X03F if any of Frame Fault counters exceeds
ImcArbnFrmFltThd.</td>
</tr>
<tr class="odd">
<td><strong>Parameters</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Return value</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td rowspan="19"><strong>Affected static and global
variables</strong></td>
<td>Read and Write to following variables in sub-functions</td>
</tr>
<tr class="even">
<td>Read and Write to following variables in sub-functions</td>
</tr>
<tr class="odd">
<td><em>SigGroupMissCntr</em></td>
</tr>
<tr class="even">
<td><em>SigGroupNeverRxd</em></td>
</tr>
<tr class="odd">
<td><em>RxdSigData</em></td>
</tr>
<tr class="even">
<td><em>RxdSigDataExtdSts</em></td>
</tr>
<tr class="odd">
<td><em>PrevRollgCntrRxd</em></td>
</tr>
<tr class="even">
<td><em>PrimSrcRxBuf</em></td>
</tr>
<tr class="odd">
<td><em>SecdrySrcRxBuf</em></td>
</tr>
<tr class="even">
<td><em>FrmFltCntr100MilliSec</em></td>
</tr>
<tr class="odd">
<td><em>RxdSigDataSrc</em></td>
</tr>
<tr class="even">
<td><em>SigGroupSkipCntr</em></td>
</tr>
<tr class="odd">
<td><em>PrimSrcResyncCntr</em></td>
</tr>
<tr class="even">
<td><em>SecdrySrcResyncCntr</em></td>
</tr>
<tr class="odd">
<td><em>ResyncOnPrimActv</em></td>
</tr>
<tr class="even">
<td><em>ResyncOnSecdryActv</em></td>
</tr>
<tr class="odd">
<td><em>SigGroupDataSrc</em></td>
</tr>
<tr class="even">
<td><em>PrimSrcRollgCntrResync</em></td>
</tr>
<tr class="odd">
<td><em>SecdrySrcRollgCntrResync</em></td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Affected inter-runnable variable</strong></td>
<td>Reads /Writes following inter-runnable variable</td>
</tr>
<tr class="odd">
<td><em>IniTiOutChkCmpl</em></td>
</tr>
<tr class="even">
<td><strong>Exclusive area access</strong></td>
<td>Needed to read received Signal Group data buffers and write to Imc
Signal data, Signal Status and Signal source buffers</td>
</tr>
<tr class="odd">
<td rowspan="5"><strong>Configuration access</strong></td>
<td>Accesses following configuration data in the sub-functions call</td>
</tr>
<tr class="even">
<td><em>SIGGROUPCONFIG_REC</em></td>
</tr>
<tr class="odd">
<td><em>RATEGROUPOFFS_CNT_U08</em></td>
</tr>
<tr class="even">
<td><em>NRSIGGROUPINRATEGROUP_CNT_U08</em></td>
</tr>
<tr class="odd">
<td><em>MISSSIGGROUPTIOUT_CNT_U08</em></td>
</tr>
<tr class="even">
<td rowspan="3"><strong>Calibration data access</strong></td>
<td>Accesses following calibration value in the sub-functions call</td>
</tr>
<tr class="odd">
<td><em>ImcArbnEcuIninTiOutThd</em></td>
</tr>
<tr class="even">
<td><em>ImcArbnFrmFltThd</em></td>
</tr>
<tr class="odd">
<td rowspan="4"><strong>Called local functions</strong></td>
<td>Calls following local function</td>
</tr>
<tr class="even">
<td><em>GetImcFltParamByte</em></td>
</tr>
<tr class="odd">
<td>Calls following function only when number of Signal Groups
configured under the 100ms Rate Group is NOT zero
(IMCARBN_NROF100MILLISECRATEGROUP_CNT_U08 != 0)</td>
</tr>
<tr class="even">
<td><em>ImcArbnRx</em></td>
</tr>
<tr class="odd">
<td rowspan="4"><strong>External Interface call</strong></td>
<td>Calls following external function</td>
</tr>
<tr class="even">
<td><em>GetTiSpan100MicroSec32bit</em></td>
</tr>
<tr class="odd">
<td><em>SetNtcSts</em></td>
</tr>
<tr class="even">
<td><em>Crc_CalculateCRC8</em></td>
</tr>
<tr class="odd">
<td><strong>Called by</strong></td>
<td>100ms Task</td>
</tr>
</tbody>
</table>

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image19.emf)

## Sub-Function: SetRxSigGroup

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 74%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>SetRxSigGroup</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>Server Runnable, Global</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>This server function is called by primary / secondary source Rx
layers to store signal group data that have been received over IMC
channels.</td>
</tr>
<tr class="odd">
<td rowspan="4"><strong>Parameters</strong></td>
<td>Requires following parameters</td>
</tr>
<tr class="even">
<td><em>SigGroup -</em> Signal Group Id provided by IMC Arbitration
Configuration<br />
Type: uint8<br />
Range: 0 to 255</td>
</tr>
<tr class="odd">
<td><em>DataSrc -</em> Imc Channel ID from which the server runnable
called<br />
Type: ImcArbnRxDataSrc1<br />
Range:<br />
IMCARBNRXDATASRC_PRIM (0U)<br />
IMCARBNRXDATASRC_SECDRY (1U)<br />
IMCARBNRXDATASRC_NOSRC (2U)<br />
All other values are invalid</td>
</tr>
<tr class="even">
<td><em>Buf -</em> Pointer to the received Signal Group data
buffer<br />
Type: Ary1D_u8_8*<br />
Valid Range: 0x00000001 to 0xFFFFFFFF</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Return value</strong></td>
<td>Returns following value</td>
</tr>
<tr class="even">
<td>ErrCod - Informs the caller about status of the operation<br />
Type: Std_ReturnType<br />
Range: E_OK (0)<br />
E_NOT_OK (1)</td>
</tr>
<tr class="odd">
<td rowspan="4"><strong>Affected static and global
variables</strong></td>
<td>Writes to following variables in sub-functions</td>
</tr>
<tr class="even">
<td><em>PrimSrcRxBuf</em></td>
</tr>
<tr class="odd">
<td><em>SecdrySrcRxBuf</em></td>
</tr>
<tr class="even">
<td><em>SigGroupNeverRxd</em></td>
</tr>
<tr class="odd">
<td><strong>Affected inter-runnable variable</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Exclusive area access</strong></td>
<td>Needed to write primary and secondary source received data
buffers.</td>
</tr>
<tr class="odd">
<td><strong>Configuration access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Calibration data access</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Called local functions</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>External Interface call</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Called by</strong></td>
<td>Primary and Secondary Source drivers</td>
</tr>
</tbody>
</table>

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image20.emf)

## Sub-Function: GetTxSigGroup

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 74%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>GetTxSigGroup</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>Server Runnable, Global</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>This server function is called by primary / secondary source Tx
layers to get signal group data to transmit over IMC channels.</td>
</tr>
<tr class="odd">
<td rowspan="3"><strong>Parameters</strong></td>
<td>Requires following parameters</td>
</tr>
<tr class="even">
<td><em>SigGroupId -</em> Signal Group Id provided by IMC Arbitration
Configuration<br />
Type: uint8<br />
Range: 0 to 255</td>
</tr>
<tr class="odd">
<td><em>Buf -</em> Pointer to the buffer where transmit data to be
copied<br />
Type: uint8*<br />
Valid Range: 0x00000001 to 0xFFFFFFFF</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Return value</strong></td>
<td>Returns following value</td>
</tr>
<tr class="odd">
<td>ErrCod - Informs the caller about status of the operation<br />
Type: Std_ReturnType<br />
Range: E_OK (0)<br />
E_NOT_OK (1)</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Affected static and global
variables</strong></td>
<td>Reads following variable</td>
</tr>
<tr class="odd">
<td><em>TxBuf</em></td>
</tr>
<tr class="even">
<td><strong>Affected inter-runnable variable</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Exclusive area access</strong></td>
<td>Needed to read from Tx data buffer.</td>
</tr>
<tr class="even">
<td><strong>Configuration access</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Calibration data access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Called local functions</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>External Interface call</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Called by</strong></td>
<td>Primary and Secondary Source drivers</td>
</tr>
</tbody>
</table>

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image21.emf)

## Sub-Function: GetTxRateGroup

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 74%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>GetTxRateGroup</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>Server Runnable, Global</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>This server function is called by primary / secondary source Tx
layers to get transmit data of all Signal Groups configured under given
Rate Group.</td>
</tr>
<tr class="odd">
<td rowspan="3"><strong>Parameters</strong></td>
<td>Requires following parameters</td>
</tr>
<tr class="even">
<td><em>RateGroup -</em> Rate Group Id provided by IMC Arbitration
Configuration<br />
Type: uint8<br />
Range:<br />
IMCARBN_RATEGROUPID2MILLISEC_CNT_U08 (0U)<br />
IMCARBN_RATEGROUPID10MILLISEC_CNT_U08 (1U)<br />
IMCARBN_RATEGROUPID100MILLISEC_CNT_U08 (2U)<br />
All other values are invalid</td>
</tr>
<tr class="odd">
<td><em>Buf -</em> Pointer to the buffer where transmit data to be
copied<br />
Type: uint8*<br />
Valid Range: 0x00000001 to 0xFFFFFFFF</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Return value</strong></td>
<td>Returns following value</td>
</tr>
<tr class="odd">
<td>ErrCod - Informs the caller about status of the operation<br />
Type: Std_ReturnType<br />
Range: E_OK (0)<br />
E_NOT_OK (1)</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Affected static and global
variables</strong></td>
<td>Reads following variable</td>
</tr>
<tr class="odd">
<td><em>TxBuf</em></td>
</tr>
<tr class="even">
<td><strong>Affected inter-runnable variable</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Exclusive area access</strong></td>
<td>Needed to read from Tx data buffer.</td>
</tr>
<tr class="even">
<td rowspan="3"><strong>Configuration access</strong></td>
<td>Accesses following configuration data</td>
</tr>
<tr class="odd">
<td><em>RATEGROUPOFFS_CNT_U08</em></td>
</tr>
<tr class="even">
<td><em>NRSIGGROUPINRATEGROUP_CNT_U08</em></td>
</tr>
<tr class="odd">
<td><strong>Calibration data access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Called local functions</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>External Interface call</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Called by</strong></td>
<td>Primary and Secondary Source drivers</td>
</tr>
</tbody>
</table>

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image22.emf)

## Sub-Function: GetSigImcDataExtdSts\_\<DATA_TYPE\>

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 74%" />
</colgroup>
<thead>
<tr class="header">
<th
colspan="2"><strong>GetSigImcDataExtdSts_&lt;DATA_TYPE&gt;</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>Server Runnable, Global</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>1) This server function is called by application components to get
particular Signal data received over IMC Channels, Extended Signal
Status and Signal Source.<br />
<br />
2) There are 8 Server runnables defined to get signal data with extended
signal status received via Imc channels each of which called based on
received signal data type. Place holder &lt;DATA_TYPE&gt; can be any of
the following: f32 (float32), u32 (uint32), s32 (sint32), u16 (uint16),
s16 (sint16), u08 (uint8), s08 (sint8), logl (boolean).</td>
</tr>
<tr class="odd">
<td rowspan="5"><strong>Parameters</strong></td>
<td>Requires following parameters</td>
</tr>
<tr class="even">
<td><em>SigId -</em> IMC Signal Id provided by IMC Arbitration
Configuration<br />
Type: uint16<br />
Range:<br />
0 to 65535</td>
</tr>
<tr class="odd">
<td><em>Data -</em> Pointer to the signal data buffer where signal data
to be copied<br />
Type: uint8*<br />
Valid Range: 0x00000001 to 0xFFFFFFFF</td>
</tr>
<tr class="even">
<td><em>Sts -</em> Pointer to signal status buffer where signal status
to be copied<br />
Type: ImcArbnRxSts1*<br />
Valid Range: 0x00000001 to 0xFFFFFFFF</td>
</tr>
<tr class="odd">
<td><em>DataSrc -</em> Imc Channel ID from which the signal data
received<br />
Type: ImcArbnRxDataSrc1*<br />
Valid Range: 0x00000001 to 0xFFFFFFFF</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Return value</strong></td>
<td>Returns following value</td>
</tr>
<tr class="odd">
<td>ErrCod - Informs the caller about status of the operation<br />
Type: Std_ReturnType<br />
Range: E_OK (0)<br />
E_NOT_OK (1)</td>
</tr>
<tr class="even">
<td rowspan="4"><strong>Affected static and global
variables</strong></td>
<td>Reads following variable</td>
</tr>
<tr class="odd">
<td><em>RxdSigData</em></td>
</tr>
<tr class="even">
<td><em>RxdSigDataExtdSts</em></td>
</tr>
<tr class="odd">
<td><em>RxdSigDataSrc</em></td>
</tr>
<tr class="even">
<td><strong>Affected inter-runnable variable</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Exclusive area access</strong></td>
<td>Needed to read from Signal data, Signal status and Signal Source
buffers</td>
</tr>
<tr class="even">
<td><strong>Configuration access</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Calibration data access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Called local functions</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>External Interface call</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Called by</strong></td>
<td>Application components which needs signal data received over IMC
Channels</td>
</tr>
</tbody>
</table>

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image23.emf)

## Sub-Function: GetSigImcData\_\<DATA_TYPE\>

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 74%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>GetSigImcData_&lt;DATA_TYPE&gt;</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>Server Runnable, Global</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>1) This server function is called by application components to get
particular Signal data received over IMC Channels and Signal
Status.<br />
2) There are 8 Server runnables defined to get signal data with signal
status received via Imc channels each of which called based on received
signal data type. Place holder &lt;DATA_TYPE&gt; can be any of the
following: f32 (float32), u32 (uint32), s32 (sint32), u16 (uint16), s16
(sint16), u08 (uint8), s08 (sint8), logl (boolean).</td>
</tr>
<tr class="odd">
<td rowspan="4"><strong>Parameters</strong></td>
<td>Requires following parameters</td>
</tr>
<tr class="even">
<td><em>SigId -</em> IMC Signal Id provided by IMC Arbitration
Configuration<br />
Type: uint16<br />
Range:<br />
0 to 65535</td>
</tr>
<tr class="odd">
<td><em>Data -</em> Pointer to the signal data buffer where signal data
to be copied<br />
Type: uint8*<br />
Valid Range: 0x00000001 to 0xFFFFFFFF</td>
</tr>
<tr class="even">
<td><em>Sts -</em> Pointer to signal status buffer where signal status
to be copied<br />
Type: ImcArbnRxSts1*<br />
Valid Range: 0x00000001 to 0xFFFFFFFF</td>
</tr>
<tr class="odd">
<td><strong> </strong></td>
<td>DataSrc -</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Return value</strong></td>
<td>Returns following value</td>
</tr>
<tr class="odd">
<td>ErrCod - Informs the caller about status of the operation<br />
Type: Std_ReturnType<br />
Range: E_OK (0)<br />
E_NOT_OK (1)</td>
</tr>
<tr class="even">
<td rowspan="3"><strong>Affected static and global
variables</strong></td>
<td>Reads following variable</td>
</tr>
<tr class="odd">
<td><em>RxdSigData</em></td>
</tr>
<tr class="even">
<td><em>RxdSigDataExtdSts</em></td>
</tr>
<tr class="odd">
<td><strong>Affected inter-runnable variable</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Exclusive area access</strong></td>
<td>Needed to read from Signal data and Signal status buffers</td>
</tr>
<tr class="odd">
<td><strong>Configuration access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Calibration data access</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Called local functions</strong></td>
<td>Calls following local function</td>
</tr>
<tr class="even">
<td><em>GetImcSigSts</em></td>
</tr>
<tr class="odd">
<td><strong>External Interface call</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Called by</strong></td>
<td>Application components which needs signal data received over IMC
Channels</td>
</tr>
</tbody>
</table>

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image24.emf)

## Sub-Function: RxFrmVldChk

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 74%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>RxFrmVldChk</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>Local</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>Evaluates validity of received Signal Group data based on CRC and
Rolling counter values and returns status that indicates whether given
Signal Group data, rolling counter values are valid or not. In addition
to that it tracks CRC and Rolling counter frame faults per Rate Group
per fault type (CRC / Rolling counter) using Frame Fault counters. This
function also tracks Skip counters and Resync counters for Rolling
counter evaluation.</td>
</tr>
<tr class="odd">
<td rowspan="8"><strong>Parameters</strong></td>
<td>Requires following parameters</td>
</tr>
<tr class="even">
<td><em>DataBuf -</em> Pointer to the received Signal Group data
buffer<br />
Type: uint8*<br />
Valid Range: 0x00000001 to 0xFFFFFFFF</td>
</tr>
<tr class="odd">
<td><em>FrmFltCntr -</em> Pointer to the frame fault counters for the
given Rate Group where frame faults to be accounted.<br />
Type: Ary2D_u8_2_2*<br />
Valid Range: 0x00000001 to 0xFFFFFFFF</td>
</tr>
<tr class="even">
<td><em>SigGroupDataSrc-</em> Imc Channel ID on which Signal Group data
received<br />
Type: ImcArbnRxDataSrc1<br />
Range:<br />
IMCARBNRXDATASRC_PRIM (0U)<br />
IMCARBNRXDATASRC_SECDRY (1U)<br />
IMCARBNRXDATASRC_NOSRC (2U)<br />
All other values are invalid</td>
</tr>
<tr class="odd">
<td><em>RateGroup -</em> Rate Group Id provided by IMC Arbitration
Configuration<br />
Type: uint8<br />
Range:<br />
IMCARBN_RATEGROUPID2MILLISEC_CNT_U08 (0U)<br />
IMCARBN_RATEGROUPID10MILLISEC_CNT_U08 (1U)<br />
IMCARBN_RATEGROUPID100MILLISEC_CNT_U08 (2U)<br />
All other values are invalid</td>
</tr>
<tr class="even">
<td><em>SigGroup -</em> Signal Group Id provided by IMC Arbitration
Configuration<br />
Type: uint8<br />
Range: 0 to 255</td>
</tr>
<tr class="odd">
<td>PrimSrcOnlySigGroup - Flag to indicate whether the given Signal
Group is only transmitted on Primary Source or No data received on
secondary source.<br />
Type: boolean<br />
TRUE – Primary Source only Signal Group or No data received on secondary
source<br />
FALSE – Transmtted on both Primary and Secondary sources</td>
</tr>
<tr class="even">
<td>IniTiOutChkCmpl - Initial time-out completion status<br />
Type: boolean<br />
TRUE – Time-out completed<br />
FALSE – Time-out not completed</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Return value</strong></td>
<td>Returns following value</td>
</tr>
<tr class="even">
<td>FrmSts - Informs the caller about validity of Rolling counter and
Data<br />
Type: ImcArbnRxRollgCntrSts1<br />
Range:<br />
ROLLGCNTRVLDNEWDATA (0)<br />
ROLLGCNTRVLDOLDDATA (1)<br />
ROLLGCNTRINVLD (2)</td>
</tr>
<tr class="odd">
<td rowspan="11"><strong>Affected static and global
variables</strong></td>
<td>Read and Write to following variables in sub-functions</td>
</tr>
<tr class="even">
<td><em>SigGroupSkipCntr</em></td>
</tr>
<tr class="odd">
<td><em>PrimSrcResyncCntr</em></td>
</tr>
<tr class="even">
<td><em>PrimSrcRollgCntrResync</em></td>
</tr>
<tr class="odd">
<td><em>ResyncOnPrimActv</em></td>
</tr>
<tr class="even">
<td><em>SecdrySrcResyncCntr</em></td>
</tr>
<tr class="odd">
<td><em>SecdrySrcRollgCntrResync</em></td>
</tr>
<tr class="even">
<td><em>ResyncOnSecdryActv</em></td>
</tr>
<tr class="odd">
<td><em>FrmFltCntr2MilliSec</em></td>
</tr>
<tr class="even">
<td><em>FrmFltCntr10MilliSec</em></td>
</tr>
<tr class="odd">
<td><em>FrmFltCntr100MilliSec</em></td>
</tr>
<tr class="even">
<td><strong>Affected inter-runnable variable</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Exclusive area access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Configuration access</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Calibration data access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td rowspan="4"><strong>Called local functions</strong></td>
<td>Calls following local function</td>
</tr>
<tr class="odd">
<td><em>Crc_CalculateCRC8</em></td>
</tr>
<tr class="even">
<td><em>ImcChResyncHndlg</em></td>
</tr>
<tr class="odd">
<td><em>VldtRollgCntr</em></td>
</tr>
<tr class="even">
<td><strong>External Interface call</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Called by</strong></td>
<td>Called by following functions</td>
</tr>
<tr class="even">
<td><em>ImcArbnRx</em></td>
</tr>
</tbody>
</table>

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image25.emf)

## Sub-Function: ImcChResyncHndlg

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 74%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>ImcChResyncHndlg</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>Local</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>Runs Resynchronization logic for Primary and Secondary sources</td>
</tr>
<tr class="odd">
<td rowspan="4"><strong>Parameters</strong></td>
<td>Requires following parameters</td>
</tr>
<tr class="even">
<td><em>SigGroupDataSrc-</em> Imc Channel ID on which Signal Group data
received<br />
Type: ImcArbnRxDataSrc1<br />
Range:<br />
IMCARBNRXDATASRC_PRIM (0U)<br />
IMCARBNRXDATASRC_SECDRY (1U)<br />
IMCARBNRXDATASRC_NOSRC (2U)<br />
All other values are invalid</td>
</tr>
<tr class="odd">
<td><em>SigGroup -</em> Signal Group Id provided by IMC Arbitration
Configuration<br />
Type: uint8<br />
Range: 0 to 255</td>
</tr>
<tr class="even">
<td><em>PrsntRollgCntr -</em> Present Rolling counter received for the
Signal Group<br />
Type: uint8<br />
Range: 0 to 31</td>
</tr>
<tr class="odd">
<td><strong>Return value</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td rowspan="7"><strong>Affected static and global
variables</strong></td>
<td>Read and Write to following variables in sub-functions</td>
</tr>
<tr class="odd">
<td><em>PrimSrcResyncCntr</em></td>
</tr>
<tr class="even">
<td><em>PrimSrcRollgCntrResync</em></td>
</tr>
<tr class="odd">
<td><em>ResyncOnPrimActv</em></td>
</tr>
<tr class="even">
<td><em>SecdrySrcResyncCntr</em></td>
</tr>
<tr class="odd">
<td><em>SecdrySrcRollgCntrResync</em></td>
</tr>
<tr class="even">
<td><em>ResyncOnSecdryActv</em></td>
</tr>
<tr class="odd">
<td><strong>Affected inter-runnable variable</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Exclusive area access</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Configuration access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Calibration data access</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Called local functions</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>External Interface call</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Called by</strong></td>
<td>Called by following functions</td>
</tr>
<tr class="even">
<td><em>RxFrmVldChk</em></td>
</tr>
</tbody>
</table>

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image26.emf)

## Sub-Function: CreatSigGroupData

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 74%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>CreatSigGroupData</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>Local</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>Collect Signal data for all signals configured under given Signal
Group, combine all into a uint32 data based on configuration and return
to the caller.</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Parameters</strong></td>
<td>Requires following parameters</td>
</tr>
<tr class="even">
<td><em>SigGroup_T_rec -</em> Pointer to the Signal Group configuration
data<br />
Type: SigGroupRec1 const *<br />
Valid Range: 0x00000001 to 0xFFFFFFFF</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Return value</strong></td>
<td>Returns following value</td>
</tr>
<tr class="even">
<td>RetData - Combined four byte data for given Signal Group
configuration<br />
Type: uint32<br />
Range:<br />
0x00000000 to 0xFFFFFFFF</td>
</tr>
<tr class="odd">
<td><strong>Affected static and global variables</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Affected inter-runnable variable</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Exclusive area access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Configuration access</strong></td>
<td>Accesses following configuration data</td>
</tr>
<tr class="odd">
<td><em>SIGGROUPCONFIG_REC</em></td>
</tr>
<tr class="even">
<td><strong>Calibration data access</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Called local functions</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Called local functions</strong></td>
<td>Calls following local function</td>
</tr>
<tr class="odd">
<td><em>Calls Signal access wrapper functions for each signal configured
under given Signal Group</em></td>
</tr>
<tr class="even">
<td><strong>External Interface call</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Called by</strong></td>
<td>Called by following functions</td>
</tr>
<tr class="even">
<td><em>ImcArbnTx</em></td>
</tr>
</tbody>
</table>

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image27.emf)

## Sub-Function: DecodSigGroupData

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 74%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>DecodSigGroupData</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>Local</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>Split given uint32 data into Signal data according to the
configuration for given Signal Group, store Signal values in Rx Signal
Data buffer, updates Signal Status and Signal Source.</td>
</tr>
<tr class="odd">
<td rowspan="5"><strong>Parameters</strong></td>
<td>Requires following parameters</td>
</tr>
<tr class="even">
<td><em>SigGroup_T_rec -</em> Pointer to the Signal Group configuration
data<br />
Type: SigGroupRec1 const *<br />
Valid Range: 0x00000001 to 0xFFFFFFFF</td>
</tr>
<tr class="odd">
<td>SigGroupRxData - Combined four bytes received data for given Signal
Group configuration<br />
Type: uint32<br />
Range:<br />
0x00000000 to 0xFFFFFFFF</td>
</tr>
<tr class="even">
<td>RxSigExtdSts1 - Extended Signal Status<br />
Type: ImcArbnRxExtdSts1<br />
Range:<br />
IMCARBNRXEXTDSTS_NEVERRXD (0U)<br />
IMCARBNRXEXTDSTS_MISS (1U)<br />
IMCARBNRXEXTDSTS_DATAINVLD (2U)<br />
IMCARBNRXEXTDSTS_PREVDATA (3U)<br />
IMCARBNRXEXTDSTS_DATAVLDWITHBACKUP (4U)<br />
IMCARBNRXEXTDSTS_DATAVLDWITHNOBACKUP (5U)<br />
IMCARBNRXEXTDSTS_STRTG (6U)<br />
All other values are invalid</td>
</tr>
<tr class="odd">
<td><em>RxDataSrc -</em> Imc Channel ID from which the Signal Group data
received<br />
Type: ImcArbnRxDataSrc1<br />
Range:<br />
IMCARBNRXDATASRC_PRIM (0U)<br />
IMCARBNRXDATASRC_SECDRY (1U)<br />
IMCARBNRXDATASRC_NOSRC (2U)<br />
All other values are invalid</td>
</tr>
<tr class="even">
<td><strong>Return value</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td rowspan="4"><strong>Affected static and global
variables</strong></td>
<td>Read and Write to following variables in sub-functions</td>
</tr>
<tr class="even">
<td><em>RxdSigData</em></td>
</tr>
<tr class="odd">
<td><em>RxdSigDataExtdSts</em></td>
</tr>
<tr class="even">
<td><em>RxdSigDataSrc</em></td>
</tr>
<tr class="odd">
<td><strong>Affected inter-runnable variable</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Exclusive area access</strong></td>
<td>Needed to write Imc Signal data, Signal Status and Signal source
buffers.</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Configuration access</strong></td>
<td>Accesses following configuration data</td>
</tr>
<tr class="even">
<td><em>ImcArbn_SigGroupConfig_Rec</em></td>
</tr>
<tr class="odd">
<td><strong>Calibration data access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Called local functions</strong></td>
<td>Calls following local function</td>
</tr>
<tr class="odd">
<td><em>GetBitMask</em></td>
</tr>
<tr class="even">
<td><strong>External Interface call</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Called by</strong></td>
<td>Called by following functions</td>
</tr>
<tr class="even">
<td><em>ImcArbrRx</em></td>
</tr>
</tbody>
</table>

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image28.emf)

## Sub-Function: GetBitMask

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 74%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>GetBitMask</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>Local</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>Returns bitmask for requested number of bits.</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Parameters</strong></td>
<td>Requires following parameters</td>
</tr>
<tr class="even">
<td>NrOfBits - Number of bits required to be set in the return
value<br />
Type: uint8<br />
Range:<br />
1 to 32</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Return value</strong></td>
<td>Returns following value</td>
</tr>
<tr class="even">
<td>BitMask - Bit mask for given number of bits<br />
Type: uint32<br />
Range:<br />
0x00000000 to 0xFFFFFFFF</td>
</tr>
<tr class="odd">
<td><strong>Affected static and global variables</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Affected inter-runnable variable</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Exclusive area access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Configuration access</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Calibration data access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Called local functions</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>External Interface call</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td rowspan="3"><strong>Called by</strong></td>
<td>Called by following functions</td>
</tr>
<tr class="odd">
<td><em>CreatSigGroupData</em></td>
</tr>
<tr class="even">
<td><em>DecodSigGroupData</em></td>
</tr>
</tbody>
</table>

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image29.emf)

## Sub-Function: GetImcFltParamByte

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 74%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>GetImcFltParamByte</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>Local</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>Evaluates Frame faults counters and returns IMC Arbitration fault
parameter byte to log / clear NTC 0x3F (IMC Arbitration fault). Bits
which are corresponding to particular fault that exceeds threshold limit
will be set in the return value. Refer below picture for details of bit
mapping in the parameter byte</td>
</tr>
<tr class="odd">
<td><strong>Parameters</strong></td>
<td>void</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Return value</strong></td>
<td>Returns following value</td>
</tr>
<tr class="odd">
<td>FltBitMask - Bit mask for given number of bits<br />
Type: uint8<br />
Range: Bitmask<br />
PRIMSRCCRCFLT_CNT_U08 (0x01U)<br />
PRIMSRCROLLGCNTRFLT_CNT_U08 (0x02U)<br />
SECDRYSRCCRCFLT_CNT_U08 (0x04U)<br />
SECDRYSRCROLLGCNTRFLT_CNT_U08 (0x08U)<br />
All other bits are unused.</td>
</tr>
<tr class="even">
<td rowspan="4"><strong>Affected static and global
variables</strong></td>
<td>Reads following variables</td>
</tr>
<tr class="odd">
<td><em>FrmFltCntr2MilliSec</em></td>
</tr>
<tr class="even">
<td><em>FrmFltCntr10MilliSec</em></td>
</tr>
<tr class="odd">
<td><em>FrmFltCntr100MilliSec</em></td>
</tr>
<tr class="even">
<td><strong>Affected inter-runnable variable</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Exclusive area access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Configuration access</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Calibration data access</strong></td>
<td>Accesses following calibration value in the sub-functions call</td>
</tr>
<tr class="even">
<td><em>ImcArbnFrmFltThd</em></td>
</tr>
<tr class="odd">
<td><strong>Called local functions</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>External Interface call</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Called by</strong></td>
<td>Called by following functions</td>
</tr>
<tr class="even">
<td><em>ImcArbnPer6</em></td>
</tr>
</tbody>
</table>

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image30.emf)

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image31.emf)

## Sub-Function: VldtRollgCntr

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 74%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>VldtRollgCntr</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>Local</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>Validates Rolling Counter</td>
</tr>
<tr class="odd">
<td rowspan="5"><strong>Parameters</strong></td>
<td>Requires following parameters</td>
</tr>
<tr class="even">
<td><em>SigGroupDataSrc-</em> Imc Channel ID on which Signal Group data
received<br />
Type: ImcArbnRxDataSrc1<br />
Range:<br />
IMCARBNRXDATASRC_PRIM (0U)<br />
IMCARBNRXDATASRC_SECDRY (1U)<br />
IMCARBNRXDATASRC_NOSRC (2U)<br />
All other values are invalid</td>
</tr>
<tr class="odd">
<td><em>RateGroup -</em> Rate Group Id provided by IMC Arbitration
Configuration<br />
Type: uint8<br />
Range:<br />
IMCARBN_RATEGROUPID2MILLISEC_CNT_U08 (0U)<br />
IMCARBN_RATEGROUPID10MILLISEC_CNT_U08 (1U)<br />
IMCARBN_RATEGROUPID100MILLISEC_CNT_U08 (2U)<br />
All other values are invalid</td>
</tr>
<tr class="even">
<td><em>SigGroup -</em> Signal Group Id provided by IMC Arbitration
Configuration<br />
Type: uint8<br />
Range: 0 to 255</td>
</tr>
<tr class="odd">
<td>PrsntRollgCntr- Present Rolling counter value received for the given
Signal Group<br />
Type: uint8<br />
Range: 0 to 31</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Return value</strong></td>
<td>Returns following value</td>
</tr>
<tr class="odd">
<td>FrmSts - Informs the caller about validity of Rolling counter and
Data<br />
Type: ImcArbnRxRollgCntrSts1<br />
Range:<br />
ROLLGCNTRVLDNEWDATA (0)<br />
ROLLGCNTRVLDOLDDATA (1)<br />
ROLLGCNTRINVLD (2)</td>
</tr>
<tr class="even">
<td rowspan="7"><strong>Affected static and global
variables</strong></td>
<td>Read and Write to following variables in sub-functions</td>
</tr>
<tr class="odd">
<td><em>PrimSrcResyncCntr</em></td>
</tr>
<tr class="even">
<td><em>PrimSrcRollgCntrResync</em></td>
</tr>
<tr class="odd">
<td><em>ResyncOnPrimActv</em></td>
</tr>
<tr class="even">
<td><em>SecdrySrcResyncCntr</em></td>
</tr>
<tr class="odd">
<td><em>SecdrySrcRollgCntrResync</em></td>
</tr>
<tr class="even">
<td><em>ResyncOnSecdryActv</em></td>
</tr>
<tr class="odd">
<td><strong>Affected inter-runnable variable</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Exclusive area access</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Configuration access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Calibration data access</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Called local functions</strong></td>
<td>Calls following local function</td>
</tr>
<tr class="even">
<td><em>VldtRollgCntrAlg</em></td>
</tr>
<tr class="odd">
<td><strong>External Interface call</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Called by</strong></td>
<td>Called by following functions</td>
</tr>
<tr class="odd">
<td><em>RxFrmVldChk</em></td>
</tr>
</tbody>
</table>

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image32.emf)

## Sub-Function: VldtRollgCntrAlg

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 74%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>VldtRollgCntrAlg</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>Local</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>Implements Rolling counter algorithm</td>
</tr>
<tr class="odd">
<td rowspan="5"><strong>Parameters</strong></td>
<td>Requires following parameters</td>
</tr>
<tr class="even">
<td><em>SigGroupDataSrc-</em> Imc Channel ID on which Signal Group data
received<br />
Type: ImcArbnRxDataSrc1<br />
Range:<br />
IMCARBNRXDATASRC_PRIM (0U)<br />
IMCARBNRXDATASRC_SECDRY (1U)<br />
IMCARBNRXDATASRC_NOSRC (2U)<br />
All other values are invalid</td>
</tr>
<tr class="odd">
<td><em>RateGroup -</em> Rate Group Id provided by IMC Arbitration
Configuration<br />
Type: uint8<br />
Range:<br />
IMCARBN_RATEGROUPID2MILLISEC_CNT_U08 (0U)<br />
IMCARBN_RATEGROUPID10MILLISEC_CNT_U08 (1U)<br />
IMCARBN_RATEGROUPID100MILLISEC_CNT_U08 (2U)<br />
All other values are invalid</td>
</tr>
<tr class="even">
<td><em>SigGroup -</em> Signal Group Id provided by IMC Arbitration
Configuration<br />
Type: uint8<br />
Range: 0 to 255</td>
</tr>
<tr class="odd">
<td>PrsntRollgCntr- Present Rolling counter value received for the given
Signal Group<br />
Type: uint8<br />
Range: 0 to 31</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Return value</strong></td>
<td>Returns following value</td>
</tr>
<tr class="odd">
<td>FrmSts - Informs the caller about validity of Rolling counter and
Data<br />
Type: ImcArbnRxRollgCntrSts1<br />
Range:<br />
ROLLGCNTRVLDNEWDATA (0)<br />
ROLLGCNTRVLDOLDDATA (1)<br />
ROLLGCNTRINVLD (2)</td>
</tr>
<tr class="even">
<td rowspan="4"><strong>Affected static and global
variables</strong></td>
<td>Reads or writes following variables in sub-functions</td>
</tr>
<tr class="odd">
<td><em>PrevRollgCntrRxd</em></td>
</tr>
<tr class="even">
<td><em>SigGroupSkipCntr</em></td>
</tr>
<tr class="odd">
<td><em>SigGroupDataSrc</em></td>
</tr>
<tr class="even">
<td><strong>Affected inter-runnable variable</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Exclusive area access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Configuration access</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Calibration data access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Called local functions</strong></td>
<td>Calls following local function</td>
</tr>
<tr class="odd">
<td><em>RollgCntrSeqChk</em></td>
</tr>
<tr class="even">
<td><strong>External Interface call</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Called by</strong></td>
<td>Called by following functions</td>
</tr>
<tr class="even">
<td><em>VldtRollgCntr</em></td>
</tr>
</tbody>
</table>

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image33.emf)

## Sub-Function: RollgCntrSeqChk

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 74%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>RollgCntrSeqChk</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>Local</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>Checks whether present rolling counter value received on IMC channel
falls within the range lower and upper drift limits from anticipated
rolling counter.</td>
</tr>
<tr class="odd">
<td rowspan="5"><strong>Parameters</strong></td>
<td>Requires following parameters</td>
</tr>
<tr class="even">
<td>PrsntRollgCntr- Present Rolling counter value received for the given
Signal Group<br />
Type: uint8<br />
Range: 0 to 31</td>
</tr>
<tr class="odd">
<td>AntcptdRollCntr - Anticipated Rolling counter value for the given
Signal Group<br />
Type: uint8<br />
Range: 0 to 31</td>
</tr>
<tr class="even">
<td>UpprDriftLim - Drift limit on the lower from Anticipated Rolling
counter<br />
Type: uint8<br />
Range: 0 to 31</td>
</tr>
<tr class="odd">
<td>LwrDriftLim - Drift limit on the lower side from Anticipated Rolling
counter<br />
Type: uint8<br />
Range: 0 to 31</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Return value</strong></td>
<td>Returns following value</td>
</tr>
<tr class="odd">
<td>RollgCntrVld - Returns validity of Rolling counter<br />
Type: boolean<br />
Range:<br />
TRUE - Rolling counter value acceptable<br />
FALSE - Rolling counter value not acceptable</td>
</tr>
<tr class="even">
<td><strong>Affected static and global variables</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Affected inter-runnable variable</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Exclusive area access</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Configuration access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Calibration data access</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Called local functions</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>External Interface call</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Called by</strong></td>
<td>Called by following functions</td>
</tr>
<tr class="even">
<td><em>VldtRollgCntrAlg</em></td>
</tr>
</tbody>
</table>

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image34.emf)

## Sub-Function: NoDataHndlg

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 74%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>NoDataHndlg</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>Local</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>Handles No data reception cases for Singal Status, Reset counter,
Skip counter and Resync counters</td>
</tr>
<tr class="odd">
<td rowspan="7"><strong>Parameters</strong></td>
<td>Requires following parameters</td>
</tr>
<tr class="even">
<td>RxSigExtdSts1 - Extended signal Status value<br />
Type: ImcArbnRxExtdSts1<br />
Range:<br />
IMCARBNRXEXTDSTS_NEVERRXD (0U)<br />
IMCARBNRXEXTDSTS_MISS (1U)<br />
IMCARBNRXEXTDSTS_DATAINVLD (2U)<br />
IMCARBNRXEXTDSTS_PREVDATA (3U)<br />
IMCARBNRXEXTDSTS_DATAVLDWITHBACKUP (4U)<br />
IMCARBNRXEXTDSTS_DATAVLDWITHNOBACKUP (5U)<br />
IMCARBNRXEXTDSTS_STRTG (6U)<br />
Other values are invalid</td>
</tr>
<tr class="odd">
<td><em>RxDataSrc -</em> Imc Channel ID<br />
Type: ImcArbnRxDataSrc1<br />
Range:<br />
IMCARBNRXDATASRC_PRIM (0U)<br />
IMCARBNRXDATASRC_SECDRY (1U)<br />
IMCARBNRXDATASRC_NOSRC (2U)<br />
All other values are invalid</td>
</tr>
<tr class="even">
<td><em>RateGroup -</em> Rate Group Id provided by IMC Arbitration
Configuration<br />
Type: uint8<br />
Range:<br />
IMCARBN_RATEGROUPID2MILLISEC_CNT_U08 (0U)<br />
IMCARBN_RATEGROUPID10MILLISEC_CNT_U08 (1U)<br />
IMCARBN_RATEGROUPID100MILLISEC_CNT_U08 (2U)<br />
All other values are invalid</td>
</tr>
<tr class="odd">
<td><em>SigGroup -</em> Signal Group Id provided by IMC Arbitration
Configuration<br />
Type: uint8<br />
Range: 0 to 255</td>
</tr>
<tr class="even">
<td>PrimSrcNoDataRxd - No data Received on Primary Source flag<br />
Type: boolean<br />
TRUE – No data received<br />
FALSE – Data received</td>
</tr>
<tr class="odd">
<td>SecdrySrcNoDataRxd - No data Received on Secondary Source flag<br />
Type: boolean<br />
TRUE – No data received<br />
FALSE – Data received</td>
</tr>
<tr class="even">
<td><strong>Return value</strong></td>
<td>void</td>
</tr>
<tr class="odd">
<td rowspan="9"><strong>Affected static and global
variables</strong></td>
<td>Read and Write to following variables in sub-functions</td>
</tr>
<tr class="even">
<td><em>SigGroupSkipCntr</em></td>
</tr>
<tr class="odd">
<td><em>PrimSrcResyncCntr</em></td>
</tr>
<tr class="even">
<td><em>SecdrySrcResyncCntr</em></td>
</tr>
<tr class="odd">
<td><em>PrimSrcRollgCntrResync</em></td>
</tr>
<tr class="even">
<td><em>SecdrySrcRollgCntrResync</em></td>
</tr>
<tr class="odd">
<td><em>ResyncOnPrimActv</em></td>
</tr>
<tr class="even">
<td><em>ResyncOnSecdryActv</em></td>
</tr>
<tr class="odd">
<td><em>RxdSigDataExtdSts</em></td>
</tr>
<tr class="even">
<td><strong>Affected inter-runnable variable</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Exclusive area access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Configuration access</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Calibration data access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Called local functions</strong></td>
<td>Calls following local function</td>
</tr>
<tr class="odd">
<td><em>EvlSigGroupNeverRxdMissSts</em></td>
</tr>
<tr class="even">
<td><strong>External Interface call</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Called by</strong></td>
<td>Called by following functions</td>
</tr>
<tr class="even">
<td><em>ImcArbnRx</em></td>
</tr>
</tbody>
</table>

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image35.emf)

## Sub-Function: EvlSigGroupNeverRxdMissSts

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 74%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>EvlSigGroupNeverRxdMissSts</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>Local</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>Evaluates Signal missing / never received cases and updates signals
status.</td>
</tr>
<tr class="odd">
<td rowspan="3"><strong>Parameters</strong></td>
<td>Requires following parameters</td>
</tr>
<tr class="even">
<td><em>RateGroup -</em> Rate Group Id provided by IMC Arbitration
Configuration<br />
Type: uint8<br />
Range:<br />
IMCARBN_RATEGROUPID2MILLISEC_CNT_U08 (0U)<br />
IMCARBN_RATEGROUPID10MILLISEC_CNT_U08 (1U)<br />
IMCARBN_RATEGROUPID100MILLISEC_CNT_U08 (2U)<br />
All other values are invalid</td>
</tr>
<tr class="odd">
<td><em>SigGroup -</em> Signal Group Id provided by IMC Arbitration
Configuration<br />
Type: uint8<br />
Range: 0 to 255</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Return value</strong></td>
<td>Returns following value</td>
</tr>
<tr class="odd">
<td>RxSigExtdSts1 - Extended Signal Status<br />
Type: ImcArbnRxExtdSts1<br />
Range:<br />
IMCARBNRXEXTDSTS_NEVERRXD (0U)<br />
IMCARBNRXEXTDSTS_MISS (1U)<br />
IMCARBNRXEXTDSTS_DATAINVLD (2U)<br />
IMCARBNRXEXTDSTS_PREVDATA (3U)<br />
IMCARBNRXEXTDSTS_DATAVLDWITHBACKUP (4U)<br />
IMCARBNRXEXTDSTS_DATAVLDWITHNOBACKUP (5U)<br />
IMCARBNRXEXTDSTS_STRTG (6U)<br />
All other values are invalid</td>
</tr>
<tr class="even">
<td rowspan="3"><strong>Affected static and global
variables</strong></td>
<td>Reads / Writes to following variables in functions</td>
</tr>
<tr class="odd">
<td><em>SigGroupNeverRxd</em></td>
</tr>
<tr class="even">
<td><em>SigGroupMissCntr</em></td>
</tr>
<tr class="odd">
<td><strong>Affected inter-runnable variable</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Exclusive area access</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Configuration access</strong></td>
<td>Accesses following configuration data</td>
</tr>
<tr class="even">
<td><em>MISSSIGGROUPTIOUT_CNT_U08</em></td>
</tr>
<tr class="odd">
<td><strong>Calibration data access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Called local functions</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>External Interface call</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Called by</strong></td>
<td>Called by following functions</td>
</tr>
<tr class="odd">
<td><em>ImcArbnRx</em></td>
</tr>
</tbody>
</table>

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image36.emf)

## Sub-Function: OvrdSigStsDurgStrtUp

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 74%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>OvrdSigStsDurgStrtUp</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>Local</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>Sets signal status as STARTING in the Signal Status buffer when
initial start-up timer is still running.</td>
</tr>
<tr class="odd">
<td rowspan="3"><strong>Parameters</strong></td>
<td>Requires following parameters</td>
</tr>
<tr class="even">
<td><em>SigGroup -</em> Signal Group Id provided by IMC Arbitration
Configuration<br />
Type: uint8<br />
Range: 0 to 255</td>
</tr>
<tr class="odd">
<td>IniTiOutChkCmpl - Initial time-out completion status<br />
Type: boolean<br />
TRUE – Time-out completed<br />
FALSE – Time-out not completed</td>
</tr>
<tr class="even">
<td><strong>Return value</strong></td>
<td>void</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Affected static and global
variables</strong></td>
<td>Writes to following variables in functions</td>
</tr>
<tr class="even">
<td><em>RxSigDataExtdSts</em></td>
</tr>
<tr class="odd">
<td><strong>Affected inter-runnable variable</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Exclusive area access</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Configuration access</strong></td>
<td>Accesses following configuration data</td>
</tr>
<tr class="even">
<td><em>SIGGROUPCONFIG_REC</em></td>
</tr>
<tr class="odd">
<td><strong>Calibration data access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Called local functions</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>External Interface call</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Called by</strong></td>
<td>Called by following functions</td>
</tr>
<tr class="odd">
<td><em>ImcArbnRx</em></td>
</tr>
</tbody>
</table>

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image37.emf)

## Sub-Function: GetImcSigSts

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 74%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>GetImcSigSts</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>Local</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>Remaps Extended signal status value to basic version of Signal
Status</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Parameters</strong></td>
<td>Requires following parameters</td>
</tr>
<tr class="even">
<td>SigExtdSts - Extended Signal Status<br />
Type: ImcArbnRxExtdSts1<br />
Range:<br />
IMCARBNRXEXTDSTS_NEVERRXD (0U)<br />
IMCARBNRXEXTDSTS_MISS (1U)<br />
IMCARBNRXEXTDSTS_DATAINVLD (2U)<br />
IMCARBNRXEXTDSTS_PREVDATA (3U)<br />
IMCARBNRXEXTDSTS_DATAVLDWITHBACKUP (4U)<br />
IMCARBNRXEXTDSTS_DATAVLDWITHNOBACKUP (5U)<br />
IMCARBNRXEXTDSTS_STRTG (6U)<br />
All other values are invalid</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Return value</strong></td>
<td>Returns following value</td>
</tr>
<tr class="even">
<td>RetSts - Remapped basic Signal Status<br />
Type:ImcArbnRxSts1<br />
Range:<br />
IMCARBNRXSTS_NODATA (0U)<br />
IMCARBNRXSTS_VLD (1U)<br />
IMCARBNRXSTS_INVLD (2U)<br />
All other values are invalid</td>
</tr>
<tr class="odd">
<td><strong>Affected static and global variables</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Affected inter-runnable variable</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Exclusive area access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Configuration access</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Calibration data access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Called local functions</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>External Interface call</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Called by</strong></td>
<td>Called by following functions</td>
</tr>
<tr class="odd">
<td><em>GetSigImcData_&lt;DATA_TYPE&gt;</em></td>
</tr>
</tbody>
</table>

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image38.emf)

## Sub-Function: NoDataRxd

### Hardware Related Design

None

### Software Related Design

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 74%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>NoDataRxd</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Function scope</strong></td>
<td>Local</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>Evaluates no data received condition</td>
</tr>
<tr class="odd">
<td rowspan="3"><strong>Parameters</strong></td>
<td>Requires following parameters</td>
</tr>
<tr class="even">
<td><em>StrtByte -</em> Start byte of given Signal Group<br />
Type: uint8<br />
Range: 0 to 255</td>
</tr>
<tr class="odd">
<td><em>EndByte -</em> End byte of given Signal Group<br />
Type: uint8<br />
Range: 0 to 255</td>
</tr>
<tr class="even">
<td rowspan="2"><strong>Return value</strong></td>
<td>Returns following value</td>
</tr>
<tr class="odd">
<td><em>RetVal-</em> Indicates whether No data received<br />
Type: boolean<br />
Range:<br />
TRUE - No data received<br />
FALSE - Data Received</td>
</tr>
<tr class="even">
<td><strong>Affected static and global variables</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Affected inter-runnable variable</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Exclusive area access</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Configuration access</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>Calibration data access</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td><strong>Called local functions</strong></td>
<td>None</td>
</tr>
<tr class="even">
<td><strong>External Interface call</strong></td>
<td>None</td>
</tr>
<tr class="odd">
<td rowspan="2"><strong>Called by</strong></td>
<td>Called by following functions</td>
</tr>
<tr class="even">
<td><em>ImcArbnRx</em></td>
</tr>
</tbody>
</table>

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image39.emf)

# Timing / Execution Constraints

## Rationale / Comments

• ImcArbnPer1, ImcArbnPer2 and ImcArbnPer3 periodic functions shall be
called prior to calling respective primary and secondary signal source
transmit layer functions.

• ImcArbnPer4, ImcArbnPer5 and ImcArbnPer6 periodic functions shall be
called after calling respective primary and secondary signal source
receive layer functions.

• ImcArbn Receive periodics (ImcArbnPer4, ImcArbnPer5 and ImcArbnPer6)
functions shall run prior to the ImcArbn Transmit periodic functions
((ImcArbnPer1, ImcArbnPer2 and ImcArbnPer3).

## Rates and State Execution

| **Sub-Function** | **Rate (ms)** | **Cold Init** | **Warm Init** | **Operate** | **Disable** |
|---------------------|-----------|----------|-----------|-----------|----------|
| ImcArbnPer1      | 2             | Req           | Req           | Req         | Req         |
| ImcArbnPer2      | 10            | Req           | Req           | Req         | Req         |
| ImcArbnPer3      | 100           | Req           | Req           | Req         | Req         |
| ImcArbnPer4      | 2             | Req           | Req           | Req         | Req         |
| ImcArbnPer5      | 10            | Req           | Req           | Req         | Req         |
| ImcArbnPer6      | 100           | Req           | Req           | Req         | Req         |

# Serial Communications Interfaces

None

# Additional Information

## Imc Arbitration – Configuration

### Hardware Related Design

None

### Software Related Design

#### Imc Signals 

A Signal Group is a basic element of communication for the Imc
Arbitration component.

Signals that are need to be transmitted by IMC shall be configured under
any of the Signal Group based on their transmit rate requirements.

Following are the general design assumptions about the signals that are
transmitted by Imc Arbitration:

1.  All IMC signals are accessible via RTE to pack it in a particular
    Signal Group.

2.  Data type of the signals that are transmitted by Imc Arbitration can
    be anyone of the following: boolean, uint8, sint8, uint16, sint16,
    uint32, sint32 and float32. No other types of signals are supported.

#### This component defines unique LOCAL constants for each of the configured signals as Signal ID. Following format is used to define the Signal ID.  [this-component-defines-unique-local-constants-for-each-of-the-configured-signals-as-signal-id.-following-format-is-used-to-define-the-signal-id.]

#### Format:  [format]

#### IMCARBN\_\<signalname\>\_CNT_U16 [imcarbn_signalname_cnt_u16]

#### signalname – name of the signal in upper case as defined in Imc Arbitration configuration. [signalname-name-of-the-signal-in-upper-case-as-defined-in-imc-arbitration-configuration.]

#### Signal Group (SG)

Following elements forms a Signal Group:

Pattern ID: The pattern identification is used as a start of frame to
synchronize data on asynchronous communication protocols such as SCI. As
shown in the below figure, the pattern ID is 3 bits (101b).

Rolling Counter: The rolling counter is used to monitor for new data. If
the rolling counter has been updated, the data is new. If the rolling
counter maintains the same value, the data is old. As shown in the below
picture, the Rolling Counter is 5 bits.

Signal Group ID: The message ID is used to identify the received data
group. As shown in the below picture the Message Id is 8 bits. All data
bytes (0 –3) have the same message ID.

Data Byte 0 – 3: Contains packed data of all signals configured for a
given Signal Group.

CRC: The Cyclic Redundancy Check is calculated on the message ID and all
of the data bytes. This check ensures the integrity of the information
being transmitted. The pattern ID and rolling counter are inherently
protected by comparing to the complement, and therefore do not need CRC
protection. As shown in the figure 2, the CRC is 8 bits.

Pattern Id compliment and Rolling Counter Compliment: The pattern
identification and rolling counter complements are used to identify the
end of frame, and also as a basic data reception check. If the start of
frame (Pattern ID and Rolling Counter) and this frame XOR’d together
equal all ones, then the full frame is assumed to have been captured and
can be passed on for rolling counter and CRC checks. As shown in the
below picture, the Pattern ID Complement is 3 bits and The Rolling
Counter Complement is 5 bits.

#### This component defines unique global constant for each of the Signal Groups. Following format is used to define the Signal Groups.  [this-component-defines-unique-global-constant-for-each-of-the-signal-groups.-following-format-is-used-to-define-the-signal-groups.]

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image40.emf)

#### Format:  [format-1]

#### IMCARBN\_\<SigGroupName\>\_CNT_U08 [imcarbn_siggroupname_cnt_u08]

SigGroupName – Signal Group name in uppercase as defined during
configuration

#### Rate Group

Imc System supports transmission / reception of Signal Groups at three
different rates: 2ms, 10ms and 100ms. Every Signal Group shall be listed
under any one of the Rate Group. All Signal Groups that are configured
under given Rate Group processed at the same rate. E.g. a Signal Group
configured under 2ms rate is processed in a 2ms periodic.

Following global constant values are defined to identify the Rate Groups
in the system:

> IMCARBN_RATEGROUPID2MILLISEC_CNT_U08 (0U)
>
> IMCARBN_RATEGROUPID10MILLISEC_CNT_U08 (1U)

IMCARBN_RATEGROUPID100MILLISEC_CNT_U08 (2U)

Below picture depicts data organization for Imc Arbitration Tx and Rx
frames

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image41.emf)

Below picture depicts Configuration Description for the component.

![](ElectricPowerSteering_Renesas_GM_G2KCA_website/docs/AR350A_ImcArbn_Design/Design/mediax/media/image42.emf)

#### Types Definitions for Configuration Data

<table>
<colgroup>
<col style="width: 28%" />
<col style="width: 71%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><em>typedef uint32 (*GetSigVal)(void);</em></td>
<td>Typedef for the function pointer that will read data from the source
FDD. Note that the return value is always considered as (NOT
type-casted) uint32 in order to reduce complexity in Tx/Rx buffer
handling.</td>
</tr>
<tr class="even">
<td><p>typedef struct</p>
<p>{</p>
<p>GetSigVal GetSigValOper;</p>
<p>uint16 SigId_u16;</p>
<p>uint8 DestSize_u08;</p>
<p>uint8 StrtLocn_u08;</p>
<p>}SigPrmRec1;</p></td>
<td><p>Structure that defines properties of a signal that need to be
communicated across two microcontrollers.</p>
<p>GetSigValOper – Pointer to the wrapper function which returns current
value of the signal.</p>
<p>SigId_u16 – Signal Id – Unique ID generated for the signal by Imc
Arbitrator. Throughout the system, this would be used to get value of
particular signal.</p>
<p>DestSize_u08 – Number of bits used for the signal to pack it in its
Signal Group.</p>
<p>StrtLocn_u08 - Position of the signal in its Signal Group.</p></td>
</tr>
<tr class="odd">
<td><p>typedef struct</p>
<p>{</p>
<p>SigPrmRec1 const *SigPrm;</p>
<p>uint8 NrOfSig_u08;</p>
<p>uint8 SigGroupId_u08;</p>
<p>boolean PrimSrcOnlySigGroup_logl;</p>
<p>}SigGroupRec1;</p></td>
<td><p>Structure that defines properties of a Signal Group (SG).</p>
<p>SigPrm – Pointer to an array of SigPrm_Rec1 type structures. This
holds reference to all signals that are configured under particular
Signal Group.</p>
<p>NrOfSig_u08 – Number of signals that are packed into particular
Signal Group.</p>
<p>SigGroupId_u08 - Unique ID generated for the Signal Group by Imc
Arbitrator. Throughout the system, this would be used to get frame of
particular Signal Group.</p>
<p>PrimSrcOnlySigGroup_logl– Indicates whether the Signal Group to be
transmitted only on Primary channel.</p>
<p>TRUE – Primary only Tx Group.</p>
<p>FALSE – Both Primary and Secondary Tx Group.</p></td>
</tr>
</tbody>
</table>

#### Configuration Structure: SIGGROUPCONFIG_REC

This configuration is an array of structures of type SigGroupRec1
containing all Imc configuration data for each configured Signal Groups
which will be generated during build time based on the configuration.

Each array element of this structure corresponds to a Signal Group
configured. Positon of each Signal Group in this structure will be based
out of Rate Group: First Signal Groups configured under 2ms Rate Group,
then Signal Groups configured under 10ms Rate Group and finally Signal
Groups configured under 100ms Rate Group.

**Sample configuration:**

> */\* General configuration for signal group TestSigGroup1 \*/*
>
> *const SigGroupRec1
> SIGGROUPCONFIG_REC\[IMCARBN_TOTALNROFSIGGROUP_CNT_U08\] =*
>
> *{*
>
> *{*
>
> *&TESTSIGGROUP1\[0\], /\* Signal group config structure for
> TestSigGroup1 signal group \*/*
>
> *1U,/\* Number of signals configured in the signal group \*/*
>
> *IMCARBN_SGTESTSIGGROUP1_CNT_U08, /\* Signal Group identifier \*/*
>
> *TRUE, /\* Primary Only Signal group \*/*
>
> *},*
>
> *{*
>
> *&ImcArbn\_ TESTSIGGROUP2\[0\], /\* Signal group config structure for
> TestSigGroup2 signal group \*/*
>
> *1U,/\* Number of signals configured in the signal group \*/*
>
> *IMCARBN_SGTESTSIGGROUP2_CNT_U08, /\* Signal Group identifier \*/*
>
> *FALSE, /\* Primary Only Signal group \*/*
>
> *},*
>
> *{*
>
> *&ImcArbn\_ TESTSIGGROUP3\[0\], /\* Signal group config structure for
> this signal group \*/*
>
> *5U,/\* Number of signals configured in the signal group \*/*
>
> *IMCARBN_SGTESTSIGGROUP3_CNT_U08, /\* Signal Group identifier \*/*
>
> *FALSE, /\* Primary Only Signal group \*/*
>
> *},*
>
> *};*

#### Configuration Structure: \<Signal Group Name\>

This configuration array of structure of type *SigPrmRec1* contains Imc
configuration data for individual Signal Groups which will be generated
during build time based on the configuration.

Individual elements in this array correspond to properties of each
Signal configured under given Signal Group.

Following naming convention will be followed while generating Signal
Group structures:

***\<SIGGROUPNAME\>\_REC***

**Sample Configuration:**

*/\* Signal configuration for the signal group TestSigGroup1 \*/*

*STATIC const SigPrmRec1 TESTGIGGROUP1_REC\[\] =*

*{*

*{*

*&GetTestSig1, /\* Pointer to the function which provides Signal data
\*/*

*IMCARBN_TESTSIG1_CNT_U08, /\* Signal Id \*/*

*8U,/\* Number of bits to be used in the Signal Group for this signal
\*/*

*0U, /\* Position of the signal from LSB \*/*

*},*

*{*

*&GetTestSig2, /\* Pointer to the function which provides Signal data
\*/*

*IMCARBN_TESTSIG2_CNT_U08, /\* Signal Id \*/*

*8U,/\* Number of bits to be used in the Signal Group for this signal
\*/*

*8U, /\* Position of the signal from LSB \*/*

*},*

*{*

*&GetTestSig3, /\* Pointer to the function which provides Signal data
\*/*

*IMCARBN_TESTSIG3_CNT_U08, /\* Signal Id \*/*

*16U,/\* Number of bits to be used in the Signal Group for this signal
\*/*

*16U, /\* Position of the signal from LSB \*/*

*},*

*};*

#### Signal data access functions: Get\<Signal Name\>

This component will generate a Signal data access function for every IMC
Signal configured in the configuration.

Irrespective of configured Signal data type, this function will return
uint32 value.

Prototype:

***uint32 GetSignalName\> (void) ;***

This function will read data for configured Signal from respective
application component.

Signals of type uint32 will be returned without any typecasting.

Boolean, uint8, sint8, uint16, sint16 signals will be typecasted to
uint32 and typecassted value will be returned.

Float32 signals will be **read** as uint32 without typecasting and will
be returned as uint32 (i.e this means underlying float data format will
not be disturbed).

**Sample Function 1:** TestSig1 is a float signal

> */\* Wrapper function to get value of TestSig1 \*/*
>
> *uint32 GetTestSig1(void)*
>
> *{*
>
> *uint32 RetVal_Uls_T_u32;*
>
> *float32 SigVal_Uls_T_f32;*
>
> *SigVal_Uls_T_f32 = Rte_Read_TestSig1_Val ();*
>
> *RetVal_Uls_T_u32 = \*((uint32\*)&SigVal_Uls_T_f32);*
>
> *return(RetVal_Uls_T_u32);*
>
> *}*

**Sample Function 2:** TestSig2 is a boolean signal

> */\* Wrapper function to get value of TestSig2 \*/*
>
> *uint32 GetTestSig2(void)*
>
> *{*
>
> *uint32 RetVal_Uls_T_u32;*
>
> *RetVal_Uls_T_u32 = Rte_Read_TestSig2_Val ();*
>
> *return(RetVal_Uls_T_u32);*
>
> *}*

#### Configuration Array: RATEGROUPOFFS_CNT_U08

This configuration array provides offset for accessing for each Rate
group configuration data in the configuration structure
ImcArbn_SigGroupConfig_Rec. It is defined as follows:

RATEGROUPOFFS_CNT_U08 \[IMCARBN_NROFRATEGROUP_CNT_U08\] = { 0U,
IMCARBN_NROF2MILLISECRATEGROUP_CNT_U08,
IMCARBN_NROF2MILLISECRATEGROUP_CNT_U08 +
IMCARBN_NROF10MILLISECRATEGROUP_CNT_U08 };

#### Configuration Array: NRSIGGROUPINRATEGROUP_CNT_U08

This configuration array provides number of Signal group defined for
each Rate Group in the configuration structure
ImcArbn_SigGroupConfig_Rec. It is defined as follows:

NRSIGGROUPINRATEGROUP_CNT_U08 \[IMCARBN_NROFRATEGROUP_CNT_U08\] = {
IMCARBN_NROF2MILLISECRATEGROUP_CNT_U08,
IMCARBN_NROF10MILLISECRATEGROUP_CNT_U08,
IMCARBN_NROF100MILLISECRATEGROUP_CNT_U08 };

#### Configuration Array: MISSSIGGROUPTIOUT_CNT_U08

This configuration array provides missing count value for individual
Rate Groups. Count values are corresponding to be number of cycles of
respective Rate Groups. It is defined as follows:

MISSSIGGROUPTIOUT_CNT_U08\[IMCARBN_NROFRATEGROUP_CNT_U08\] = {
MISSTHD2MILLISECRATEGROUP_CNT_U08, MISSTHD10MILLISECRATEGROUP_CNT_U08,
MISSTHD100MILLISECRATEGROUP_CNT_U08

}

## Imc Signal Mapping for Receiving FDDs

### Hardware Related Design

None

### Software Related Design

Since configured Imc Signal names may not match with the signal name
which is used in by receiving FDDs, Signal mapping mechanism is provided
to resolve mapping between IMC input signals and user of IMC input
signals.

FDDs which needs signal from Imc Arbitration component shall use
following naming convention for naming Signal ID ( which is an argument
for GetSigImcData_xxx):

Format:

***IMCARBN\_\<componentshortname\>\<signalname\>\_CNT_U16***

> *componentshortname* – Short name of the component which is interested
> in receiving the signal from Imc Arbitration.
>
> *signalname* – name of the signal as defined by the receiving
> component.
>
> Note that ownership of this constant is still with Imc Arbitration
> (hence the “***IMCARBN\_”*** prefix).

Imc Arbitration component will generate configurations to map these
Signal IDs with its own Signal IDs for each of the Imc signal.

e.g.

**IMCARBN_FDD1OPTIONALSIGNAME1_CNT_U16**

## Enumerations - Signal Status, Extended Signal Status and Signal Source

### Hardware Related Design

None

### Software Related Design

This component uses three RTE enumerations and one local enumeration:

1.  **Extended Signal Status (ImcArbnRxExtdSts1):** Following table
    indicates list of values and its meaning.

| **Extended Signal Status**                                                | **Meaning**                                   |
|----------------------------------------------|--------------------------|
| IMCARBNRXEXTDSTS_STRTG                                                    | Initial Start-up time not completed           |
| IMCARBNRXEXTDSTS_DATAVLDWITHBACKUP / IMCARBNRXEXTDSTS_DATAVLDWITHNOBACKUP | Valid Data Received                           |
| IMCARBNRXEXTDSTS_NEVERRXD                                                 | Message never received                        |
| IMCARBNRXEXTDSTS_DATAINVLD                                                | Invalid - CRC, Rolling Counter                |
| IMCARBNRXEXTDSTS_PREVDATA                                                 | Message Missing - Threshold yet to be reached |
| IMCARBNRXEXTDSTS_MISS                                                     | Message Missing - Threshold reached           |

Extended signal status value would be returned to the caller when the
Server Runnable GetSigImcDataExtdSts invoked.

1.  **Signal Status (ImcArbnRxSts1):** Following table indicates list of
    values and its meaning.

| **Signal Status**   | **Use case**                                                                  |
|--------------------------------------------|----------------------------|
| IMCARBNRXSTS_NODATA | Initial Start-up time not completed                                           |
| IMCARBNRXSTS_VLD    | Valid Data Received                                                           |
| IMCARBNRXSTS_INVLD  | Message never received, Invalid CRC, Invalid Rolling Counter, Message missing |

Signal status value would be returned to the caller when the Server
Runnable GetSigImcData invoked.

1.  **Signal Data Source (ImcArbnRxDataSrc1):** Following table
    indicates list of values and its meaning.

| **Signal Data Source**  | **Meaning**                                   |
|-------------------------|-----------------------------------------------|
| IMCARBNRXDATASRC_PRIM   | Signal received on Primary Source             |
| IMCARBNRXDATASRC_SECDRY | Signal received on Secondary Source           |
| IMCARBNRXDATASRC_NOSRC  | Signal is not received on any of the sources. |

Signal data source would be returned to the caller when the Server
Runnable GetSigImcDataExtdSts invoked.

1.  **Rolling counter status (ImcArbnRxRollgCntrSts1):** This enum used
    to indicate status of Rolling counter evaluation:

| **Signal Data Source** | **Meaning**                         |
|------------------------|-------------------------------------|
| ROLLGCNTRVLDNEWDATA    | Rolling counter valid with New data |
| ROLLGCNTRVLDOLDDATA    | Rolling counter valid with old data |
| ROLLGCNTRINVLD         | Rolling counter invalid.            |

# Revision Record & Change Approval

<table>
<colgroup>
<col style="width: 7%" />
<col style="width: 12%" />
<col style="width: 14%" />
<col style="width: 65%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Rev</strong></td>
<td><strong>Date</strong></td>
<td><strong>Change Control #</strong></td>
<td><strong>Change Description</strong></td>
</tr>
<tr class="even">
<td>1</td>
<td>15/01/17</td>
<td>EA4#9025</td>
<td>Initial Version</td>
</tr>
<tr class="odd">
<td>2</td>
<td>17/01/17</td>
<td>EA4#9025</td>
<td><p>Updates:</p>
<p>1. Tx flow chart to remove ternary operator in the Rolling counter
calculation</p>
<p>2. SetRxSigGroup – Data type for Buf changed from uint8* to
Ary1D_u8_8*</p></td>
</tr>
</tbody>
</table>

{% endraw %}