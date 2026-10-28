# CCSDS 882.0-M-1 Low Data-Rate Wireless Communications (LDR-WIR) Engineering Specification

## 1\. Executive Summary & Purpose

The **Low Data-Rate Wireless Communications for Spacecraft Monitoring and Control** standard defined in **CCSDS 882.0-M-1 (Magenta Book, Issue 1, May 2013\)** establishes recommended practices for implementing onboard low-power wireless sensor networks (WSN) aboard spacecraft, planetary exploration landers, and launch vehicles.

Its primary operational objective is the elimination of parasitic copper wiring harnesses for non-flight-critical monitoring and control, enabling:

- Substantial dry mass reduction (5% to 10% of spacecraft mass saved).  
- Elimination of complex wiring routing through structural bulkheads, thermal Multi-Layer Insulation (MLI) blankets, and articulated deployable booms.  
- Rapid assembly, integration, and test (AIT) operations during spacecraft ground qualification.  
- Comprehensive structural health monitoring (SHM), thermal field mapping, and launch vibration logging.

---

## 2\. Network Topology & Physical Layer Architecture (§2.2, §3.2)

### 2.1 Topologies

- **Star Topology**: Central Spacecraft PAN Coordinator (gateway to the Onboard Computer / OBC) communicating directly with distributed sensor end-devices.  
- **Cluster-Tree Topology**: Hierarchical multi-hop routing extending wireless reach across multi-stage launch vehicle fairings and large deployable solar arrays.

### 2.2 Physical Layer (PHY)

- **Radio Standard**: IEEE 802.15.4 Direct Sequence Spread Spectrum (DSSS) using Offset Quadrature Phase-Shift Keying (O-QPSK) at 250 kbps symbol rates.  
- **Carrier Frequencies**: Worldwide 2.4 GHz Industrial, Scientific, and Medical (ISM) band (Channels 11 through 26 with 5 MHz spacing) and Sub-GHz (868/915 MHz).

---

## 3\. MAC Superframe & Deterministic GTS Scheduling (§3.3, §3.4)

The MAC layer operates under a synchronized beacon-enabled superframe:

- **Superframe Duration**: \$SD \= \\text{aBaseSuperframeDuration} \\times 2^{SO}\$  
- **Beacon Interval**: \$BI \= \\text{aBaseSuperframeDuration} \\times 2^{BO}\$  
- **Energy Duty Cycle**: \$\\text{DutyCycle} \= SD / BI \= 2^{SO \- BO}\$ (e.g. \$SO=3, BO=6 \\implies 12.5%\$ duty cycle).  
- **Contention Free Period (CFP)**: Allocates up to 7 Guaranteed Time Slots (GTS) for jitter-free, deterministic sensor sampling.

---

## 4\. Link-Layer Security Architecture (§4.3)

- **Algorithm**: AES-128 CCM\* (Counter with CBC-MAC).  
- **Protection**: Cryptographic payload encryption, Message Integrity Code (MIC-32 / MIC-64 / MIC-128), and a 32-bit sequential Frame Counter preventing replay attacks.

---

## 5\. Space Packet & SOIS Gateway (§5.1, §6.1)

The PAN Coordinator translates 802.15.4 sensor frames directly into standard **CCSDS 133.0-B-2 Space Packets**:

- Tagged with dedicated Application Process Identifier (APID `0x382`).  
- Integrated Spacecraft Elapsed Time (SCET) secondary header timestamping.  
- Bound directly to SOIS Device Access Service (DAS — CCSDS 871.0-M-1) and Subnetwork Packet Service (SPS — CCSDS 851.0-M-1) interfaces.