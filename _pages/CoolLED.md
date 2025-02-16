---
autogenerated: true
title: CoolLED
redirect_from:
  - /wiki/CoolLED
  - /wiki/PrecisExcite
layout: page
---

<table>
<tr>
<td><p>Summary:</p></td>
<td><p>Device adapter for <a href="http://www.CoolLED.com">CoolLED</a> pE LED illuminators</p></td>
</tr>
<tr>
<td><p>Authors:</p></td>
<td><p>Arthur Edelstein<br />
Gordon Scott</p></td>
</tr>
<tr>
<td><p>Documentation:</p></td>
<td><p>Arthur Edelstein<br />
Pariksheet Nanda</p></td>
</tr>
<tr>
<td><p>License:</p></td>
<td><p>BSD</p></td>
</tr>
<tr>
<td><p>Platforms:</p></td>
<td><p>Windows, Mac OS X, Linux (uses virtual serial interface over USB)</p></td>
</tr>
<tr>
<td><p>Devices:</p></td>
<td><p>pE-1<br />
pE-2<br />
pE-Integrator</p></td>
</tr>
<tr>
<td><p>Micro-Manager version</p></td>
<td><p>&gt;=1.3.34</p></td>
</tr>
</table>

------------------------------------------------------------------------

Note: CoolLED now has a new [closed-source device
adapter](http://www.coolled.com/wp-content/uploads/2014/04/MicroManager-Software-Summary-Sheet-R3.pdf)
for the pE-300 and pE-4000.

## Installation

Make sure the USB cable is connected, and that the module is powered up.

To install the CoolLED fluorescence illumination systems (pE-1, pE-2,
pE-300, pE-4000), one has to choose the preciseExcite device. This is
because CoolLED's original product was known as precisExcite and
Micro-Manager still knows it by the preciseExcite name.

No installation is required on Mac OS X, since it already has a driver
that will recognize the virtual serial port.

No installation is required on Linux, since it already has a driver that
will recognize the virtual serial port. The port can usually be found in
/dev/serial/by-id

On Windows:

-   Download the file CoolLED-pE-inf.zip from here:
    [www.coolled.com](http://www.coolled.com) and unzip the
    `CoolLED-pE.inf` and `.cat` files. You may need to ask CoolLED for
    access to the download area.
-   In the `Device Manager`, the CoolLED will appear under
    `Other Devices > CoolLED USB ...` with a yellow exclamation mark in
    the device icon.
-   To install your unzipped INF file, in the `Device Manager`,
    right-click on
    `CoolLED USB ... > Update Driver Software > Browse my computer for driver software`.
    Set the location to the place you unzipped the INF file.
-   On successful installation, the device will show up as
    `CoolLED USB Virtual Serial Port`.

pE-1 and pE-2 have one such port. pE-300 and pE-4000 have two Virtual
Serial Ports on the one USB connection.

## Device Configuration

In the `Hardware Configuration Wizard` (under the Micro-Manager `Tools`
menu):

-   In Step 2, add the `PrecisExcite` device and choose the appropriate
    COM Port. The default COM port settings (baud rate, etc) will work.
-   In Step 3, you may want to set the `Default Shutter` to the
    `precisExcite`.
-   You may also want to enable the `Auto shutter` checkbox is so that
    it automatically opens during a "Snap" or "Acquisition" and close
    immediately afterwards.

The `Trigger` and `TriggerSequence` properties can be used for external
triggering by TTL pulses. In the trigger sequence, channels are labeled
"A", "B", "C", "D", and a pause is denoted by "0" (zero).

