# HIDCaster
Control all of your BLE equipped devices with the HID's already in your hands.

Alright, using a single-board computer as a hub for your wired mouse and keyboard, an ESP32 with native USB, and a lightswitch, I've colaged together some existing libraries and the afformentioned electronics to control my media computer with the kb and mouse I'm already using with the flip of a switch. 

Basically the ESP32-S3 decides whether to resend the HID reoports over BLE or USB based on the switch state. I bet this could be a little unencumbered by using the microcontroller as a USB host. The BLE library and the USB HID library are using Identical structs with identical names in KeyReport. Perhaps that struct could be broken out into its own file that both use? At the moment, I've renamed one to *BleKeyReport* to apease the compiler.

The kCtx.c/.h library I've included that probably looks utterly superfluous to this application is an eye toward a subsequent project with this at its core.

I tested this with an Orange Pi 5 plus as the SBC, an ESP32-S3 Devkit as the microcontroller, and my partner controls a Linux Lenovo from the HID's at a Windows 11 IBuyPower gaming rig.
