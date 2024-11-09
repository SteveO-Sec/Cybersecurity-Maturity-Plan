# Cybersecurity Maturity Plan for Enterprise
A strategic plan to improve an enterprise's cybersecurity posture by implementing SecurityOnion, network segmentation, and IAM policies.

## Introduction
This project outlines a comprehensive cybersecurity maturity plan for an enterprise transitioning from an immature security state to a mature, resilient security posture. The plan covers recommendations for network monitoring, access control, and policy implementation to strengthen the organization's defenses while ensuring service availability.

## Objectives
The main objectives of this plan are to:
- Deploy SecurityOnion for centralized monitoring, log management, and intrusion detection.
- Implement network segmentation through VLANs to prevent lateral movement.
- Enhance Identity and Access Management (IAM) with multi-factor authentication and restricted administrative privileges.
- Establish essential security policies and best practices for continuous improvement.

## Current State and Challenges
The enterprise currently faces several security challenges, including:
- No SIEM or central log collection system.
- Lack of internet filtering and vulnerability management.
- Over-permissioned access control: all employees have VPN access by default, and users are administrators on their endpoints.
- Legacy web application on an unsupported OS, creating a non-patchable vulnerability.
- No password rotation policy.
  
These issues create an environment that is vulnerable to both internal and external threats, requiring a strategic overhaul to establish a secure and reliable network.

## Key Recommendations
### 1. Deploy SecurityOnion
   - **Architecture**: Use one primary node for log management and multiple sensor nodes across network segments for packet analysis and alert generation.
   - **Features**: Utilize Zeek, Suricata, and Kibana for real-time traffic analysis, threat detection, and visualization.

### 2. Implement Network Segmentation
   - **VLANs**: Segment the network into VLANs for users, servers, and management to reduce risk.
   - **DMZ**: Place external-facing servers and the legacy web application in a DMZ to isolate them from the internal network.

### 3. Enhance Identity and Access Management
   - **Multi-Factor Authentication (MFA)**: Enforce MFA for VPN access and remove unnecessary administrative privileges from users and support staff.
   - **Password Policy**: Implement a 90-day password change policy with complexity requirements.

### 4. Introduce Vulnerability Management and Endpoint Security
   - **OpenVAS**: Conduct regular vulnerability scans with OpenVAS to proactively identify weaknesses.
   - **Endpoint Protection**: Install antivirus with state monitoring on all endpoints and servers.

## Technical Breakdown

The recommended infrastructure includes:

- **SecurityOnion Nodes**:
  - **Primary Node**: Manages data processing, log ingestion, and provides a central management interface for log aggregation and analysis.
  - **Sensor Nodes**: Placed across network segments to monitor traffic, capture packets, and generate alerts, with data forwarded to the primary node.

- **Network Tap**: Passively monitors network traffic to feed data to sensor nodes without disrupting data flow.

- **Firewall**: Supports deep packet inspection, intrusion detection, VPN capabilities, and traffic filtering, with multiple interfaces to manage VLAN segmentation.

- **Core Switches**: Layer 3 switches with Quality of Service (QoS) and VLAN support, essential for effective network segmentation and traffic management.

- **Data Retention Storage**: Network-attached storage (NAS) to handle log and data retention, meeting organizational requirements for backup and data security.

> **Note**: Specific hardware specifications, including CPU, RAM, and storage, should be selected based on the organization's traffic volume, log retention needs, and processing requirements.


## Conclusion
Implementing this cybersecurity maturity plan will greatly enhance the organization’s ability to detect, respond to, and mitigate security threats. By prioritizing centralized monitoring, network segmentation, and IAM controls, the enterprise will be positioned to proactively manage risks and ensure business continuity.

---

## Full Documentation
For a detailed breakdown, including visuals of the current and proposed network architecture, please refer to the [Cybersecurity Maturity Plan Document](path/to/document.pdf).

---

