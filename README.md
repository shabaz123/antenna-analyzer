# Antenna Analyzer
This repository contains the detail to construct a VHF/UHF antenna analyzer instrument designed by VK5JST (Amateur Radio, May 2005). Refer to the original article for more information concerning it. The design was entered into KiCad software by TDARS, to create the printed circuit boards described here.

# Overview
The analyzer has two connections; one from the radio transmitter (2W max, but you could use an attenuator), and one to the antenna. Note that the instrument also supports HF, but you'll still need to limit power to 2W max, or use an attenuator.

There's a 4-position rotary selector knob. By using that, it is possible to select SWR or R/Z modes, and observe these values on the built-in moving-coil meter movement. The meter is fitted with a detailed scale, although the diagram here just shown LO/HI.

<img width="100%" align="left" src="images/overview-diag.jpg">

# One-Time Calibration
To calibrate the instrument one-time after building it, you just need a HF signal source of adjustable power. Do the following:

(1) Connect a low-power HF source to the RF input on the instrument, and ensure that nothing is attached to the antenna connector (to simulate a bad antenna)

(2) Set the selector knob to the leftmost position which is the **Check Input** position.

(3) Slowly ramp up the input power until the meter scale reaches the center of the '**INPUT OK**' section, which may occur at about 1W of transmitted power

(4) Set the selector knob to next position (**Set FSD**), and then adjust the **front panel potentiometer** until the needle reaches the full scale position

(5) Set the selector knob to the next position (**SWR**), and adjust the trimmer resistor labeled **TP1** to place the needle at the full scale position again

(6) Set the selector knob to the last remaining position (**R/Z**) and adjust the trimmer resistor labeled **TP2** to place the needle again at the full scale position

(7) All is done!

# Using It

In normal use, connect the instrument up to your transmitter (maximum 2W! or use an attenuator) as well as your antenna. Then, follow these steps:

(1) Turn the selector knob to the Set FSD position, and then, at your desired transmit frequency, transmit at approximately half a Watt, or 1W (2W max! or use an attenuator). Turn the rotary potentiometer on the front panel until the meter needle is at max.

(2) Now you are free to select either the SWR or R/Z positions, and examine the values. A good SWR value will be low (leftmost on the meter dial), and a good impedance value will be 50 ohms (close to the center of the meter dial).

(3) By slowly varying the transmit frequency, you should be able to find the antenna resonant frequency, by looking at the impedance. Picture a valley. If you traverse from low to high frequency, then the impedance will reduce down toward 50 ohm, and then beyond a certain frequency it will start increasing. The impedance valley bottom location is where the antenna is resonant.

# Main Circuit Board (with snap-off areas)
The instrument is built using a printed circuit board that has snap-away sections for the rotary controls. Most of the parts are large surface-mount, which is easy to assemble using a good pair of tweezers and a decent soldering iron. Note: Don't solder the BNC and N sockets, until you've looked at the section further below titled 'End Panel'.

<img width="100%" align="left" src="3d-renders/main-board.jpg">

This is what the underside looks like:

<img width="100%" align="left" src="3d-renders/main-board-underside.jpg">

As you can see, there are snap-off areas for the controls. Note that the PCB manufacturer may ask for an additional charge subsequently as a result of that. For instance, see JLC PCB rules here: https://jlcpcb.com/help/article/in-what-cases-will-there-be-charged-extra

# Alternative Main Circuit Board (with no snap-off areas)
If desired, you could order a PCB without the snap-off areas. You'd need to manually wire the controls (rotary switch and potentiometer) and resistor R8, or use a Flex PCB which is described next. 

<img width="100%" align="left" src="3d-renders/mainboard-only-render.jpg">

# Flex PCB Controls
If you like, you could use a flexible PCB for the controls and resistor R8. This is what the design looks like:
<img width="100%" align="left" src="3d-renders/flex-layout.jpg">

Here is the 3D view of it:
<img width="100%" align="left" src="3d-renders/flex-layout-top.jpg">

Here is the underside view of it:
<img width="100%" align="left" src="3d-renders/flex-layout-underside.jpg">

To use this flex PCB, you'll need to attach a Flat Flexible Cable (FFC) connector onto the mainboard:
<img width="100%" align="left" src="3d-renders/ffc-conn-detail.jpg">

The connector is available from AliExpess, search for **FPC 2.54mm Pitch Connector Flat Flexible Cable** and select an 8-way connector. There are straight and right-angle options. The 3D render above shows a right-angle connector, but a straight connector is probably easier to install without hitting the meter. 

## Important: Connector Orientation
Install the connector such that the Pin 1 marking on the flexible PCB mates with Pin 1 on the mainboard, which is indicated by a square pad. 

NOTE: You also have to ensure that the springy side of the terminal inside the connector mates with the copper side of the flexible PCB, to make good contact. If you're unsure, use a multimeter set to continuity mode and check there is good contact before soldering the connector. This will help eliminate the risk of installing the connector the wrong way around.


# End Panel
If you don't have the ability to drill holes, then optionally, an end panel printed circuit board can be created too. This eliminates needing to drill any holes.

<img width="100%" align="left" src="3d-renders/end-panel.jpg">

The BNC and N sockets are simply screwed onto the panel, and the ring tags can be soldered down.

<img width="100%" align="left" src="3d-renders/end-panel-inside.jpg">

After you've done that, the BNC and N connectors can be soldered to the main board PCB and then solder the edge of the main board against the horizontal bare copper area on the end panel.

# Top Panel
Optionally, if desired, you could use the top panel printed circuit board, if you don't have a way to cut out a meter panel rectangular hole. The top panel eliminates needing to cut out anything!

<img width="100%" align="left" src="3d-renders/top-panel.jpg">

The meter side ears are removed, and then the meter is fitted into the panel, and then the side ears are fitted on, and rotated until the meter is held in position firmly.

<img width="100%" align="left" src="3d-renders/top-panel-inside.jpg">

# Ordering the Circuit Boards

You'll need the following zip files:

[main-board-gerbers.zip](https://github.com/shabaz123/antenna-analyzer/raw/refs/heads/main/gerbers/main-board-gerbers.zip)

[end-panel-gerbers.zip](https://github.com/shabaz123/antenna-analyzer/raw/refs/heads/main/gerbers/end-panel-gerbers.zip)

[top-panel-gerbers.zip](https://github.com/shabaz123/antenna-analyzer/raw/refs/heads/main/gerbers/top-panel-gerbers.zip)

If you intend to go the flexible controls PCB route, then you don't need the main-board-gerbers.zip file, and instead, you need to replace that with these two files:

[mainboard-only-no-snap-off-areas.zip](https://github.com/shabaz123/antenna-analyzer/raw/refs/heads/main/gerbers/mainboard-only-no-snap-off-areas.zip)

[controls-flex-gerbers.zip](https://github.com/shabaz123/antenna-analyzer/raw/refs/heads/main/gerbers/controls-flex-gerbers.zip)


To order, go to any PCB manufacturer, e.g. JLCPCB, register for an account, then click on **Order Now** and then click on **Add Gerber File**. 

<img width="100%" align="left" src="images/order-example-1.jpg">

Select one of the zip files and upload it. You can accept all the defaults, but feel free to play around with the PCB color options (some may cost more, or take a couple of days longer to manufacture). Optionally, select **Remove Mark** which is in the **Mark on PCB** section (if you don't select Remove Mark, then a little serial number will appear on your board, and you might not want that for cosmetic reasons). Once you're done, click the **Save to Cart** button. 

<img width="100%" align="left" src="images/order-example-2.jpg">

Repeat for the other zip files as required. When you checkout the order, you'll see a list of the three boards. Click on the checkbox on the left side, to select all the items. 

<img width="100%" align="left" src="images/order-example-3.jpg">

Note: If you're ordering the flexible controls PCB, then you need to perform the following steps:

<img width="100%" align="left" src="images/flex-pcb-ordering.jpg">

Select **Global Shipping Direct Line**, which is usually the far cheaper delivery option. You can confirm the price in the box on the right, prior to finally paying (with, say PayPal).

<img width="100%" align="left" src="images/order-example-4.jpg">

Note that if you're ordering the flexible PCB, then it's highly recommended to select the 'Payment after Review' option, so that the manufacturer can e-mail you any queries that they may have. If they have trouble understanding what the flexible PCB is supposed to look like, you could send them the flex PCB layout and 3D render screenshots, so that they have some context.

# Parts List

The PDF parts list is downloadable here: 

[parts-list.pdf](https://github.com/shabaz123/antenna-analyzer/raw/refs/heads/main/components/parts-list.pdf)
NOTE: The PDF parts list is missing the Flat Flex Cable (FFC) connector, which is optional, it is only required if you're using the flex PCB.

The contents are reproduced here for convenience (including the FFC connector):

**Row**|**Identifier**|**Value**|**Qty**|**Description**|**Source**|**Part Code**
:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:
1|R1,R2,R3|3 x 150R Parallel|9|1206 150 ohm Resistor Thick Film 0.75W|Mouser|SG73P2BTTD151G
2|R4|15k|1|0805 Resistor|Mouser|RCG080515K0FKEA
3|R5|10k|1|0805 Resistor|Mouser|RCG080510K0FKEA
4|R6|27k|1|0805 Resistor|Mouser|RCS080527K0FKEA
5|R7|56k|1|0805 Resistor|Mouser|RCS080556K0FKEA
6|R8|470R|1|0805 Resistor|Mouser|CRCW0805470RFKEA
7|C1,C2,C3|470p|3|0805 Capacitor NP0 470pF|Mouser|08055A471J4T2A
8|C4,C5,C6|100n|3|0805 Capacitor X7R 100nF|Mouser|KAM21BR71H104JT
9|D1,D2,D3|1N5711W-7-F|3|Schottky Diode SOD-123|Mouser|1N5711W-7-F
10|TP1,TP2|10k Trimmer|2|Trimmer Resistor 10k 3386P|Mouser|3386P-1-103T
11|SK3|BNC Socket|1|BNC Socket 031-221-RFX|Mouser|031-221-RFX
12|SK4|N Socket|1|N Socket 1-1337417-0|Mouser|1-1337417-0
13|M1|100uA Panel Meter|1|85C17 100uA Panel Meter|AliExpress|85C17 100uA
14|P1|5k LIN (B) Potentiometer|1|RV097 Linear (B) 5k Potentiometer |AliExpress|RV097 B 5k
15|SW1|RS1010 Rotary Switch|1|RS1010 2 Pole 4 Way Switch|AliExpress|RS1010 2 Pole 4
16|n/a|Knob|2|Potentiometer Knob 10mm dia|AliExpress|Knob Flower Axis Diameter 10mm
17|n/a|8-way Cable|1|2.54 mm Pitch Grey Flat Cable 70mm|AliExpress|2.54mm Flat Cable 8P 70mm
18|n/a|4-way Cable|1|2.54 mm Pitch Grey Flat Cable 70mm|AliExpress|2.54mm Flat Cable 4P 70mm
19|n/a|FFC Connector|1|FPC 2.54mm Pitch Connector Flat Flexible Cable 8-way Straight (ideally)|AliExpress|FPC 2.54mm Pitch Connector Flat Flexible Cable Straight










