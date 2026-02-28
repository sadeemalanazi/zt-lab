# ZTA Component Definitions

## Policy Engine (PE)
The Policy Engine is the decision-making component of Zero Trust Architecture. It evaluates security signals such as user identity, device posture, and network location before determining whether access should be granted or denied. It does not enforce access itself but makes the final authorization decision based on defined policies.

## Policy Administrator (PA)
The Policy Administrator carries out the decision made by the Policy Engine. It translates the decision into action by generating session credentials or blocking access. It communicates instructions to the enforcement layer to either allow or deny the connection.

## Policy Enforcement Point (PEP)
The Policy Enforcement Point acts as the gatekeeper that physically allows or blocks access to the protected resource. It enforces the decision given by the Policy Administrator. The PEP does not make security decisions; it only enforces them.

# Core Principle Application

## Selected Principle: Verify Explicitly

The Verify Explicitly principle requires that every access request be evaluated using multiple security signals before access is granted. Trust is never assumed.

For example, when an HR employee attempts to access the HR Employee PII Database at the Golden State Water Treatment Facility, the Policy Engine checks whether the user authenticated with multi-factor authentication, whether the device is encrypted and compliant, and whether the login attempt originates from an approved U.S. location. If any of these conditions fail, the Policy Engine denies access. This demonstrates Verify Explicitly because access is continuously validated before being granted.

# Simplified Policy Table

| Policy Requirement (Signal) | Condition to be Met by User | Action if Condition is Met |
|-----------------------------|-----------------------------|----------------------------|
| User Identity | Must authenticate with MFA and be a member of the HR Security Group | Grant Access |
| Device Posture | Must use a company-issued encrypted device with updated security software | Grant Access |
| Network Context | Must connect from an approved U.S. location and non-flagged IP address | Grant Access |

# Git Repository Metadata

Filename: ZT-Policy-Profile.md

Commit Message:
Created Zero Trust Policy Profile for HR PII Database – https://github.com/sadeemalanazi/zt-lab 
