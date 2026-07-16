# Pioneer AVH-7148ZC / Toyota 86140-0H020 Reverse Engineering Project

## Project Goal

Ultimate objective:
Replace the factory Pioneer software with our own software while retaining the original hardware where possible.

Secondary objectives:
- Understand the complete hardware architecture.
- Reverse engineer the boot process.
- Document everything publicly on GitHub.
- Create the definitive reference for this head unit.

---

# Status System

🟢 Confirmed

🟡 Probable

🔴 Unknown

⚫ Disproved

---

# Investigation Summary

## INV-001 – Head Unit Removal

🟢 Successfully removed the Pioneer head unit from the Peugeot.

Discovered:
- Removal requires more than just the two top screws.
- Front assembly is more complex than expected.

---

## INV-002 – Initial Teardown

🟢 Covers removed.

Photographed:
- Main PCB
- Display PCB
- Rear PCB
- Power supply section

Large photographic record created.

---

## INV-003 – Display Board

Display board identified.

Board markings:

- MDK 421V-0
- CN05564-01
- Tim846FQ121H

Identified:

- 🟢 LCD interface
- 🟢 Touchscreen interface
- 🟢 Push-lock ribbon connectors

Originally thought to be flip-lock.

⚫ Disproved after close-up inspection.

---

## INV-004 – Ribbon Connector

Ribbon connector investigated.

Conclusion:

🟢 Connector uses two push-release tabs.

Procedure:

1. Push both black T-shaped tabs.
2. Ribbon slides out.
3. No force required.

**Warning:** Do not try to lift the connector like a flip-lock ZIF connector.

---

## INV-005 – Internal SD Card Discovery

Huge breakthrough.

Found:

- 🟢 Internal Panasonic 4GB SDHC card.

Observations:

- Windows detects insertion/removal.
- No drive letter appears.
- No disk appears in Disk Management.
- Vehicle does not have navigation.

Working theories:

- 🟡 Operating system stored here.
- 🟡 Pioneer SD password protection (CMD42).

---

## Current Status

### 🟢 Confirmed

- Toyota 86140-0H020
- Pioneer AVH-7148ZC
- Panasonic Internal SD
- Renesas R5F6417
- NXP SAF7741HV/135
- Macronix Flash
- ALPS RF module
- Push-lock ribbon connectors

### 🟡 Probable

- Embedded Linux
- Main processor under RF shield
- Internal SD contains operating system

### 🔴 Unknown

- Application processor
- Bootloader
- UART
- JTAG
- Secure Boot
- Linux version

---

# Long-Term Goals

- Phase 1 – Hardware identification ✅
- Phase 2 – Identify application processor
- Phase 3 – Dump firmware
- Phase 4 – Recover SD contents
- Phase 5 – Understand bootloader
- Phase 6 – Modify firmware
- Phase 7 – Custom operating system