# Public Domain Documents

- [Notes](#notes)
  - [CubieBoard 2](#cubieboard-2)

---

## Notes

Open and convert `.dwg` and `.dxf` with FreeCAD and ODA File Converter, see:
https://askubuntu.com/a/1136178

---

### CubieBoard 2

#### Construction

| Release    | Schematic                           | Layout (PCB)                        | 2D Drawing                          | 3D Model                            | Status     |
| :--------: | :---------------------------------: | :---------------------------------: | :---------------------------------: | :---------------------------------: | :--------: |
| V1         | [PDF][dCB2V1PSC]                    | 2012-09-09                          | [DXF][dCB2V1DXF] ([PDF][dCB2V1P2D]) |                                     | **EOL**    |
| V2         | [PDF][dCB2V2PSC]                    | 2015-12-11                          |                                     | [STP][dCB2V2STP] ([PDF][dCB2V2P3D]) |            |

[dCB2V1PSC]:
   Cubietech/CubieBoard1/CAD/cubieboard_schematic_2012-08-08.pdf
   "2012-08-08 (A10-cubieboard-2012-08-08, Rev: V1.0)"
[dCB2V1DXF]:
   Cubietech/CubieBoard1/CAD/Cubieboard1&2%20Mechanical_120909.dxf
   "2012-09-09"
[dCB2V1P2D]:
   Cubietech/CubieBoard1/CAD/Cubieboard1&2%20Mechanical_120909.pdf
   "2012-09-09"
[dCB2V2PSC]:
   Cubietech/CubieBoard2/CAD/cb2_a20_20151211.pdf
   "2015-11-24 (A20-cubieboard-2015-11-24, Rev: V1.0)"
[dCB2V2STP]:
   Cubietech/CubieBoard2/CAD/CubieBoard2-20151211-EMMC/CubieBoard2-20151211-3D%20model.stp
   "2016-07-28"
[dCB2V2P3D]:
   Cubietech/CubieBoard2/CAD/CubieBoard2-20151211-EMMC/CubieBoard2-3D-Lateral2.pdf
   "2016-07-28"

#### Components

##### Electronic Parts

| Component                                          | Manufactor                                    | Name                                     | V1 **(EOL)**    | V2              | Package         | Refs            |
| :------------------------------------------------- | :-------------------------------------------- | :--------------------------------------- | :-------------: | :-------------: | :-------------- | :-------------: |
| Central Procesing Unit (CPU), ARM Cortex-A7 @ 1GHz | [*Allwinner*](Allwinner/00-comefrom-urls)     | [**A20**](Allwinner/A20)                 | `U1`            | `U1`            | FBGA441-0.8mm   | [IMG][iCB2CPU]  |
| Random Access Memory (DDR3-SDRAM), 1GB @ 480MHz    | [*GT*](GT/00-comefrom-urls)                   | [**GT8UB256M16BP**](GT/GT8UB256M16BP)    | `U2`, `U3`      | `7U1`, `7U2`    | FBGA96-0.8mm    | [IMG][iCB1DDR3] |
|                                                    | [*Hynix*](Hynix/00-comefrom-urls)             | [**H5TQ4G63AFR**](Hynix/H5TQ4G63AFR)     |                 |                 |                 | [IMG][iCB2DDR3] |
| NAND Technology Flash (NAND-Flash), 4GB            | [*Hynix*](Hynix/00-comefrom-urls)             | [**H27UBG8T2BTR**](Hynix/H27UBG8T2BTR)   | `U4`            | `U2`            | TSOP48-0.5mm    | [IMG][iCB2NAND] |
| NAND Technology Flash (NAND-Flash), 8GB            |                                               | [**H27UCG8T2BTR**](Hynix/H27UCG8T2BTR)   |                 |                 |                 |                 |
| 2nd SD Card                                        |                                               |                                          |                 | `CARD2`         |                 | [IMG][iCB2SDC]  |
| TSOP SD (tSD) Card (1.1/2.0) NAND Flash, 4G        | [*Foresee*](Foresee/00-comefrom-urls)         | [**NCTSTS86-04G**](Foresee/NCTSTS86-04G) |                 |                 |                 | [IMG][iCB2TSD]  |
| embedded Multi Media Card (eMMC) NAND Flash, 4G    | [*Foresee*](Foresee/00-comefrom-urls)         | [**NCEFEH58-08G**](Foresee)              |                 | `U20A`          | FBGA169-0.5mm   | [IMG][iCB2EMMC] |
| Power Management IC (PMIC), Li-Battery Charger     | [*X-Powers*](X-Powers/00-comefrom-urls)       | [**AXP209**](X-Powers/AXP209)            | `U6`            | `12U2`          | QFN48-0.4mm     | [IMG][iCB2PMIC] |
| Step Down Regulator, 1.5V (DDR3), 3.3V (I/O)       | [*GMT*](GMT/00-comefrom-urls)                 | [**G5725**](GMT)                         |                 | `12U1`, `12U3`  | SOT23-5-0.95mm  |                 |
| Step Down Regulator, 1.5V (DDR3), 3.3V (I/O)       |                                               |  **TCS4199**                             | `U5`, `U7`      |                 | SOT23-5         |                 |
| LDO Voltage Regulator, 2.5V (SATA)                 | [*TCS*](TCS/00-comefrom-urls)                 | [**TCS2108-25**](TCS)                    | `U8`            | `12U4`          | SOT25-0.95mm    |                 |
|                                                    | [*Chipown*](Chipown/00-comefrom-urls)         | [**AP1231**](Chipown)                    |                 |                 |                 |                 |
| pMOSFET 2.5-V (G-S) 2A, 5V (SATA)                  | [*AOSMD*](AOSMD/00-comefrom-urls)             | [**AO3423**](AOSMD)                      |                 | `9Q4`           | SOT23-0.95mm    | [IMG][iCB2SATA] |
| pMOSFET 2.5-V (G-S) 1A, 5V (SATA), 3.3V (EMAC)     | [*TCS*](TCS/00-comefrom-urls)                 | [**TCS1305**](TCS)                       | `Q1`, `Q6`      |                 | SOT23-0.95mm    | [IMG][iCB1SATA] |
| Low RDS(ON) Load Switch, VBUS USB Host             | [*TCS*](TCS/00-comefrom-urls)                 | [**TCS9708**](TCS)                       | `U10`, `U11`    | `U4`, `U5`      | SOT23-5-0.95mm  |                 |
| Low RDS(ON) Load Switch, VBUS USB OTG              | [*Silergy*](Silergy/00-comefrom-urls)         | [**SY6280**](Silergy)                    |                 | `U6`            | SOT23-5-0.95mm  |                 |
|                                                    | [*TCS*](TCS/00-comefrom-urls)                 | [**TCS9708**](TCS)                       | `U12`           |                 |                 |                 |
| 10/100M Fast Ethernet PHY Receiver (EMAC)          | [*Realtek*](Realtek/00-comefrom-urls)         | [**RTL8201CP**](Realtek/RTL8201CP)       | `U13`           | `U8`            | LQFP48-0.5mm    | [IMG][iCB2EMAC] |
| IR Receiver                                        | [*Vishay*](Vishay/00-comefrom-urls)           | [**HS0038B**](Vishay)                    |                 | `U3`            |                 |                 |
|                                                    |                                               | [**HS0038B-NEC**](Vishay)                | `U9`            |                 |                 |                 |

[iCB2CPU]:
   Cubietech/CubieBoard2/IMG/cubieboard2-9.jpg
   "Allwinner A20 Cortex-A7 DualCore Mali 400 MP2"
[iCB2DDR3]:
   Cubietech/CubieBoard2/IMG/cubieboard2-10.jpg
   "1 GB Hynix DDR3 32 Bit Width 256M*16*2pcs"
[iCB2NAND]:
   Cubietech/CubieBoard2/DOC/cubieboard2-20120909-NAND.jpg
   "CubieBoard2 20120909 Nand"
[iCB2SDC]:
   Cubietech/CubieBoard2/DOC/cubieboard2-20120909-TFC2SDC.jpg
   "CubieBoard2 20120909 DualCard"
[iCB2TSD]:
   Cubietech/CubieBoard2/DOC/cubieboard2-20120909-TSD.jpg
   "CubieBoard2 20120909 TSD"
[iCB2EMMC]:
   Cubietech/CubieBoard2/DOC/cubieboard2-20151211-EMMC.jpg
   "CubieBoard2 20151211 EMMC"
[iCB2PMIC]:
   Cubietech/CubieBoard2/IMG/cubieboard2-14.jpg
   "Intelligent PMU Support Dynamic Voltage and Frequency Scaling (DVFS)"
[iCB2SATA]:
   Cubietech/CubieBoard2/IMG/cubieboard2-13.jpg
   "SATA 2.0 3 GBPS 2.5'' SSD"
[iCB2EMAC]:
   Cubietech/CubieBoard2/IMG/cubieboard2-12.jpg
   "Support 10/100Mbps RJ45"

#### Assembly

| [![zCB2BOARD]][iCB2BOARD]                                             |
| :-------------------------------------------------------------------: |
| *CubieBoard 2 - top (component side) - bottom (print/solder side)*    |

[zCB2BOARD]:
   https://images.weserv.nl/?url=raw.githubusercontent.com/lipro-armbian/pddocs/master/Cubietech/CubieBoard2/IMG/cubieboard2-8.jpg&trim=10
[iCB2BOARD]:
   Cubietech/CubieBoard2/IMG/cubieboard2-8.jpg
   "Board 2012-09-09"

* [How To Distinguish Your CubieBoard 2 Version](Cubietech/CubieBoard2/DOC/How%20To%20Distinguish%20Your%20CubieBoard2%20Version.pdf)
* http://www.cubietech.com/product-detail/cubieboard2
* http://www.cubietech.com/product-detail/cubieboard2-dualcard
* https://linux-sunxi.org/Cubietech_Cubieboard2
* https://github.com/allwinner-zh/documents

##### Console

| ![r12]&#x2757;<span style='color:#f03c15;'>TTL 3.3V</span>&#x2757;![r12] |
| :----------------------------------------------------------------------: |
| &#x2B95; `console=ttyS0,115200n8`                                        |
| [![zCB2CONS]][iCB2CONS]                                                  |

[zCB2CONS]:
   https://images.weserv.nl/?url=raw.githubusercontent.com/lipro-armbian/pddocs/master/Cubietech/USBUARTCable/IMG/Cubieboard.UART-TTL_wire_colors.jpg&w=300&trim=10
[iCB2CONS]:
   Cubietech/USBUARTCable/IMG/Cubieboard.UART-TTL_wire_colors.jpg
   "Console 2012-09-09"

* https://linux-sunxi.org/Cubietech_Cubieboard2#Adding_a_serial_port
* http://linux-sunxi.org/Cubieboard/TTL
* http://linux-sunxi.org/UART#UART-USB_dongle

##### Expansion Ports

| [![zCB2EXPPD]][iCB2EXPPD] | [![zCB2GPIOD]][iCB2GPIOD] |
| :-----------------------: | :-----------------------: |
| [PDF][dCB2EXPPD]          | [PDF][dCB2GPIOD]          |

[zCB2EXPPD]:
   https://images.weserv.nl/?url=raw.githubusercontent.com/lipro-armbian/pddocs/master/Cubietech/CubieBoard1/CAD/a10_a20_cubieboard_expansion_ports.png&w=600&trim=10
[iCB2EXPPD]:
   Cubietech/CubieBoard1/CAD/a10_a20_cubieboard_expansion_ports.png
   "CubieBoard 2 Expansion Ports Drawing Top: Drawing"
[dCB2EXPPD]:
   Cubietech/CubieBoard1/CAD/a10_a20_cubieboard_expansion_ports.pdf
   "CubieBoard 2 Expansion Ports Drawing Top: Drawing"
[zCB2GPIOD]:
   https://images.weserv.nl/?url=raw.githubusercontent.com/lipro-armbian/pddocs/master/Cubietech/CubieBoard1/CAD/gpio_defination_large.jpg&w=600&trim=10
[iCB2GPIOD]:
   Cubietech/CubieBoard1/CAD/gpio_defination_large.jpg
   "Cubian GPIO Pin Definition Top: Drawing"
[dCB2GPIOD]:
   Cubietech/CubieBoard1/CAD/gpio_defination_cubian.pdf
   "Cubian GPIO Pin Definition Top: Drawing"

#### Armbian

* https://www.armbian.com/cubieboard-2/ (End of Support)

---
