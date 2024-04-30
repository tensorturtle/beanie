# Beanie

Beanie is a custom PCB designed to provide a variety of general purpose connection interfaces and capabilities to NVIDIA Jetson Nano or Xavier NX SoC coupled to [Leetop A203 Carrier Board](http://www.leetop.top/leetopen.asp?id=256).

## Design priorities
+ **Compactness**: Beanie's dimensions closely match that of the Leetop A203, which itself is not much bigger than the Jetson board. 
+ **Embedded**: Low-profile, reliable connectors for enclosed use cases.
+ **Open Source**: This repository contains everything you need to modify Beanie to your specifications.

## Capabilities

+ 4G LTE via header socket for a [Waveshare SIM7600X 4G Module](https://www.waveshare.com/sim7600g-h-4g-module.htm?sku=23992) (Choose options: "SIM7600G-H", "Standard Version + FPC antenna")
+ 2x USB 2.0 via JST 2.0mm 4-pin connectors (USB hub onboard)
+ Direct connection to pins 29,31,33 via JST 2.0mm 2-pin connectors. Can be used for GPIO digital read/write.
+ 1x I2C bus via JST 2.0mm 2-pin connector.
+ 1x Power Button (short the pins for power on/off) via JST 2.0mm 2-pin connector.
+ USB audio interface + powered 6W stereo speaker amp output with 12V power input.

