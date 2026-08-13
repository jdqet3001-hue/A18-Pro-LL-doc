# Sanitized public evidence

Sanitized copies prepared for public release. The original uploaded artifacts are not overwritten.

Files:
- `dfu-observation.log` — DFU descriptor/USB observation and relevant terminal transcript.
- `iphone-usb-kernel.log` — iPhone USB enumeration/disconnect/recovery/DFU kernel events only.
- `dfu-enumeration.pcapng` — filtered USB capture containing the DFU device traffic.
- `dfu-session.pcapng` — filtered USB capture containing the DFU device traffic.
- `dfu-hybrid-observation.pcapng` — filtered USB capture containing the Apple/DFU device traffic from the hybrid-observation capture.

Sanitization:
- Unrelated USB traffic was removed from the PCAPNG captures; only the relevant Apple/DFU USB device traffic on bus 7 was retained.
- Device serial/ECID strings were redacted in text logs and in captured USB string-descriptor payloads, while descriptor lengths were preserved.
- usbmon kernel pointer IDs were replaced with stable local IDs where exposed in the text/PCAP.
- MAC addresses, host username/hostname, and MAC-derived network-interface names were redacted where present.
- The large `dfu-control(1).txt` upload was excluded because the reviewed content was dominated by unrelated USB traffic and did not contain identifiable DFU observation records.

The original files should be retained separately as the evidence originals.
