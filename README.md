# Smart 3-axis Force Torque Sensor 3FT2000-D65-C (ENG)

Rev. 2026.10.16

- [Foreword](#foreword)
  - [Notice](#notice)
  - [Manufacturer](#manufacturer)
  - [Safety Precautions](#safety-precautions)
  - [Warning & Caution](#warning--caution)
- [1. Product Overview](#1-product-overview)
  - [1.1 Smart 3-axis Force Torque Sensor, 3FT2000-D65](#11-smart-3-axis-force-torque-sensor-3ft2000-d65)
  - [1.2 Key features](#12-key-features)
  - [1.3 Specifications](#13-specifications)
  - [1.4 Complex Loading Range](#14-complex-loading-range)
- [2. Installation Guide](#2-installation-guide)
  - [2.1 Basic Components](#21-basic-components)
  - [2.2 Mounting](#22-mounting)
  - [2.3 Axes and Drawings](#23-axes-and-drawings)
  - [2.4 Cable](#24-cable)
- [3. Communication](#3-communication)
  - [3.1 Default CAN Setting](#31-default-can-setting)
  - [3.2 User Commands](#32-user-commands)
  - [3.3 Sensor Data Output](#33-sensor-data-output)
- [4. Additional information](#4-additional-information)
  - [4.1 USB-to-CAN interfaces](#41-usb-to-can-interfaces)
- [F & Q](#f--q)
- [Revision History](#revision-history)

![3FT2000-D65 rendering](img/3ft2000-d65-rendering.jpg)

## Foreword

Thank you for purchasing our Force Torque sensor. This manual contains the information necessary for the correct use of the AIDIN ROBOTICS 3FT2000-D65 sensor.  
Please carefully read this manual when using this software.   
Please note that the basic performance of the product will not be exhibited when the robot system is used out of conditions.  
This manual describes possible dangers and consequences using Force Torque sensor. Be sure to comply with safety precautions written in this manual to use safety and correctly.

### Notice

This manual Do **NOT** allow copy, reproduction or share without authorization of AIDIN ROBOTICS.  
Please notify us any errors in this manual or the provided instructions.

### Manufacturer

AIDIN ROBOTICS

### Safety Precautions

Installation of Force Torque sensor **MUST** be performed by qualified personnel in accordance with national and local codes. Please carefully read this manual when using this software.

### Warning & Caution

> [!CAUTION]
> This symbol indicates that a danger of possible serious injury or death exists if the associated instructions are not followed properly.

> [!WARNING]
> This symbol indicates that a danger of possible harm to people or physical damage to equipment and facilities exists if the associated instructions are not followed properly.

## 1. Product Overview

### 1.1 Smart 3-axis Force Torque Sensor, 3FT2000-D65

### 1.2 Key features

- Smart 3-axis force/torque sensor
- All-in-one sensor (No additional amplifier)
- Digital output communications (CAN, CAN-FD)
- Easy installation and data collection
- Grippers, robot hands, collaborative robot, industrial robot

### 1.3 Specifications

| Index | Unit | Value |
|---|---|---|
| **Operating voltage** | **VDC** | **5** |
| Max. safe excitation voltage | VDC | 12 |
| **Nominal force range (F\_XYZN)** | **N** | **2000** |
| **Nominal torque range (M\_XYZN)** | **Nm** | **100** |
| Limit force (F\_XYZL) | N | 3000 |
| Limit torque (M\_XYZL) | Nm | 120 |
| Force Noise-free resolution (STD) | N | 12 |
| Torque Noise-free resolution (STD) | Nm | 1 |
| Dimensions | mm | D65 x H21 |
| Weight | g |  |
| Temperature | ℃ | 10-50 |
| Sample rate | Hz | 1000 $\color{red}\textsf{(Default 500)}$ |
| Interfaces | Mbps | CAN 2.0 : Nominal 1 <br>CAN-FD : Nominal 1 / Data 4 (BRS) |
| Wire | Length: 10 cm | For User: <br>CAN\_H / CAN\_L / VCC / GND |

### 1.4 Complex Loading Range

The sensor can operate up to its nominal capacity, while a single axis load. On Nominal capacity reading is incorrect and invalid.

The nominal capacity of composite loading is The following diagram illustrates a complex loading scenario. The sensor cannot operate outside the normal operating area

The following graph shows the range of payloads and tool lengths that can be used with 3FT2000-D65 sensor for applications requiring high or moderate precision.

- The total percentage of the calibrated range used by Fz and Txy axes is greater than 105%. Refer to the following Fz, Txy equation.

$$
\sqrt{{T_x}^2+{T_y}^2}/{T_{xy}Range} +|{F_z}|/{F_{z}Range} >105 \%
$$

## 2. Installation Guide

### 2.1 Basic Components

- 3FT2000-D65 x 1 EA

### 2.2 Mounting

- **M4 bolt 3.5 Nm required for tightening**
- **Performance cannot be guaranteed and A/S not possible when disassembling internal/external bolts**
- **Sensor mounting example**

![Sensor mounting example](img/mounting-example.png)

- **CAUTION OF CABLE CUTTING AND EXCESS PULLING**
- **Secure the sensor line with the robot so that it does not pull as it moves**
  - **Do not fix it to the robot using cable ties, etc., or use cable ties to fix it in a bundle shape like other wires**
  - **We recommend that you use Velcro to fix it with the robot, and please use Velcro to fix it when fixing it in a bundle form with other lines**

> [!NOTE]
> **Performance CANNOT be guaranteed if not followed to the tightening torque guide**.

> [!NOTE]
> **If the sensor line is not fixed to the robot, the output signal may have a noise due to the pulled by robot**

### 2.3 Axes and Drawings

![Sensor axes](img/sensor-axes.png)

Drawing File :

![3FT2000-D65 drawing](img/drawing.jpg)

- [3FT2000-D65_v1.pdf](files/3FT2000-D65_v1.pdf)

### 2.4 Cable

- Cable pin out
  - Length: 10cm

![Cable pin out](img/cable-pinout.png)

> [!NOTE]
> To acquire CAN data, a 120 Ω termination resistor is required between CAN H and CAN L.

## 3. Communication

### 3.1 Default CAN Setting

- **The output rate can be changed from 100 Hz to 1000 Hz** $\color{red}\textsf{(Default 500 Hz)}$
- **Please refer to the “3.2 User Commands” below for how to change it**
- CAN-2.0
  - Nominal bitrate : 1Mbps
  - Data bitrate : 1Mbps
  - $\color{red}\textsf{RX ID MASK : 0x200, 0x210}$
  - $\color{red}\textsf{FD-tolerant (no error frames on CAN FD frames)}$
- CAN-FD
  - $\color{red}\textsf{Nominal bitrate : 1Mbps (Sample point 87.5\%)}$
  - $\color{red}\textsf{Data bitrate : 4Mbps (BRS mode, Sample point 75\%)}$
  - $\color{red}\textsf{RX ID MASK : 0x200, 0x210}$
- CAN-FD PARAMETER SETTING (Clock 80 MHz, FDSET3)

| Item | Nominal | Data |
|---|---|---|
| Bit rate | $\color{red}\textsf{1 Mbps}$ | $\color{red}\textsf{4 Mbps}$ |
| Sample point | $\color{red}\textsf{87.5\%}$ | $\color{red}\textsf{75\%}$ |
| Prescaler | $\color{red}\textsf{1}$ | $\color{red}\textsf{1}$ |
| TSEG1 | $\color{red}\textsf{69}$ | $\color{red}\textsf{14}$ |
| TSEG2 | $\color{red}\textsf{10}$ | $\color{red}\textsf{5}$ |
| SJW | $\color{red}\textsf{10}$ | $\color{red}\textsf{4}$ |
| TDC | - | $\color{red}\textsf{ON}$ |
| TDCO (SSP offset) | - | $\color{red}\textsf{15 (75\%)}$ |
| TDCF | - | 15 |

### 3.2 User Commands

- RX CAN IDs : $\color{red}\textsf{0x200}$ (CAN 2.0) , $\color{red}\textsf{0x210}$ (CAN FD)  
  TX CAN IDs :The pre-configured TX CAN IDs are $\color{red}\textsf{0x201}$ (CAN 2.0) and $\color{red}\textsf{0x211}$ (CAN FD). Accordingly, the 'current TX CAN ID' in the table below is represented as [0x01, 0x02] or [0x11, 0x02] (LSB first).

- Data Transmission Procedure  
  On power-up, the sensor automatically outputs Float Combined data in CAN FD mode (BRS ON).  
  To change the output, the host must send the **CAN MODE** configuration command followed by the **TRANSMIT DATA** request command.  
  Example:   
  **CAN MODE:** ID: `0x210`, Data: `0x11 0x02 0x04 0x03`  
  **TRANSMIT DATA:** ID: `0x210`, Data: `0x11 0x02 0x03 0x06`

| COMMAND | RX CAN ID | Data[0] | Data[1] | Data[2] | Data[3]<br>See table below | Data[4] | Data[5] |
|---|---|---|---|---|---|---|---|
| SENSOR TX CAN ID SET | $\color{red}\textsf{0x200}$ <br>$\color{red}\textsf{0x210}$ | current<br>TX CAN <br>ID (LSB) | current<br>TX CAN <br>ID (MSB) | 0x01 | 0x01<br><br>0x02 | TX CAN 2.0 <br>ID(LSB)<br>TX CAN FD<br>ID(LSB) | TX CAN 2.0<br> ID(MSB)<br>TX CAN FD <br>ID(MSB) |
| BIAS |  |  |  | 0x02 |  |  |  |
| TRANSMIT DATA |  |  |  | 0x03 | 0x01~0x06 |  |  |
| CAN MODE |  |  |  | 0x04 | 0x01<br>0x02<br>0x03 |  |  |
| SAMPLE RATE SET |  |  |  | 0x05 | 0x01<br>0x02<br>0x03 <br>0x04 |  |  |
| FD PARAMETER SET |  |  |  | 0x06 | 0x01<br>0x02<br>0x03<br>0x04 |  |  |
| AVERAGE FILTER SET |  |  |  | 0x07 | 0x01~0xff |  |  |
| TX CAN ID CONFIRM |  | 0xFF | 0xFE | 0xFC | 0x01<br>0x02 |  |  |
| FACTORY RESET |  | 0xFF | 0xFE | 0xFD |  |  |  |

| COMMAND | Data[3] DESCRIPTION |
|---|---|
| SENSOR TX CAN ID SET | 0x01 : TX CAN 2.0 ID SET  ex) ID(LSB) = 0x23, ID(MSB) = 0x01,  Resulting ID 0x123<br>0x02 : TX CAN FD ID SET  ex) ID(LSB) = 0x56, ID(MSB) = 0x04,  Resulting ID 0x456 |
| BIAS | Bias |
| TRANSMIT DATA | 0x01 : INT Transmitting data<br>0x02 : INT Transmitting data (Temperature compensated)<br>0x03 : INT Combined Transmitting data  (FD only)<br>0x04 : INT Combined Transmitting data (Temperature compensated, FD only)<br>0x05 : Float Combined Transmitting data  (FD only)<br>0x06 : Float Combined Transmitting data (Temperature compensated, FD only, Default) |
| CAN MODE | 0x01 : CAN 2.0 mode<br>0x02 : CAN FD mode BRS OFF (Effective from 2026.07.02)<br>0x03 : CAN FD mode BRS ON (Effective from 2026.07.02) (Default) |
| SAMPLE RATE SET | 0x01 :RATE 100Hz  <br>0x02 :RATE 250Hz<br>$\color{red}\textsf{0x03 :RATE 500Hz (Default)}$<br>0x04 :RATE 1000Hz |
| FD PARAMETER SET | 0x01 :FDSET1 <br>0x02 :FDSET2<br>0x03 :FDSET3 (Default) <br>0x04 :FDSET4 |
| AVERAGE FILTER SET | 0x01~0xff  (Effective from 2026.10.12) <br>(0x01 : Default, no filtering) |
| TX CAN ID CONFIRM | 0x01 :TX CAN 2.0 ID : data field not used (DLC = 0)<br>0x02 :TX CAN FD ID : data field not used  (DLC = 0) |
| FACTORY RESET | FDSET3 (Default) <br>$\color{red}\textsf{RATE 500Hz (Default)}$<br>Zero Bias (Default) <br>current TX CAN 2.0 ID : $\color{red}\textsf{0x201}$ , current TX CAN FD ID : $\color{red}\textsf{0x211}$ (Default)<br> FILTER : 0x01 (Default)|

### 3.3 Sensor Data Output

> [!NOTE]
> **To stabilize the sensor signal, it is recommended to have a running time of about 30 minutes.**
> **Please leave the sensor data on for at least 10 minutes before using it
> The first 10 minutes of sensor output data can cause data to flow.**

**Force INT Transmitting data (data[2] : 0x03, data[3] : 1 or 2)**

| INDEX | TX CAN ID | DLC | data[0] | data[1] | data[2] | data[3] | data[4] | data[5] |
|---|---|---|---|---|---|---|---|---|
| FINT | 2.0 ID $\color{red}\textsf{0x201}$<br>FD ID $\color{red}\textsf{0x211}$ | 6 | Fx(LSB) | Fx(MSB) | Fy(LSB) | Fy(MSB) | Fz(LSB) | Fz(MSB) |

- $\color{red}\textsf{Fx Output = 0}$
- $\color{red}\textsf{Fy Output = 0}$
- Fz Output = Fz(MSB)\*256 + Fz(LSB)
- $\color{red}\textsf{Force[N] = Force Output/10}$

> [!NOTE]
> **The final calculated Force and Torque values need to be cast into 16-bit integers.**

**Torque INT Transmitting data (data[2] : 0x03, data[3] : 1 or 2)**

| INDEX | TX CAN ID | DLC | data[0] | data[1] | data[2] | data[3] | data[4] | data[5] |
|---|---|---|---|---|---|---|---|---|
| TINT | 2.0 ID $\color{red}\textsf{0x202}$<br>FD ID $\color{red}\textsf{0x212}$ | 6 | Tx(LSB) | Tx(MSB) | Ty(LSB) | Ty(MSB) | Tz(LSB) | Tz(MSB) |

- Tx Output = Tx(MSB)\*256 + Tx(LSB)
- Ty Output = Ty(MSB)\*256 + Ty(LSB)
- $\color{red}\textsf{Tz Output = 0}$
- $\color{red}\textsf{Torque[Nm] = Torque Output/100}$

> [!NOTE]
> **The final calculated Force and Torque values need to be cast into 16-bit integers.**

![INT data output example](img/data-output-int.png)

**Combined INT Transmitting data (data[2] : 0x03, data[3] : 3 or 4 )**

| INDEX | TX CAN ID | DLC | data[0] | data[1] | data[2] | data[3] | data[4] | data[5] |
|---|---|---|---|---|---|---|---|---|
| CINT | FD ID $\color{red}\textsf{0x213}$ | 12 | Fx(LSB) | Fx(MSB) | Fy(LSB) | Fy(MSB) | Fz(LSB) | Fz(MSB) |

| INDEX | data[6] | data[7] | data[8] | data[9] | data[10] | data[11] |
|---|---|---|---|---|---|---|
| CINT | Tx(LSB) | Tx(MSB) | Ty(LSB) | Ty(MSB) | Tz(LSB) | Tz(MSB) |

- $\color{red}\textsf{Fx Output = 0}$
- $\color{red}\textsf{Fy Output = 0}$
- Fz Output = Fz(MSB)\*256 + Fz(LSB)
- Tx Output = Tx(MSB)\*256 + Tx(LSB)
- Ty Output = Ty(MSB)\*256 + Ty(LSB)
- $\color{red}\textsf{Tz Output = 0}$
- $\color{red}\textsf{Force[N] = Force Output/10}$
- $\color{red}\textsf{Torque[Nm] = Torque Output/100}$

> [!NOTE]
> **The final calculated Force and Torque values need to be cast into 16-bit integers**

![Combined INT data output example](img/data-output-combined-int.png)

**Combined Float Transmitting data (data[2] : 0x03, data[3] : 5 or 6)**

| INDEX | TX CAN ID | DLC | data[0~3] | data[4~7] | data[8~11] | data[12~15] | data[16~19] | data[20~23] |
|---|---|---|---|---|---|---|---|---|
| CFLOAT | FD ID $\color{red}\textsf{0x213}$ | 24 | Fx | Fy | Fz | Tx | Ty | Tz |

- $\color{red}\textsf{float Fx\_Output = 0;}$
- $\color{red}\textsf{float Fy\_Output = 0;}$
- `uint32_t Fz_Raw = (Fz(MSB) << 24) | (Fz(3rd) << 16) | (Fz(2nd) << 8) | (Fz(LSB));`
- `float Fz_Output = *(float *)&Fz_Raw ;`
- `uint32_t Tx_Raw = (Tx(MSB) << 24) | (Tx(3rd) << 16) | (Tx(2nd) << 8) | (Tx(LSB));`
- `float Tx_Output = *(float *)&Tx_Raw ;`
- `uint32_t Ty_Raw = (Ty(MSB) << 24) | (Ty(3rd) << 16) | (Ty(2nd) << 8) | (Ty(LSB));`
- `float Ty_Output = *(float *)&Ty_Raw ;`
- $\color{red}\textsf{float Tz\_Output = 0;}$
- $\color{red}\textsf{Force[N] = Force Output}$
- $\color{red}\textsf{Torque[Nm] = Torque Output}$

> [!NOTE]
> **The final calculated Force and Torque values need to be cast into float.**

![Combined Float data output example](img/data-output-combined-float.png)

> [!NOTE]
> $\color{red}\textsf{The calculation of the data must follow the little-endian format.}$
> ![Little-endian format](img/little-endian.png)

## 4. Additional information

### 4.1 USB-to-CAN interfaces

**PCAN-USB FD Device (USB to CAN FD)**

- **You may use a different CAN-enabled board, but use peak-system converter to use the sample program**

![PCAN-USB FD](img/pcan-usb-fd.png)

- Device Item number IPEH-004022
  - <https://www.peak-system.com/PCAN-USB-FD.365.0.html?&L=1>
- PCAN-View (Windows Software for Displaying)
  - <https://www.peak-system.com/PCAN-View.242.0.html?&L=1>

## F & Q

**Q. What is the waterproof grade?**

A. The sensor is not waterproof or dustproof.

**Q. What does NC mean?**

A. NC stands for Not Connected.

**Q. What happens if the sensor is used outside the operating temperature range?**

A. Temperature changes within the allowable range are compensated by the calibration values. However, using the sensor outside the recommended temperature range distorts the measurements and results in abnormal output values.

**Q. Is it possible to develop additional software?**

A. Additional software development is available through separate consultation and agreement.

**Q. Can I extend the cable?**

A. We are not responsible for any problems caused by the use of cables not manufactured by AIDIN ROBOTICS. It is recommended that the cable length be less than 1 m, up to a maximum of 3 m.

**Q. Is it okay to disassemble the sensor myself?**

A. Disassembling the sensor voids the A/S policy and may cause the sensor calibration values to shift.

## Revision History

| Date | Description |
|---|---|
| 2026.10.16 | CAN settings updated (RX/TX CAN ID, RX ID MASK, CAN-FD bit timing, default sample rate 500 Hz, power-up output) (Current version) |
| [2026.10.14](https://github.com/yb25-kim/3FT2000_D65_Share_X2/blob/3b8cdfe9402f163b72399c0c472810de9acaab7f/README.md) | Unused axes (Fx, Fy, Tz) shown as = 0; RX ID MASK display fixed |
| 2026.10.13 | Minor wording revisions |
| 2026.10.12 | AVERAGE FILTER SET |
| 2026.07.24 |  |
| 2026.07.02 | CAN MODE options updated (CAN FD BRS OFF / BRS ON) |
| 2026.04.28 |  |
