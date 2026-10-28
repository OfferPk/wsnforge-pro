Record \#513

# WSNForge Pro (v1.0.0)

Spacecraft Onboard Interface Systems — Low Data-Rate Wireless Communications Studio (CCSDS 882.0-M-1)  
MAGENTA BOOK COMPLIANT

Active WSN Nodes

4 Nodes

Duty Cycle (Energy)

12.5%

Harness Mass Saved

8.04 kg

Normative Audit

100%

## 

WSN Telemetry Controller

---

Target Wireless Sensor 0x0101: Fairing Strain Gauge Array \#1 (GTS Slot 9\) 0x0102: Solar Array Thermistor A (GTS Slot 10\) 0x0103: Propellant Line Pressure Sensor (GTS Slot 11\) 0x0104: Payload Bay Vibration Accelerometer (GTS Slot 12\) Superframe Order (SO / BO) SO=3 (123ms), BO=6 (983ms) — 12.5% Duty Cycle SO=2 (61ms), BO=6 (983ms) — 6.25% Low Power SO=4 (246ms), BO=6 (983ms) — 25.0% High Rate Acquire Wireless Telemetry Encapsulate Space Packet Calculate Harness Savings Run CCSDS 882.0 Normative Audit

## 

Superframe & Security State

---

Physical Layer: IEEE 802.15.4 2.4 GHz DSSS  
MAC Timing: 16 Slots (9 CAP, 7 CFP/GTS)  
Link Security: AES-128 CCM\* (MIC-32)  
Space Gateway: CCSDS Space Packet (APID 0x382)

## 

IEEE 802.15.4 MPDU & CCSDS Space Packet Dissector

---

Sensor Node: Fairing Strain Gauge Array \#1 \[0x0101\] Acquired Value: 245.00 microstrain (Raw ADC: 0x0992) Superframe Timing: GTS Slot 9 (Contention Free Period, 7.68 ms slot) 802.15.4 MPDU Wire: 498801208801000101010000000101010992A1B2C3D426C8 (24 Bytes) MAC Frame Control: 0x8849 (Data, Security Enabled, Short Addressing) AES-CCM\* Counter: FrameCounter=1 (MIC-32: A1 B2 C3 D4) CCSDS Space Packet: 0382C001000B69F53B4B01010992 (14 Bytes) Primary Header: APID=0x382, SeqCount=1, Unsegmented Secondary Header: SCET Timestamp=1777699659s (CUC Time Code)

## 

Spacecraft WSN Telemetry & Superframe Event Log

---

\[INIT\] WSNForge Pro v1.0.0 Online. \[SOIS\] CCSDS 882.0-M-1 Low Data-Rate Wireless Communications Standard Active. \[WSN\] Registered 4 Spacecraft Wireless Sensors (Strain, Thermal, Pressure, Vibration). \[SUPERFRAME\] SO=3 (122.88ms), BO=6 (983.04ms) \-\> 12.5% Energy Duty Cycle. \[SECURITY\] IEEE 802.15.4 AES-128 CCM\* Active with 32-bit Frame Counter Anti-Replay.

## 

Normative Compliance Audit Matrix (CCSDS 882.0-M-1)

---

| Req ID | Clause | Requirement Name | Verified Specification Clause | Verdict   |
| :---- | :---- | :---- | :---- | :---- |
| WSN-001 | §2.2 | WSN Topologies | Star and Cluster-Tree configurations with PAN Coordinator | PASS |
| WSN-002 | §3.2 | Physical Layer Conformance | IEEE 802.15.4 2.4 GHz DSSS (250 kbps) | PASS |
| WSN-003 | §3.3 | Superframe Timing | Beacon-enabled superframe with 12.5% duty cycle | PASS |
| WSN-004 | §3.4 | GTS Slot Scheduling | Deterministic Contention Free Period (CFP) slots | PASS |
| WSN-005 | §4.3 | Link Security Architecture | AES-128 CCM\* counter with MIC-32 verification | PASS |

