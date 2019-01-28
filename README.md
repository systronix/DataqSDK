# DataqSDK
Git repo for Linux SDK 1.1 from Dataq

## Purpose
The intent is to adapt [this old Dataq Linux beta code from 2007](http://support.dataq.com/viewforum.php?f=32), identified as version 1.0 on the web page but 1.1 in the archive file, written for the DI-154 and DI-194 (long [obsolete](https://www.dataq.com/resources/obsolete/products/)) to the current model [DI-1120](https://www.dataq.com/products/di-1120/) which replaces the DI-155, and the [DI-4208](https://www.dataq.com/products/di-4208/). Since the DI-1120 replaces the DI-155, and it is only one count away from the DI-154, adapting this old code might be straightforward.

## Why Dataq?
The Dataq line of [starter kits](https://www.dataq.com/data-acquisition/starter-kits/) offers amazing analog front end value. In particular, the DI-1120 and DI-4208 were chosen for their specific features and price points.

### DI-1120
+ Four armored analog differential inputs
+ 14-bit analog-to-digital resolution
+ 160 kHz sample throughput rate, so 40 KHz per channel if all four channels are active
+ Programmable range per channel: ±2, 5, 10, 20, 50, 100 V full scale
+ Up to 120 V rms without damage
+ 80 dB common mode rejection
+ Supports ChannelStretch™ multi-unit synchronization of "similar" devices, including the DI-4208
+ Adaptable low-pass filter per channel, corner frequency set as a function of sampling rate
+ Seven digital ports
+ $178 (2019 Jan)

### DI-4208
+ Eight armored analog differential inputs
+ 16-bit analog-to-digital resolution
+ 160 kHz sample throughput rate, so 20 KHz per channel if all eight channels are active
+ Programmable ranges: ±2, ±5, ±10, ±20, ±50, ±100 V full scale
+ Up to 120 V rms without damage
+ 50 dB common mode rejection
+ Supports ChannelStretch™ multi-unit synchronization of "similar" devices, including the DI-1120
+ Adaptable low-pass filter per channel, corner frequency set as a function of sampling rate
+ Seven digital ports
+ $299 (2019 Jan)

## Why Linux?
We want to be able run logging software 24/7 for days or weeks. Windows is not stable enough to run that long, and the trend in Windows 10 is to force updates such that you cannot keep a system from being rebooted for any defined time period. On the other hand, Linux PCs often run for weeks without needing a reboot, and this is even more true in the case of Linux servers and embedded systems. It's a different mindset from Windows. 

## Functionality - minimum
+ Trigger on level of any input exceeding a threshold
+ Save captured data to a file with an incrementing name, a timestamp, and device configuration
+ Synch the file data to the cloud

## Functionality - highly desired
+ It should be possible to create capture of "pre-trigger" data on these devices which do not natively support such a feature. This can be done by continuously sampling data and reading it into a ring buffer on the USB host.
+ This moves the triggering software into the USB host
+ This would make the overal function of these low-cost devices comparable to something costing much more

## Future Work
+ Support Teensy 3.5 as a smart USB Host for the Dataq "starter kit" level of devices. Log to uSD card and over Ethernet to the cloud
