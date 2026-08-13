
# log 12/08/26

-setting up the experiment environment
-done some training in ghidra with arm64, going to start the actual research now

# log 13/08/26

acclaration here, i will drop the logs of the console and wireshark later while i try to fix the current situation of my phone 

and i also reported the charging problem to apple, hoping that they provide a solution without (possibly) ruinning the current research
# iPhone DFU/USB State Investigation

> ⚠️ Experimental research — unconfirmed behavior

## DO NOT TRY TO REPLICATE THIS WITH YOUR OWN PERSONAL DEVICE AS IT MIGHT FAIL TO CHARGE DUE TO UNKNOWN CONDTIONS (for now)

This repository documents an unexpected USB/DFU state observed during
experimentation with an iPhone and Debian GNU/Linux 13 (trixie).

## Observation

The device was observed by Linux as:

    05ac:f014 — Apple Device (Port DFU Mode)

The USB interface reported:

- Interface Class: 254
- Interface Subclass: 1
- Interface Protocol: 2
- USB Bus: 7
- Device Address observed: 30

The unusual observation was that the device subsequently appeared to
boot normally while the USB interface continued to identify itself as
an Apple DFU device.

## Tools

- Debian GNU/Linux 13 (trixie)
- irecovery
- dmesg
- lsusb
- tshark
- Wireshark
- Linux USB capture

## Evidence

Raw logs and packet captures are preserved in `evidence/`.

The USB capture was recorded during the original investigation and
has not been intentionally modified.

## Current status

This behavior has not been independently reproduced.

It has not been established whether:

- the BootROM remained active;
- the DFU interface was actually functional after normal boot;
- the behavior was caused by a USB state-machine issue;
- the behavior was caused by another firmware component; or
- the behavior was a host-side enumeration artifact.

No jailbreak or BootROM exploit is claimed.

The behavior may be reported privately to Apple Security.

The complete reproduction procedure is intentionally not published
while the behavior remains under investigation.

(proof of concepts will be dropping next week maybe, depends if the bug is easy to reproduce)

# log 13/08/26 Part 2

the iphone booted on normally after the "hard reset" i will start to investigate what really happened and upload the poc and console logs