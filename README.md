# Beanie

![](photos/beanie-v1-top.jpg)

Beanie is a custom PCB designed to provide a variety of general purpose connection interfaces and capabilities to NVIDIA Jetson Nano or Xavier NX SoC coupled to [Leetop A203 Carrier Board](http://www.leetop.top/leetopen.asp?id=256).

## Design priorities
+ **Compactness**: Beanie's dimensions closely match that of the Leetop A203, which itself is not much bigger than the Jetson board. 
+ **Embedded**: Low-profile, reliable connectors for enclosed use cases.
+ **Open Source**: This repository contains everything you need to modify Beanie to your specifications.


![](photos/beanie-v1-quarter.jpg)


## Capabilities

+ 4G LTE via header socket for a [Waveshare SIM7600X 4G Module](https://www.waveshare.com/sim7600g-h-4g-module.htm?sku=23992) (Choose options: "SIM7600G-H", "Standard Version + FPC antenna")
+ 2x USB 2.0 via JST 2.0mm 4-pin connectors (USB hub onboard)
+ Direct connection to pins 29,31,33 via JST 2.0mm 2-pin connectors. Can be used for GPIO digital read/write.
+ 1x I2C bus via JST 2.0mm 2-pin connector.
+ 1x Power Button (short the pins for power on/off) via JST 2.0mm 2-pin connector.
+ USB audio interface + powered 6W stereo speaker amp output with 12V power input.

## Pricing

19 USD per unit. Minimum order quantity is 5.

Shipping is between 10 to 30 USD.

## Order your Beanie

Familiarity with EasyEDA and JLCPCB, as well as basic hand solering is required to manufacture this board using the PCB file provided in this repository.

You can contact me (tensorturtle@gmail.com) and I'll have it manufactured and sent to you for a fee.

If you'd like to do it youself, read on.

### Ordering it yourself

Log into EasyEDA and JLCPCB first. Instructions here are provided for EasyEDA STD version.

In the `easyeda-ready-to-manufacture` directory, find `beanie-v1.1.json` and upload it to [EasyEDA](https://easyeda.com) (`File` -> `Open` -> `EasyEDA`). Go to `Fabrication` -> `One-click Order PCB/SMT`. Now, at the JLCPCB order screen, use the following settings (choice in parenthesis) :
+ Base Material: FR-4
+ Layers: 2
+ Dimensions: 95 * 52.09
+ PCB Qty: 5 (your choice; 5 is minimum)
+ Product type: Industrial/Consumer electronics
+ Different Design: 1
+ Delivery Format: Single PCB
+ PCB Thickness: 1.6 (greater than 0.8mm recommended)
+ PCB Color: Green (other colors are fine, they take longer)
+ Silkscreen: White
+ Surface Finish: HASL with lead (up to you)
+ Outer Copper Weight: 1 oz
+ Via Covering: Tented
+ Board Outline Tolerance: Regular
+ Confirm Production File: No (up to you)
+ Remove Order Number: No (up to you)
+ Flying Probe Test: Fully Test
+ Gold Fingers: No
+ Castellated Holes: No
+ Edge Plating: No

Turn "PCB Assembly" ON!

Use default settings. All advanced options are also unchanged.
+ PCBA Type: Economic
+ Assembly Side: Top Side
+ PCBA Qty: 5 (should match PCB quantity)
+ Tooling holes: added by JLCPCB
+ Confirm Parts Placement: No

Continue onwards. the Assembly-BOM and Assembly-CPL should already be uploaded. If that is not the case, start again from EasyEDA.

At BOM selection, *unselect* J1 and J2. The 40-pin and 14-pin 2.54mm headers must be soldered by hand by yourself because it is soldered to the bottom side. They must be ordered separately.

The PCB + Assembly price is around 90 to 95 USD, and shipping is typically between 10 to 30 USD.

### Extra Components

Beanie will need a few more parts to be fully integrated with Leetop A203:

+ 40 (2x20) and 14 (2x7) 2.54mm pin female headers. Solder them to the underside of the Beanie so that it interfaces with the male headers on the A203.
+ Short (20mm) 0.5mm pitch 20P ZIF flat cable, with the gold contacts on each end on different sides.
+ 4 set of:
  + M3 10mm hex standoff spacer
  + ~2.5mm additional spacer (or nut)
  + M3 philips head bolt

## Modify Beanie

In EasyEDA, create a new empty project.

Find the three .json files in `easyeda-full-project/beanie-v1.1-project` and load each one. The three files are:
+ Schematic
+ Layout for debug board (larger PCB, used for developing and testing the board itself)
+ Layout for production board

This gives you absolutely full control over the design and implementation of the board.

Editing text: Click on a text in EasyEDA. In 'Text Properties', click 'Fonts management'. Upload DIN-Bold.otf found in the `fonts` directory.
