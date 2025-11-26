# STIG ID: WN11-CC-000350

## 🛡️ Vulnerability Description
**The WinRM service must not allow unencrypted traffic.**

Allowing unencrypted traffic on the WinRM service exposes administrative commands and data to interception. Attackers performing Man-in-the-Middle (MITM) attacks can sniff this traffic to gain insight into the environment or inject malicious commands into the management session.

---

## ⚙️ Remediation Strategy

**PowerShell Implementation Logic:**
This remediation utilizes the WSMan provider to harden the transport layer of remote management.

1.  **WSMan Configuration:** The script targets the service configuration at `WSMan:\localhost\Service`.
2.  **Attribute Modification:** It locates the `AllowUnencrypted` attribute.
3.  **Enforcement:** The script sets this value to `$false`. This ensures that the service rejects any connection attempts that do not utilize transport layer encryption (HTTPS).

[Link to Remediation Script](https://github.com/Aaniket09/STIGS-Implementation-Automation/blob/main/WN11-CC-000350/remediate-WN11-CC-000350.ps1)

---

## 📊 Rescan Verification Report

<img width="1256" height="325" alt="Screenshot 2025-11-26 104646" src="https://github.com/user-attachments/assets/557f4acf-ed28-424e-a360-baca77714c1e" />

<img width="2095" height="835" alt="Screenshot 2025-11-26 105950" src="https://github.com/user-attachments/assets/7936b2d9-0316-4d43-bc5e-ae6af0bc93d0" />

---
