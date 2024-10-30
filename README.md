# Cybersecurity Maturity Plan for Enterprise
A strategic plan to improve an enterprise's cybersecurity posture by implementing SecurityOnion, network segmentation, and IAM policies.

## Introduction
This project outlines a comprehensive cybersecurity maturity plan for an enterprise transitioning from an immature security state to a mature, resilient security posture. The plan covers recommendations for network monitoring, access control, and policy implementation to strengthen the organization's defenses while ensuring service availability.

## Objectives
The main objectives of this plan are to:
- Deploy SecurityOnion for centralized monitoring, log management, and intrusion detection.
- Implement network segmentation through VLANs to limit lateral movement in case of a breach.
- Enhance Identity and Access Management (IAM) with multi-factor authentication and restricted administrative privileges.
- Establish essential security policies and best practices for continuous improvement.

## Current State and Challenges
The enterprise currently faces several security challenges, including:
- No SIEM or central log collection system.
- Lack of internet filtering and vulnerability management.
- Insufficient access control: all employees have VPN access by default, and users are administrators on their endpoints.
- Legacy web application on an unsupported OS, creating a non-patchable vulnerability.
- No regular password updates, with some accounts over 10 years old.
  
These issues create an environment that is vulnerable to both internal and external threats, requiring a strategic overhaul to establish a secure and reliable network.

## Key Recommendations
### 1. Deploy SecurityOnion
   - **Architecture**: Use one primary node for log management and multiple sensor nodes across network segments for packet analysis and alert generation.
   - **Features**: Leverage Zeek, Suricata, and Kibana for real-time traffic analysis, threat detection, and visualization.

### 2. Implement Network Segmentation
   - **VLANs and DMZ**: Segment the network into VLANs for users, servers, and management to reduce risk. Place external-facing servers and the legacy web application in a DMZ to isolate them from the internal network.

### 3. Enhance Identity and Access Management
   - **Multi-Factor Authentication (MFA)**: Enforce MFA for VPN access and remove unnecessary administrative privileges from users and support staff.
   - **Password Policy**: Implement a 90-day password change policy with complexity requirements.

### 4. Introduce Vulnerability Management and Endpoint Security
   - **OpenVAS**: Conduct regular vulnerability scans with OpenVAS to proactively identify weaknesses.
   - **Endpoint Protection**: Install antivirus with state monitoring on all endpoints and servers, and configure antivirus specifically for server environments to avoid compatibility issues.

## Technical Breakdown
The recommended infrastructure includes:
- **SecurityOnion Primary Node**: 8-core CPU, 32GB RAM, 2TB SSD.
- **SecurityOnion Sensor Nodes**: 4-core CPU, 16GB RAM, 1TB SSD per node.
- **Network Tap and Core Switches**: 10 Gbps Layer 3 switches to support VLANs and QoS.
- **Firewall**: pfSense XG-1541 with intrusion detection, web filtering, and VPN capabilities.
- **Network Attached Storage (NAS)**: 10TB storage for data retention and backups.

## Conclusion
Implementing this cybersecurity maturity plan will greatly enhance the organization’s ability to detect, respond to, and mitigate security threats. By prioritizing centralized monitoring, network segmentation, and IAM controls, the enterprise will be positioned to proactively manage risks and ensure business continuity.

---

## Full Documentation
For a detailed breakdown, including visuals of the current and proposed network architecture, please refer to the [Cybersecurity Maturity Plan Document](path/to/document.pdf).

---

