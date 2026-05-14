# Network Design Proposal for Berlin Office

This repository contains my networking assignment for Study.com. The project is a network design proposal for a new three-story tech startup office in Berlin, Germany.

## Assignment Overview

The goal of this assignment was to design a secure and stable network infrastructure using physical layer concepts, data link layer protocols, IP addressing, subnetting, and network security planning.

The proposal includes:

- Switch, router, and wireless access point allocation
- Floor-by-floor network device planning
- Security device recommendations
- Physical media and cabling recommendations
- IP address class selection and subnet mask planning

## Scenario

A tech startup based in Frankfurt, Germany has opened a new three-story office in Berlin. Each floor supports a different department:

- 1st Floor: Administration
- 2nd Floor: Developers
- 3rd Floor: Sales

The network must support wired devices, wireless users, VoIP phones, printers, guest Wi-Fi, and secure access to company resources.

## Files

| File | Description |
|---|---|
| `Network_Design_Proposal_Berlin_Office.docx` | Final Word document for the assignment |
| `README.md` | Repository overview and file description |

## Main Design Summary

The proposed network design includes:

- 7 access switches
- 1 core/distribution switch
- 1 edge router
- 1 firewall/security gateway
- 7 Wi-Fi 6 access points
- Cat6 or Cat6a Ethernet cabling for endpoint connections
- Fiber optic cabling for inter-floor backbone connections
- VLANs for departments, voice, printers, guests, and network management
- Private Class A IP addressing using `10.20.0.0/16`
- `/24` subnets using the subnet mask `255.255.255.0`

## Purpose

This repository is for academic submission and portfolio tracking. It shows basic network design planning, including device allocation, physical media selection, security planning, and subnetting.
